---
name: Batch download of large historical extracts
description: Materialize a large Databento historical request into downloadable flat files with an asynchronous batch job.
api: openapi/databento-batch-api-openapi.yml
operations: [batchSubmitJob, batchListJobs, batchListFiles]
generated: '2026-07-22'
method: generated
---

# Batch download of large historical extracts

Use the Batch API instead of synchronous `timeseries.get_range` whenever the
cost pre-flight (`getRecordCount` / `getBillableSize` / `getCost`) shows a
large result set.

1. **Authenticate** with HTTP Basic (`db-` API key as username, empty
   password).
2. **Submit** the job with `batchSubmitJob` — same selector parameters as a
   timeseries query (dataset, symbols, schema, start, end) plus output
   options: encoding (dbn/csv/json), compression, and split by day, symbol,
   or size. Submission is **not idempotent**: resubmitting creates a second
   billable job, so keep the returned `job_id`.
3. **Poll** `batchListJobs` until your `job_id` reaches the done state.
   Poll politely (seconds-to-minutes intervals) — jobs materialize
   asynchronously.
4. **Download** via `batchListFiles?job_id=` which returns each generated
   file with HTTPS and FTP URIs. Files remain re-downloadable for **30 days**
   at no extra cost — re-list and re-download rather than resubmitting the
   job.
5. **Errors** follow the `{"detail": ...}` envelope (401 bad credentials,
   422 invalid selector parameters).
