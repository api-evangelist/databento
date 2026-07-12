# Databento (databento)

Databento is a market data platform that delivers historical and live financial market data through a single, normalized API. It covers equities, futures, options, and other asset classes across major venues, with full order book depth (MBO / MBP), trades, OHLCV bars, statistics, and reference data. Historical data is served over a **REST HTTP API** (`hist.databento.com`) billed pay-as-you-go per byte streamed, while live data is delivered over a **low-latency raw TCP binary protocol** using Databento Binary Encoding (DBN). Official Python, C++, and Rust client libraries wrap both surfaces, and a Reference API provides security master, corporate actions, and adjustment factor data.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/databento/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/databento/refs/heads/main/apis.yml)

## Access Model and Transports

Databento is honest to model as two distinct transports:

- **Historical + Reference — REST over HTTPS.** Base URL `https://hist.databento.com/v0`. Endpoints use dotted method names (e.g. `GET /v0/timeseries.get_range`, `GET /v0/metadata.get_cost`, `POST /v0/symbology.resolve`, `POST /v0/batch.submit_job`). Authentication is **HTTP Basic auth** with your API key (prefixed `db-`) as the username and an empty password. `timeseries.get_range` returns an HTTP *streaming response* — the body streams records as they are produced — but it is still a standard request/response HTTP call, not a WebSocket and not Server-Sent Events.
- **Live — raw TCP binary (DBN).** Real-time market data is delivered over a low-latency **raw TCP binary streaming protocol** carrying Databento Binary Encoding records, the same normalized schemas as historical. Live sessions authenticate with a **CRAM challenge-response** handshake using the API key, connect to per-dataset gateway hosts, then subscribe to symbols and schemas. This is **not a documented public WebSocket** and **not SSE**; it is intended to be consumed through the official client libraries and has no OpenAPI description.

Data is returned in DBN (compact zero-copy binary), CSV, or JSON. Billing is per **uncompressed binary byte** streamed, so the metadata endpoints let you pre-compute record count, billable size, and dollar cost before running a query.

## Tags

- Market Data
- Financial Data
- Reference Data
- Historical Market Data
- Trading

## Timestamps

- **Created:** 2026-07-11
- **Modified:** 2026-07-11

## APIs

### Databento Historical Timeseries API

Streams historical market data over HTTP for a requested date/time range. A single request selects a dataset, one or more symbols, a schema (MBO full order book, MBP-1 / MBP-10, trades, OHLCV bars, statistics, and more), and a time range, and returns normalized records in DBN, CSV, or JSON. Billed per byte streamed. Ideal for backtesting, research, and reference/tick data retrieval.

