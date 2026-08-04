# Plain (plain-support)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
