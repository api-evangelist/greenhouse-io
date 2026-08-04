# Greenhouse (greenhouse-io)

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

Greenhouse Software is an enterprise applicant tracking system (ATS) and end-to-end
hiring platform spanning sourcing, structured interviewing, offer management, hiring
decisions, and new-hire onboarding. The company markets itself across early-stage,
scaling, and enterprise tiers (Core, Plus, Pro) and lists customers including DoorDash,
Betterment, MLB, Coupang, HelloFresh, Trivago, and the NFL. Greenhouse exposes a broad
developer surface — Harvest (REST), Job Board, Audit Log (Pro), Candidate Ingestion
(Partner), Onboarding (GraphQL), Assessment (partner-hosted), and Recruiting /
Onboarding Webhooks — that powers hundreds of pre-built integrations across sourcing,
assessment, background-check, video-interviewing, HRIS, payroll, SSO, and e-signature
vendors. The platform recently acquired Ezra AI Labs to integrate conversational AI
into the hiring workflow and continues to invest in fraud detection and identity
verification through its Real Talent feature set.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/greenhouse-io/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/greenhouse-io/refs/heads/main/apis.yml)

## Scope

- **Position:** Producing
- **Access:** 3rd-Party

## Tags

- ATS
- Recruiting
- Hiring
- Talent Acquisition
- Enterprise SaaS
- Human Resources
- Onboarding

## Timestamps

- **Created:** 2026-05-25T00:00:00.000Z
- **Modified:** 2026-05-25

## APIs

### Greenhouse Harvest API

The Harvest API is Greenhouse's primary REST API and source of truth for recruiting data:
candidates, applications, jobs, openings, job posts, job stages, departments, offices,
users, offers, approval flows, scheduled interviews, scorecards, sources, tags, custom
fields, prospect pools, rejection reasons, and the per-candidate activity feed.
HTTP Basic with a granular per-permission API key; RFC-5988 Link pagination; rate limits
returned in X-RateLimit-Limit per 10s.

