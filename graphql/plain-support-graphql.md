# Plain GraphQL API

Representative GraphQL schema for the [Plain](https://www.plain.com/) API-first customer
support platform. Plain exposes a **single GraphQL endpoint** that the Plain UI itself
consumes, so the API surface and the product surface are the same.

- API reference: <https://www.plain.com/docs/api-reference/graphql/introduction>
- Documentation: <https://www.plain.com/docs>
- GraphQL SDK: <https://www.plain.com/docs/graphql/sdk> (`@team-plain/graphql`)
- GitHub: <https://github.com/team-plain>

---

## Endpoint

```
POST https://core-api.uk.plain.com/graphql/v1
Content-Type: application/json
Authorization: Bearer plainApiKey_xxx
```

A single POST endpoint serves the whole API. Requests carry a JSON body with a `query`
string (a GraphQL query or mutation) and an optional `variables` object. The `/graphql/v1`
path is the versioned production endpoint; Plain hosts its core API in the UK region.

---

## Authentication

Plain uses **API keys** issued to a **Machine User**. You create a Machine User in
Settings, then generate an API key (prefixed `plainApiKey_`) that is shown only once.
Each key carries **fine-grained permissions** (for example `customer:create`,
`thread:create`, `thread:edit`, `webhookTarget:create`); a call that lacks a required
permission returns an error naming the missing permission. The key is sent as a Bearer
token:

```
Authorization: Bearer plainApiKey_xxx
```

---

## Error handling

Plain returns **mutation errors as typed data, not as thrown exceptions**. Every mutation
returns an `*Output` type with the created/updated resource plus an optional `error`
field (`MutationError`) carrying a machine-readable `code`, a human `message`, the
`type`, and a list of per-field `fields`. Transport- and schema-level problems still come
back in the standard top-level GraphQL `errors` array.

---

## Domains

| Domain | Description |
|--------|-------------|
| Customers | People you support; identified by external id or email, upserted idempotently, grouped, and flaggable as spam. |
| Threads | The unit of support work (Plain's "ticket"); created, assigned, escalated, and moved through statuses. |
| Timeline & Events | A thread's chronological feed; custom customer and thread events can be appended. |
| Messages | Replies to threads and emails, new outbound emails, and AI suggested replies. |
| Labels & Tiers | Labels and label types on threads; tiers (with SLAs) on companies and tenants. |
| Webhooks | Webhook targets, event-type subscriptions, and delivery-attempt inspection. |

---

## Key operations

### Queries
| Query | Purpose |
|-------|---------|
| `customer(customerId:)` / `customerByEmail(email:)` | Fetch a single customer. |
| `customers(first:, after:, filters:)` | Paginated customer list. |
| `thread(threadId:)` / `threads(first:, after:, filters:)` | Fetch threads. |
| `threadTimelineEntries(threadId:, first:, after:)` | Read a thread's timeline. |
| `labelTypes(first:, after:)` | List label types. |
| `tiers(first:, after:)` | List tiers and their SLAs. |
| `webhookTargets(first:, after:)` | List configured webhook targets. |
| `webhookTarget(webhookTargetId:)` | Fetch one webhook target with delivery attempts. |

### Mutations
| Mutation | Purpose |
|----------|---------|
| `upsertCustomer(input:)` | Idempotently create or update a customer (`onCreate` / `onUpdate`). |
| `deleteCustomer(input:)` | Delete a customer. |
| `markCustomerAsSpam(input:)` / `unmarkCustomerAsSpam(input:)` | Spam controls. |
| `createThread(input:)` | Open a new thread for a customer. |
| `updateThread(input:)` | Update thread attributes. |
| `changeThreadStatus(input:)` | Move a thread between TODO / SNOOZED / DONE. |
| `assignThread(input:)` / `unassignThread(input:)` | Assignment. |
| `replyToThread(input:)` | Append a reply that is delivered to the customer. |
| `sendNewEmail(input:)` | Send a brand-new outbound email. |
| `createThreadEvent(input:)` | Append a custom event to a thread timeline. |
| `createCustomerEvent(input:)` | Append a custom event to a customer timeline. |
| `addLabels(input:)` / `removeLabels(input:)` | Manage labels on a thread. |
| `createWebhookTarget(input:)` / `updateWebhookTarget(input:)` / `deleteWebhookTarget(input:)` | Manage webhook targets. |

See [`plain-support-schema.graphql`](./plain-support-schema.graphql) for a representative
SDL of the main types, queries, and mutations. It is a documented subset for reference,
not the full generated schema - fetch the live schema from the API explorer for the
complete, authoritative definition.

---

## Examples

### Fetch a customer by email
```graphql
query {
  customerByEmail(email: "ada@example.com") {
    id
    fullName
    email {
      email
      isVerified
    }
  }
}
```

### Upsert a customer
```graphql
mutation upsertCustomer($input: UpsertCustomerInput!) {
  upsertCustomer(input: $input) {
    result
    customer {
      id
      fullName
    }
    error {
      message
      type
      code
    }
  }
}
```
```json
{
  "input": {
    "identifier": { "emailAddress": "ada@example.com" },
    "onCreate": {
      "fullName": "Ada Lovelace",
      "email": { "email": "ada@example.com", "isVerified": true }
    },
    "onUpdate": {
      "fullName": { "value": "Ada Lovelace" }
    }
  }
}
```

### Create a thread
```graphql
mutation createThread($input: CreateThreadInput!) {
  createThread(input: $input) {
    thread {
      id
      title
      status
    }
    error {
      message
      type
      code
    }
  }
}
```
```json
{
  "input": {
    "customerIdentifier": { "emailAddress": "ada@example.com" },
    "title": "Cannot reset password",
    "components": [
      { "componentText": { "text": "I am locked out of my account." } }
    ]
  }
}
```

### Reply to a thread
```graphql
mutation replyToThread($input: ReplyToThreadInput!) {
  replyToThread(input: $input) {
    thread {
      id
    }
    error {
      message
      type
      code
    }
  }
}
```
```json
{
  "input": {
    "threadId": "th_01HXXXXXXXXXXXXXXXXXXXXXXX",
    "textContent": "We have sent you a password reset link."
  }
}
```

### Create a thread event (timeline)
```graphql
mutation createThreadEvent($input: CreateThreadEventInput!) {
  createThreadEvent(input: $input) {
    threadEvent {
      id
      title
      timestamp { iso8601 }
    }
    error {
      message
      type
      code
    }
  }
}
```

### Create a webhook target
```graphql
mutation createWebhookTarget($input: CreateWebhookTargetInput!) {
  createWebhookTarget(input: $input) {
    webhookTarget {
      id
      url
      eventSubscriptions {
        eventType
      }
    }
    error {
      message
      type
      code
    }
  }
}
```
