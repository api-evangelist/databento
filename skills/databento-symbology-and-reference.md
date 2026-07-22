---
name: Resolve symbology and enrich with reference data
description: Map tickers to Databento instrument IDs and join security master, corporate actions, and adjustment factors.
api: openapi/databento-symbology-api-openapi.yml, openapi/databento-reference-api-openapi.yml
operations: [symbologyResolve, securityMasterGetRange, securityMasterGetLast, corporateActionsGetRange, adjustmentFactorsGetRange]
generated: '2026-07-22'
method: generated
---

# Resolve symbology and enrich with reference data

1. **Authenticate** with HTTP Basic (`db-` API key as username, empty
   password).
2. **Resolve symbols** with `symbologyResolve`: pass dataset, the input
   symbols, `stype_in` (the system they are in: raw_symbol, parent,
   continuous) and `stype_out` (usually instrument_id), plus a start/end date
   range — mappings are date-dependent (contracts roll, tickers change).
   Use the resolved `instrument_id`s consistently across historical and live
   queries.
3. **Security master**: `securityMasterGetRange` returns instrument
   definitions and identifiers over a date range; `securityMasterGetLast`
   returns the latest snapshot.
4. **Corporate actions**: `corporateActionsGetRange` returns splits,
   dividends, symbol changes and other events for the symbols/range —
   essential when comparing prices across event dates.
5. **Back-adjusted series**: `adjustmentFactorsGetRange` returns the factors
   to apply to raw prices to build split/dividend-adjusted series.
6. **Conventions**: date ranges are ISO 8601; errors use the
   `{"detail": ...}` envelope; there is no pagination — bound requests by
   date range and symbol list.
