# Greenhouse (greenhouse-io)

Greenhouse Software is an enterprise applicant tracking system (ATS) and end-to-end hiring platform spanning sourcing, structured interviewing, offer management, hiring decisions, and new-hire onboarding. Customers include DoorDash, Betterment, MLB, Coupang, HelloFresh, Trivago, and the NFL. The platform exposes a broad developer surface that powers hundreds of pre-built integrations across sourcing, assessment, background-check, video-interviewing, HRIS, payroll, SSO, and e-signature vendors.

**URL:** [Visit APIs.json](https://raw.githubusercontent.com/api-evangelist/greenhouse-io/refs/heads/main/apis.yml)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=company-api-evangelist&utm_content=repo)

## Tags

ATS, Recruiting, Hiring, Talent Acquisition, Enterprise SaaS, Human Resources, Onboarding

## Timestamps

- **Created:** 2026-05-25
- **Modified:** 2026-05-25

## Plans

| Plan | Audience | Notable Inclusions |
|---|---|---|
| Core | Establishing a consistent hiring process | Sourcing & CRM, structured interview kits, scheduling, SSO, Real Talent, Harvest API, Job Board API, Recruiting Webhooks |
| Plus | Multi-team / multi-brand orgs | Everything in Core, AI-powered report filters, BI Connector, Sourcing Automation, candidate texting, Onboarding API, Onboarding Webhooks (beta) |
| Pro | Enterprises requiring governance & auditability | Everything in Plus, unlimited CRM events, enterprise data config, Audit Log API, developer sandbox & sync, enterprise Real Talent |

Greenhouse pricing is custom-quoted; see [plans/greenhouse-io-plans-pricing.yml](plans/greenhouse-io-plans-pricing.yml).

## APIs

### Greenhouse Harvest API
Primary REST API for recruiting data — candidates, applications, jobs, openings, job posts, job stages, departments, offices, users, offers, approvals, scheduled interviews, scorecards, sources, tags, custom fields, prospect pools, rejection reasons, and the activity feed.

**Human URL:** [https://developers.greenhouse.io/harvest.html](https://developers.greenhouse.io/harvest.html)

- [Documentation](https://developers.greenhouse.io/harvest.html)
- [OpenAPI](openapi/greenhouse-harvest-api-openapi.yml)
- [JSON Schema — Candidate](json-schema/greenhouse-candidate-schema.json)
- [JSON Schema — Job](json-schema/greenhouse-job-schema.json)
- [JSON-LD](json-ld/greenhouse-io-context.jsonld)
- [Naftiko Capability — Candidates](capabilities/harvest-candidates.yaml)
- [Naftiko Capability — Applications](capabilities/harvest-applications.yaml)
- [Naftiko Capability — Jobs](capabilities/harvest-jobs.yaml)
- [Naftiko Capability — Interviews & Scorecards](capabilities/harvest-interviews-scorecards.yaml)
- [Naftiko Capability — Offers & Approvals](capabilities/harvest-offers-approvals.yaml)
- [Naftiko Capability — Organization](capabilities/harvest-organization.yaml)

### Greenhouse Job Board API
Public, unauthenticated reads of jobs / departments / offices for a customer's careers site; authenticated POST for application submission.

**Human URL:** [https://developers.greenhouse.io/job-board.html](https://developers.greenhouse.io/job-board.html)

- [Documentation](https://developers.greenhouse.io/job-board.html)
- [OpenAPI](openapi/greenhouse-job-board-api-openapi.yml)
- [Naftiko Capability — Job Board](capabilities/job-board-public.yaml)

### Greenhouse Audit Log API
30-day administrative audit trail for governance, compliance, and incident response. JWT bearer auth (24h) issued from Harvest. Pro-tier.

**Human URL:** [https://developers.greenhouse.io/audit-log.html](https://developers.greenhouse.io/audit-log.html)

- [Documentation](https://developers.greenhouse.io/audit-log.html)
- [OpenAPI](openapi/greenhouse-audit-log-api-openapi.yml)
- [Naftiko Capability — Audit Events](capabilities/audit-log-events.yaml)

### Greenhouse Candidate Ingestion (Partner) API
Sourcing-partner API for creating candidates and prospects in a customer's Greenhouse, listing visible jobs / prospect pools, and generating tracking links. OAuth 2.0 or Basic with On-Behalf-Of header.

**Human URL:** [https://developers.greenhouse.io/candidate-ingestion.html](https://developers.greenhouse.io/candidate-ingestion.html)

- [Documentation](https://developers.greenhouse.io/candidate-ingestion.html)
- [OpenAPI](openapi/greenhouse-candidate-ingestion-api-openapi.yml)
- [Naftiko Capability — Partner Ingestion](capabilities/partner-ingestion.yaml)

### Greenhouse Onboarding API
Single GraphQL endpoint for employees, departments, locations, teams, custom fields, and mutations (addPendingHire, updateEmployeeProfile, etc.). Rate-limited by request count and per-query complexity.

**Human URL:** [https://developers.greenhouse.io/gho.html](https://developers.greenhouse.io/gho.html)

- [Documentation](https://developers.greenhouse.io/gho.html)
- [OpenAPI](openapi/greenhouse-onboarding-api-openapi.yml)
- [Naftiko Capability — Onboarding GraphQL](capabilities/onboarding-graphql.yaml)

### Greenhouse Assessment Partner API
Partner-hosted contract — list_tests, send_test, test_status, response_error — that assessment vendors implement so Greenhouse can dispatch a test to a candidate and retrieve results. Polled hourly for up to 8 weeks.

**Human URL:** [https://developers.greenhouse.io/assessment.html](https://developers.greenhouse.io/assessment.html)

- [Documentation](https://developers.greenhouse.io/assessment.html)
- [OpenAPI](openapi/greenhouse-assessment-api-openapi.yml)

### Greenhouse Recruiting Webhooks
HMAC SHA-256 signed JSON pushes for application, candidate, interview, scorecard, offer, job, and org events. Up to 7 retries over 15 hours.

**Human URL:** [https://developers.greenhouse.io/webhooks.html](https://developers.greenhouse.io/webhooks.html)

### Greenhouse Onboarding Webhooks (Beta)
HMAC SHA-256 signed employee:updated events for the Onboarding product. Customer approval gated.

**Human URL:** [https://developers.greenhouse.io/onboarding_webhooks.html](https://developers.greenhouse.io/onboarding_webhooks.html)

## Composed Capabilities

- [Naftiko Capability — Hire Flow (Board → Harvest → Onboarding)](capabilities/hire-flow.yaml)

## Operations

- **Plans:** [plans/greenhouse-io-plans-pricing.yml](plans/greenhouse-io-plans-pricing.yml)
- **Rate Limits:** [rate-limits/greenhouse-io-rate-limits.yml](rate-limits/greenhouse-io-rate-limits.yml)
- **FinOps:** [finops/greenhouse-io-finops.yml](finops/greenhouse-io-finops.yml)

## Common

- **Portal:** [greenhouse.com](https://www.greenhouse.com)
- **Developer Center:** [developers.greenhouse.io](https://developers.greenhouse.io)
- **Integrations:** [integrations.greenhouse.com](https://integrations.greenhouse.com)
- **Status:** [status.greenhouse.io](https://status.greenhouse.io)
- **Trust Center:** [trust.greenhouse.com](https://trust.greenhouse.com)
- **GitHub:** [github.com/grnhse](https://github.com/grnhse)
- **Public SDKs:** [Ruby (greenhouse_io)](https://github.com/grnhse/greenhouse_io), [PHP Job Board Tools](https://github.com/grnhse/greenhouse-tools-php), [OmniAuth Greenhouse (Ruby)](https://github.com/grnhse/omniauth-greenhouse)

## Maintainer

- **Kin Lane** — [API Evangelist](https://apievangelist.com)