- **Human URL:** [https://developers.greenhouse.io/harvest.html](https://developers.greenhouse.io/harvest.html)
- **Base URL:** `https://harvest.greenhouse.io/v1`

#### Tags

- ATS
- Recruiting
- Candidates
- Jobs
- Interviews
- Offers

#### Properties

- [Documentation](https://developers.greenhouse.io/harvest.html)
- [OpenAPI](openapi/greenhouse-harvest-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/greenhouse-harvest-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/greenhouse-harvest-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/greenhouse-candidate-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/greenhouse-job-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON-LD](json-ld/greenhouse-io-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)
- [Authentication](https://developers.greenhouse.io/harvest.html#authentication)
- [Pagination](https://developers.greenhouse.io/harvest.html#pagination)
- [Rate Limits](https://developers.greenhouse.io/harvest.html#rate-limits)

### Greenhouse Job Board API

The Job Board API exposes a customer's public career site data — jobs, departments,
offices — and accepts application submissions via POST /jobs/{id}. GET endpoints are
unauthenticated; POST endpoints accept multipart/form-data or JSON. Used to power
customer-owned career pages and third-party job-board syndication.

- **Human URL:** [https://developers.greenhouse.io/job-board.html](https://developers.greenhouse.io/job-board.html)
- **Base URL:** `https://boards-api.greenhouse.io/v1/boards/{board_token}`

#### Tags

- JobBoard
- Careers
- Public
- Applications

#### Properties

- [Documentation](https://developers.greenhouse.io/job-board.html)
- [OpenAPI](openapi/greenhouse-job-board-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/greenhouse-job-board-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/greenhouse-job-board-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Authentication](https://developers.greenhouse.io/job-board.html)

### Greenhouse Audit Log API

The Audit Log API exposes important administrative events from the prior 30 days for
governance, compliance, and incident response. JWT bearer authentication (24h validity)
issued from the Harvest /auth/jwt_access_token endpoint. Pro-tier offering.

- **Human URL:** [https://developers.greenhouse.io/audit-log.html](https://developers.greenhouse.io/audit-log.html)
- **Base URL:** `https://auditlog.us.greenhouse.io`

#### Tags

- AuditLog
- Compliance
- Security
- Governance
- Enterprise

#### Properties

- [Documentation](https://developers.greenhouse.io/audit-log.html)
- [OpenAPI](openapi/greenhouse-audit-log-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/greenhouse-audit-log-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/greenhouse-audit-log-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Authentication](undefined)
- [Rate Limits](https://developers.greenhouse.io/audit-log.html)
- [Retention](undefined)

### Greenhouse Candidate Ingestion (Partner) API

The Candidate Ingestion (Partner) API lets sourcing partners create candidates and
prospects in a customer's Greenhouse account, list jobs visible to the integrated user,
read prospect pools, retrieve the current user, and generate branded tracking links.
Used by sourcing platforms, agencies, and recruitment marketing tools.

- **Human URL:** [https://developers.greenhouse.io/candidate-ingestion.html](https://developers.greenhouse.io/candidate-ingestion.html)
- **Base URL:** `https://api.greenhouse.io/v1/partner`

#### Tags

- Partner
- Ingestion
- Sourcing
- Candidates
- Prospects

#### Properties

- [Documentation](https://developers.greenhouse.io/candidate-ingestion.html)
- [OpenAPI](openapi/greenhouse-candidate-ingestion-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/greenhouse-candidate-ingestion-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/greenhouse-candidate-ingestion-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Authentication](https://developers.greenhouse.io/candidate-ingestion.html)

### Greenhouse Onboarding API

The Greenhouse Onboarding (GHO) API is a single GraphQL endpoint covering employees,
departments, locations, teams, custom fields, and mutations such as addPendingHire and
updateEmployeeProfile. Available on the Plus and Pro tiers; requires Super Admin to
generate or revoke keys.

- **Human URL:** [https://developers.greenhouse.io/gho.html](https://developers.greenhouse.io/gho.html)
- **Base URL:** `https://onboarding-api.greenhouse.io/graphql`

#### Tags

- Onboarding
- HRIS
- GraphQL
- Employees

#### Properties

- [Documentation](https://developers.greenhouse.io/gho.html)
- [OpenAPI](openapi/greenhouse-onboarding-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/greenhouse-onboarding-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/greenhouse-onboarding-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Authentication](undefined)
- [Rate Limits](https://developers.greenhouse.io/gho.html)

### Greenhouse Assessment Partner API

The Assessment Partner API defines the four endpoints — list_tests, send_test,
test_status, response_error — that assessment vendors implement so Greenhouse can
dispatch a test to a candidate and retrieve completion details. Partner-hosted rather
than Greenhouse-hosted; results retrieved via PATCH callback or hourly polling for
up to 8 weeks.

- **Human URL:** [https://developers.greenhouse.io/assessment.html](https://developers.greenhouse.io/assessment.html)

#### Tags

- Assessment
- Partner
- PreHire
- Integrations

#### Properties

- [Documentation](https://developers.greenhouse.io/assessment.html)
- [OpenAPI](openapi/greenhouse-assessment-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/greenhouse-assessment-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/greenhouse-assessment-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Authentication](undefined)

### Greenhouse Recruiting Webhooks

Event-driven webhooks from Greenhouse Recruiting. Greenhouse POSTs JSON to your HTTPS
endpoint on each event; payloads carry a Greenhouse-Event-ID header for idempotency and
HMAC SHA-256 signature verification.

- **Human URL:** [https://developers.greenhouse.io/webhooks.html](https://developers.greenhouse.io/webhooks.html)

#### Tags

- Webhooks
- Events
- Recruiting

#### Properties

- [Documentation](https://developers.greenhouse.io/webhooks.html)
- [Authentication](undefined)
- [Retry](undefined)
- [Events](undefined)
- [Postman Collection](collections/greenhouse-assessment-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/greenhouse-assessment-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/greenhouse-audit-log-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/greenhouse-audit-log-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/greenhouse-candidate-ingestion-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/greenhouse-candidate-ingestion-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/greenhouse-harvest-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/greenhouse-harvest-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/greenhouse-job-board-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/greenhouse-job-board-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/greenhouse-onboarding-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/greenhouse-onboarding-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Greenhouse Onboarding Webhooks

Event-driven webhooks from Greenhouse Onboarding (currently in beta and gated by
customer approval). Each event posts event_type, id, and payload to the customer's
HTTPS endpoint; signatures use HMAC SHA-256 with a shared secret.

- **Human URL:** [https://developers.greenhouse.io/onboarding_webhooks.html](https://developers.greenhouse.io/onboarding_webhooks.html)

#### Tags

- Webhooks
- Events
- Onboarding
- Beta

#### Properties

- [Documentation](https://developers.greenhouse.io/onboarding_webhooks.html)
- [Authentication](undefined)
- [Retry](undefined)
- [Events](undefined)
- [Postman Collection](collections/greenhouse-assessment-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/greenhouse-assessment-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/greenhouse-audit-log-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/greenhouse-audit-log-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/greenhouse-candidate-ingestion-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/greenhouse-candidate-ingestion-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/greenhouse-harvest-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/greenhouse-harvest-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/greenhouse-job-board-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/greenhouse-job-board-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/greenhouse-onboarding-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/greenhouse-onboarding-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Portal](https://www.greenhouse.com)
- [Documentation](https://developers.greenhouse.io)
- [Documentation](https://developers.greenhouse.io/harvest.html)
- [Documentation](https://developers.greenhouse.io/job-board.html)
- [Documentation](https://developers.greenhouse.io/webhooks.html)
- [Documentation](https://developers.greenhouse.io/onboarding_webhooks.html)
- [Documentation](https://developers.greenhouse.io/gho.html)
- [Documentation](https://developers.greenhouse.io/candidate-ingestion.html)
- [Documentation](https://developers.greenhouse.io/assessment.html)
- [Documentation](https://developers.greenhouse.io/audit-log.html)
- [Plans](https://www.greenhouse.com/pricing)
- [Plans](plans/greenhouse-io-plans-pricing.yml)
- [Rate Limits](rate-limits/greenhouse-io-rate-limits.yml)
- [Fin Ops](finops/greenhouse-io-finops.yml)
- [Status Page](https://status.greenhouse.io)
- [Privacy Policy](https://www.greenhouse.com/legal/privacy)
- [Terms of Service](https://www.greenhouse.com/legal/terms)
- [Trust Center](https://trust.greenhouse.com)
- [Support](https://support.greenhouse.io)
- [Customers](https://www.greenhouse.com/customers)
- [Blog](https://www.greenhouse.com/blog)
- [Integrations](https://integrations.greenhouse.com)
- [Careers](https://www.greenhouse.com/jobs)
- [LinkedIn](https://www.linkedin.com/company/greenhouse-software)
- [Twitter](https://x.com/Greenhouse)
- [GitHub Organization](https://github.com/grnhse)
- [GitHub Repository](https://github.com/grnhse/greenhouse-api-docs)
- [SDK](https://github.com/grnhse/greenhouse_io)
- [SDK](https://github.com/grnhse/greenhouse-tools-php)
- [SDK](https://github.com/grnhse/omniauth-greenhouse)
- [Features](undefined)

## Maintainers

**FN:** Kin Lane
**Email:** info@apievangelist.com
**URL:** https://apievangelist.com
