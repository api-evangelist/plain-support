# Plain (plain-support)

Plain is an API-first customer support platform built around a single GraphQL API. Everything in the product - customers, threads, timeline entries, messages, labels, tiers, and webhooks - is exposed through the same GraphQL endpoint the Plain UI consumes, letting teams build support into their own products with threads, customer context, and a unified timeline.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/plain-support/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/plain-support/refs/heads/main/apis.yml)

## Tags

- Customer Support
- Help Desk
- GraphQL
- Threads
- Customer Communication
- API First

## Timestamps

- **Created:** 2026-06-20
- **Modified:** 2026-06-20

## APIs

### Plain Customers API

Create, update, fetch, and manage customers and customer groups via GraphQL. Idempotent upsertCustomer with onCreate / onUpdate semantics keyed on an external id or email, plus customer events and spam controls.

- **Human URL:** [https://www.plain.com/docs/api-reference/graphql/customers/upserting-customers](https://www.plain.com/docs/api-reference/graphql/customers/upserting-customers)
- **Base URL:** `https://core-api.uk.plain.com/graphql/v1`

#### Tags

- Customers
- Identity
- GraphQL

#### Properties

- [GraphQL](graphql/plain-support-graphql.md) — [GraphQL Specification](https://spec.graphql.org/)
- [Documentation](https://www.plain.com/docs/api-reference/graphql/customers/upserting-customers)
- [API Reference](https://www.plain.com/docs/api-reference/graphql/introduction)
- [OpenAPI](openapi/plain-support-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/plain-support.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/plain-support.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Plain Threads API

Create, fetch, update, assign, escalate, and change the status of threads - Plain's unit of support work - plus thread fields, autoresponders, and thread import for backfilling history.

- **Human URL:** [https://www.plain.com/docs/api-reference/graphql/threads/create-threads](https://www.plain.com/docs/api-reference/graphql/threads/create-threads)
- **Base URL:** `https://core-api.uk.plain.com/graphql/v1`

#### Tags

- Threads
- Tickets
- Conversations
- GraphQL

#### Properties

- [GraphQL](graphql/plain-support-graphql.md) — [GraphQL Specification](https://spec.graphql.org/)
- [Documentation](https://www.plain.com/docs/api-reference/graphql/threads/create-threads)
- [API Reference](https://www.plain.com/docs/api-reference/graphql/introduction)
- [OpenAPI](openapi/plain-support-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/plain-support.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/plain-support.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Plain Timeline & Events API

Read a thread's chronological timeline and append custom customer and thread events. Timeline entries unify messages, status changes, label changes, and your own structured events into one feed of context.

- **Human URL:** [https://www.plain.com/docs/api-reference/graphql/events/create-a-thread-event](https://www.plain.com/docs/api-reference/graphql/events/create-a-thread-event)
- **Base URL:** `https://core-api.uk.plain.com/graphql/v1`

#### Tags

- Timeline
- Events
- Timeline Entries
- GraphQL

#### Properties

- [GraphQL](graphql/plain-support-graphql.md) — [GraphQL Specification](https://spec.graphql.org/)
- [Documentation](https://www.plain.com/docs/api-reference/graphql/events/create-a-thread-event)
- [API Reference](https://www.plain.com/docs/api-reference/graphql/introduction)
- [OpenAPI](openapi/plain-support-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/plain-support.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/plain-support.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Plain Messages API

Reply to threads and emails, send new outbound emails, and surface AI suggested replies. Messages are appended to the thread timeline and delivered over the customer's channel (email, Slack, in-app, etc.).

- **Human URL:** [https://www.plain.com/docs/api-reference/graphql/messages/reply-to-threads](https://www.plain.com/docs/api-reference/graphql/messages/reply-to-threads)
- **Base URL:** `https://core-api.uk.plain.com/graphql/v1`

#### Tags

- Messages
- Replies
- Email
- GraphQL

#### Properties

- [GraphQL](graphql/plain-support-graphql.md) — [GraphQL Specification](https://spec.graphql.org/)
- [Documentation](https://www.plain.com/docs/api-reference/graphql/messages/reply-to-threads)
- [API Reference](https://www.plain.com/docs/api-reference/graphql/introduction)
- [OpenAPI](openapi/plain-support-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/plain-support.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/plain-support.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Plain Labels & Tiers API

Add and remove labels on threads, manage label types, and assign companies and tenants to tiers that drive SLAs and prioritization across the support workflow.

- **Human URL:** [https://www.plain.com/docs/api-reference/graphql/labels/add-labels](https://www.plain.com/docs/api-reference/graphql/labels/add-labels)
- **Base URL:** `https://core-api.uk.plain.com/graphql/v1`

#### Tags

- Labels
- Tiers
- SLAs
- GraphQL

#### Properties

- [GraphQL](graphql/plain-support-graphql.md) — [GraphQL Specification](https://spec.graphql.org/)
- [Documentation](https://www.plain.com/docs/api-reference/graphql/labels/add-labels)
- [API Reference](https://www.plain.com/docs/api-reference/graphql/introduction)
- [OpenAPI](openapi/plain-support-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/plain-support.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/plain-support.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Plain Webhooks API

Create, fetch, update, and delete webhook targets, choose which event types to subscribe to, and inspect delivery attempts to drive outbound integrations off thread and customer events.

- **Human URL:** [https://www.plain.com/docs/api-reference/graphql/webhooks/create-a-webhook-target](https://www.plain.com/docs/api-reference/graphql/webhooks/create-a-webhook-target)
- **Base URL:** `https://core-api.uk.plain.com/graphql/v1`

#### Tags

- Webhooks
- Events
- Integrations
- GraphQL

#### Properties

- [GraphQL](graphql/plain-support-graphql.md) — [GraphQL Specification](https://spec.graphql.org/)
- [Documentation](https://www.plain.com/docs/api-reference/graphql/webhooks/create-a-webhook-target)
- [API Reference](https://www.plain.com/docs/api-reference/graphql/introduction)
- [OpenAPI](openapi/plain-support-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/plain-support.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/plain-support.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [GitHub Organization](https://github.com/team-plain)
- [LinkedIn](https://www.linkedin.com/company/plain-support)
- [Website](https://www.plain.com)
- [Documentation](https://www.plain.com/docs)
- [Plans](plans/plain-support-plans-pricing.yml)
- [Rate Limits](rate-limits/plain-support-rate-limits.yml)
- [Fin Ops](finops/plain-support-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
