# Free EF Core Generated SQL Review Checklist

A short local-only checklist for teams who are about to discuss EF Core performance, query-shape, or migration-risk problems.

Use this before proposing an index, LINQ rewrite, migration change, or production fix.

## Boundary first

Do **not** paste private evidence into GitHub issues, chat, email, or public tools.

Keep these local:

- customer data;
- source code;
- raw SQL;
- schemas;
- logs;
- connection strings;
- credentials;
- IP addresses;
- infrastructure topology;
- production exports.

The goal is to collect enough redacted context for your own team to make a safer next decision.

## 1. Capture environment context

Record:

- application/runtime name, if shareable internally;
- EF Core version;
- provider name and version;
- database engine and version;
- whether Query Store / runtime stats are available;
- whether the evidence is from local, staging, or production diagnostics.

Good version values look like:

```text
EF Core: 8.0.7
Provider: Microsoft.EntityFrameworkCore.SqlServer 8.0.7
Database: Azure SQL / SQL Server 2022
```

Avoid vague values like:

```text
latest
unknown
see ticket 7
abc1def
```

## 2. Capture generated SQL locally

For the query being discussed, capture the generated SQL shape locally with EF Core tooling such as `ToQueryString()` where appropriate.

Record:

- the redacted generated SQL shape;
- the LINQ query intent in plain language;
- whether the query uses `Include`, projection, tracking/no-tracking, pagination, grouping, or split queries;
- any query tag used internally.

Do not publish raw SQL if it exposes table names, customer identifiers, business logic, tenant IDs, or schema details.

## 3. Check query-shape symptoms

Look for patterns such as:

- very wide result sets caused by unnecessary `Include` chains;
- missing projection for read-only screens/API responses;
- accidental client-side filtering or materialization;
- unbounded result sets;
- pagination after materialization;
- repeated query execution in loops;
- split vs single query tradeoffs;
- tracking enabled for read-only paths;
- grouping/aggregation that translates differently than expected.

This does not prove the fix. It narrows the review.

## 4. Add runtime evidence when available

If safe and available internally, connect the generated SQL shape to runtime evidence:

- Query Store query id;
- duration / CPU / logical reads;
- execution count;
- time window;
- parameter-sensitivity notes;
- plan regression notes;
- deployment or data-volume change timing.

If Query Store is not available, say that explicitly. Do not invent it.

## 5. Review migration risk separately

For pending migrations, record:

- table size / row-count band;
- nullable vs non-nullable column changes;
- default constraints;
- backfill ordering;
- index creation/drop impact;
- lock/blocking risk;
- rollback boundary;
- whether the migration can be split safely.

Do not treat a migration tag alone as evidence. Capture the actual risk shape.

## 6. Separate evidence from action

Before production change, write down:

- what evidence was observed;
- what is assumed;
- what local/staging proof is still missing;
- what production risk exists;
- what rollback or observation step is planned.

A useful internal review conclusion sounds like:

```text
We have generated SQL evidence and runtime correlation for this read path. The next safe step is to test a projection rewrite locally/staging and compare generated SQL plus Query Store reads before proposing an index or production deployment.
```

Not:

```text
EF is slow; add an index.
```

## Optional paid kit

The paid EF Core Performance Review Pack packages this workflow as a local ZIP with:

- buyer quickstart;
- offline evidence scorer;
- generated SQL evidence table;
- Query Store/runtime correlation guidance;
- migration-risk snippets;
- report template;
- scoring rubric;
- checksum verification.

The public paid checkout is currently withdrawn after zero-payment validation. This free checklist remains available as the low-friction entry point while the lane is parked or repositioned.

Expected ZIP SHA-256:

```text
c960d02633160031b4ff71faa0277c31dec53cc5717e53438cf069c57764088f
```

Use GitHub issues only for generic product-scope feedback. Do not include private evidence.
