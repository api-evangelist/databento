---
name: Cost-aware historical data pull
description: Discover a dataset, size and price a query, then stream historical market data from Databento without surprise spend.
api: openapi/databento-metadata-api-openapi.yml, openapi/databento-timeseries-api-openapi.yml
operations: [listDatasets, listSchemas, getDatasetRange, getRecordCount, getBillableSize, getCost, timeseriesGetRange]
generated: '2026-07-22'
method: generated
---

# Cost-aware historical data pull

Databento bills historical usage **per byte streamed** — always pre-flight the
cost before pulling data.

1. **Authenticate** every request with HTTP Basic: your `db-` prefixed API key
   as the username, empty password (`curl -u db-XXXX:`).
2. **Discover** the dataset: `listDatasets` for available datasets,
   `listSchemas?dataset=` for the record types it supports (mbo, mbp-1,
   mbp-10, trades, ohlcv-1s..1d, statistics, definition), and
   `getDatasetRange?dataset=` for its available start/end dates. Stay inside
   that range.
3. **Pre-flight the query** with the same parameters you will pass to the
   timeseries call: `getRecordCount`, `getBillableSize`, and `getCost` all
   accept dataset/symbols/schema/start/end. If the dollar cost is above your
   budget, narrow symbols, schema, or the time range.
4. **Pull the data** with `timeseriesGetRange` (dataset, symbols, schema,
   start, end, optional limit; encoding dbn|csv|json, compression zstd).
   Timestamps in records are nanosecond UNIX epoch UTC; range parameters
   accept ISO 8601.
5. **Errors**: a `401 {"detail":"Not authenticated"}` means the Basic
   credentials are wrong; `422` is a FastAPI validation error listing the bad
   parameter in `detail[].loc`. There is no pagination — bound queries with
   start/end/limit, and if the pre-flight shows a very large result, switch to
   the Batch skill instead.