- **Human URL:** [https://databento.com/docs/api-reference-historical/timeseries/timeseries-get-range](https://databento.com/docs/api-reference-historical/timeseries/timeseries-get-range)
- **Base URL:** `https://hist.databento.com/v0`

#### Tags

- Historical Market Data
- Market Data
- Timeseries
- Trading
- Financial Data

#### Properties

- [Documentation](https://databento.com/docs/api-reference-historical)
- [API Reference](https://databento.com/docs/api-reference-historical/timeseries/timeseries-get-range)
- [OpenAPI](openapi/databento-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/databento.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/databento.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Databento Metadata API

Discovery and cost-estimation endpoints for the historical catalog. List publishers, datasets, schemas, and fields; look up per-dataset date ranges and data-quality conditions; and pre-compute the record count, billable size, and dollar cost of a query before you run it. Essential for planning research and controlling spend on financial and reference data.

- **Human URL:** [https://databento.com/docs/api-reference-historical/metadata/metadata-list-datasets](https://databento.com/docs/api-reference-historical/metadata/metadata-list-datasets)
- **Base URL:** `https://hist.databento.com/v0`

#### Tags

- Metadata
- Reference Data
- Market Data
- Datasets
- Financial Data

#### Properties

- [Documentation](https://databento.com/docs/api-reference-historical)
- [API Reference](https://databento.com/docs/api-reference-historical/metadata/metadata-list-datasets)
- [OpenAPI](openapi/databento-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/databento.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/databento.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Databento Symbology API

Resolves symbols between Databento's symbology systems — raw symbol, instrument ID, parent, and continuous contract — for a dataset over a date range. Lets consumers map tickers, exchange instrument IDs, and continuous futures references onto the identifiers used across the historical and live data schemas.

- **Human URL:** [https://databento.com/docs/api-reference-historical/basics/symbology](https://databento.com/docs/api-reference-historical/basics/symbology)
- **Base URL:** `https://hist.databento.com/v0`

#### Tags

- Symbology
- Reference Data
- Symbols
- Market Data
- Financial Data

#### Properties

- [Documentation](https://databento.com/docs/api-reference-historical/basics/symbology)
- [OpenAPI](openapi/databento-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/databento.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/databento.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Databento Batch API

Submits asynchronous batch jobs that materialize large historical requests into downloadable flat files (DBN, CSV, or JSON), optionally split by day, symbol, or size. Submit a job, list your jobs and their state, and list the generated files with HTTPS and FTP download URIs. Files remain re-downloadable for 30 days at no extra cost.

- **Human URL:** [https://databento.com/docs/api-reference-historical/batch/batch-submit-job](https://databento.com/docs/api-reference-historical/batch/batch-submit-job)
- **Base URL:** `https://hist.databento.com/v0`

#### Tags

- Batch
- Flat Files
- Historical Market Data
- Market Data
- Financial Data

#### Properties

- [Documentation](https://databento.com/docs/api-reference-historical/batch/batch-submit-job)
- [API Reference](https://databento.com/docs/api-reference-historical/batch/batch-submit-job)
- [OpenAPI](openapi/databento-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/databento.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/databento.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Databento Live Streaming API

Low-latency live market data delivered over a **raw TCP binary streaming protocol** using Databento Binary Encoding (DBN) — the same normalized schemas as the historical API. Sessions authenticate with a CRAM challenge-response handshake using your API key, then subscribe to symbols and schemas per dataset gateway. This is a binary TCP protocol, **not a documented public WebSocket**; it is consumed via the official Python, C++, and Rust clients and has no OpenAPI description.

- **Human URL:** [https://databento.com/docs/api-reference-live](https://databento.com/docs/api-reference-live)
- **Base URL:** `tcp://GLBX.MDP3.lsg.databento.com` (per-dataset gateway; illustrative)

#### Tags

- Live Market Data
- Streaming
- Market Data
- Trading
- Low Latency

#### Properties

- [Documentation](https://databento.com/docs/api-reference-live)
- [Authentication](https://databento.com/docs/api-reference-live/basics/authentication)
- [Documentation](https://databento.com/docs/standards-and-conventions/databento-binary-encoding)

### Databento Reference API

Reference and non-price data that complements the market data feeds — a security master (instrument definitions and identifiers), corporate actions (splits, dividends, symbol changes, and other events), and adjustment factors for building back-adjusted price series. Served over the same REST HTTP surface as the historical API.

- **Human URL:** [https://databento.com/docs/api-reference-reference](https://databento.com/docs/api-reference-reference)
- **Base URL:** `https://hist.databento.com/v0`

#### Tags

- Reference Data
- Corporate Actions
- Security Master
- Financial Data
- Market Data

#### Properties

- [Documentation](https://databento.com/docs/api-reference-reference)
- [API Reference](https://databento.com/docs/api-reference-reference/basics/overview)
- [OpenAPI](openapi/databento-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

## Common Properties

- [GitHub Organization](https://github.com/databento)
- [LinkedIn](https://www.linkedin.com/company/databento)
- [Website](https://databento.com)
- [Documentation](https://databento.com/docs)
- [Plans](plans/databento-plans-pricing.yml)
- [Rate Limits](rate-limits/databento-rate-limits.yml)
- [Fin Ops](finops/databento-finops.yml)
- [Blog](https://databento.com/blog)

## Review

- **Question:** Does Databento expose a documented public WebSocket API?
- **Answer:** No. The Historical and Reference APIs are request/response REST over HTTPS; the Live API is a raw TCP binary DBN protocol with CRAM authentication — not a WebSocket and not Server-Sent Events. See [review.yml](review.yml).

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
