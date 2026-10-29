# Databento

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
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Databento is a market data platform that delivers historical and live financial market data through a single, normalized API. It covers equities, futures, options, and other asset classes across major venues, with full order book depth (MBO/MBP), trades, OHLCV bars, and reference data. Historical data is served over a REST HTTP API (hist.databento.com) with pay-as-you-go billing per byte streamed, while live data is delivered over a low-latency raw TCP binary protocol using Databento Binary Encoding (DBN). Official Python, C++, and Rust client libraries wrap both surfaces, and a Reference API provides security master, corporate actions, and adjustment factor data.

**Areas:** Market Data · Financial Data · Reference Data · Historical Market Data · Trading

## Databento on APIs.io

Everything profiled for Databento is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/databento/](https://apis.io/providers/databento/)** — or go straight to one of the APIs or properties below.

### APIs (24)

- [Databento Metadata API](https://apis.io/apis/databento/databento-metadata-api/) — Discovery and cost-estimation endpoints for the historical catalog. List publishers, datasets, schemas, and fields; look up per-dataset date ranges and…
- [Databento Symbology API](https://apis.io/apis/databento/databento-symbology-api/) — Resolves symbols between Databento's symbology systems - raw symbol, instrument ID, parent, and continuous contract - for a dataset over a date range. Lets…
- [Databento Batch API](https://apis.io/apis/databento/databento-batch-api/) — Submits asynchronous batch jobs that materialize large historical requests into downloadable flat files (DBN, CSV, or JSON), optionally split by day,…
- [Databento Live Streaming API](https://apis.io/apis/databento/databento-live-streaming-api/) — Low-latency live market data delivered over a raw TCP binary streaming protocol using Databento Binary Encoding (DBN) - the same normalized schemas as the…
- [Databento Reference API](https://apis.io/apis/databento/databento-reference-api/) — Reference and non-price data that complements the market data feeds - a security master (instrument definitions and identifiers), corporate actions (splits,…
- [Databento Adjustment Factors API](https://apis.io/apis/databento/databento-adjustment-factors-api/) — The adjustment_factors API from Databento — 1 operation(s) for adjustment_factors.
- [Databento Analytics API](https://apis.io/apis/databento/databento-analytics-api/) — The analytics API from Databento — 1 operation(s) for analytics.
- [Databento Auth API](https://apis.io/apis/databento/databento-auth-api/) — The auth API from Databento — 12 operation(s) for auth.
- [Databento Billing API](https://apis.io/apis/databento/databento-billing-api/) — The billing API from Databento — 14 operation(s) for billing.
- [Databento Corporate Actions API](https://apis.io/apis/databento/databento-corporate-actions-api/) — The corporate_actions API from Databento — 1 operation(s) for corporate_actions.
- [Databento OpenAPI Specification API](https://apis.io/apis/databento/databento-databento-openapi-specification-api/) — The Databento OpenAPI Specification API from Databento — 1 operation(s) for databento openapi specification.
- [Databento Dataset API](https://apis.io/apis/databento/databento-dataset-api/) — The dataset API from Databento — 17 operation(s) for dataset.
- [Databento Display API](https://apis.io/apis/databento/databento-display-api/) — The display API from Databento — 1 operation(s) for display.
- [Databento Docs API](https://apis.io/apis/databento/databento-docs-api/) — The docs API from Databento — 3 operation(s) for docs.
- [Databento Instrument API](https://apis.io/apis/databento/databento-instrument-api/) — The instrument API from Databento — 3 operation(s) for instrument.
- [Databento Latency API](https://apis.io/apis/databento/databento-latency-api/) — The latency API from Databento — 6 operation(s) for latency.
- [Databento Licensing API](https://apis.io/apis/databento/databento-licensing-api/) — The licensing API from Databento — 12 operation(s) for licensing.
- [Databento Log Post Param Vals API](https://apis.io/apis/databento/databento-log-post-param-vals-api/) — The log_post_param_vals API from Databento — 70 operation(s) for log_post_param_vals.
- [Databento Registration API](https://apis.io/apis/databento/databento-registration-api/) — The registration API from Databento — 9 operation(s) for registration.
- [Databento Security Master API](https://apis.io/apis/databento/databento-security-master-api/) — The security_master API from Databento — 2 operation(s) for security_master.
- [Databento Teams API](https://apis.io/apis/databento/databento-teams-api/) — The teams API from Databento — 11 operation(s) for teams.
- [Databento Usage API](https://apis.io/apis/databento/databento-usage-api/) — The usage API from Databento — 11 operation(s) for usage.
- [Databento Users API](https://apis.io/apis/databento/databento-users-api/) — The users API from Databento — 28 operation(s) for users.
- [Databento Time Series API](https://apis.io/apis/databento/databento-time-series-api/) — Stream historical records for a symbol set over a time range.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [databento](https://apis.io/servers/databento/databento/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Databento Agentic Access](https://apis.io/agentic-access/databento/databento-agentic-access/)

#### Collections (12)

Postman and Open Collection request collections.

- [Databento Historical and Reference API](https://apis.io/collections/databento/open-databento/)
- [Databento Historical and Reference Batch API](https://apis.io/collections/databento/open-databento-batch-api/)
- [Databento Historical and Reference Batch Metadata API](https://apis.io/collections/databento/open-databento-metadata-api/)
- [Databento OpenAPI specification](https://apis.io/collections/databento/open-databento-platform-openapi-official/)
- [Databento Historical and Batch Reference API](https://apis.io/collections/databento/open-databento-reference-api/)
- [Databento Historical and Reference Batch Symbology API](https://apis.io/collections/databento/open-databento-symbology-api/)
- [Databento Historical and Reference Batch Timeseries API](https://apis.io/collections/databento/open-databento-timeseries-api/)
- [Databento Historical and Reference Batch API](https://apis.io/collections/databento/postman-databento-batch-api/)
- [Databento Historical and Reference Batch Metadata API](https://apis.io/collections/databento/postman-databento-metadata-api/)
- [Databento Historical and Batch Reference API](https://apis.io/collections/databento/postman-databento-reference-api/)
- [Databento Historical and Reference Batch Symbology API](https://apis.io/collections/databento/postman-databento-symbology-api/)
- [Databento Historical and Reference Batch Timeseries API](https://apis.io/collections/databento/postman-databento-timeseries-api/)

#### Overlays (1)

OpenAPI overlays, including conversational phrasing for each operation.

- [Databento Platform Official Overlay](https://apis.io/overlays/databento/databento-platform-official-overlay/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Databento Authentication](https://apis.io/security/databento/databento-authentication/)
- [Databento Domain Security](https://apis.io/security/databento/databento-domain-security/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Databento Scopes](https://apis.io/scopes/databento/databento-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Databento Plans Pricing](https://apis.io/plans/databento/databento-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Databento Rate Limits](https://apis.io/rate-limits/databento/databento-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Databento Finops](https://apis.io/finops/databento/databento-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://databento.com)
- [Documentation](https://databento.com/docs)
- [Getting started](https://databento.com/docs/quickstart)
- [API reference](https://databento.com/docs/api-reference-historical)
- [Pricing](https://databento.com/pricing)
- [Sign up](https://databento.com/signup)
- [Support](https://databento.com/support)
- [Blog](https://databento.com/blog)
- [Terms of service](https://legal.databento.com/)
- [Privacy policy](https://legal.databento.com/)
- [GitHub](https://github.com/databento)
- [Status](https://status.databento.com)

## API Evangelist rating

**Kin Score 39.5** — developing · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 66.1 |
| Contract quality | 39.4 |
| Contract governance | 4.5 |
| Operational transparency | 55.3 |
| Developer ergonomics | 64.9 |
| Access clarity | 7.9 |

**Agent readiness 33.4** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | verified |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | verified |
| OpenAPI Examples | partial |
| Rate Limit Signal | derived (partial credit) |
| Event Surface Described | — |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | yes |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | — |
| Operation Distinctiveness | mostly |

**Regulatory alignment 30.6** — Securities & Market Data

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/databento/](https://apis.io/providers/databento/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Databento: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/databento/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
