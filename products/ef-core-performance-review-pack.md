# EF Core Performance Review Pack — public preview

**Buyer:** Teams shipping EF Core apps that suspect N+1 queries, bad LINQ translation, or unsafe migrations.  
**Promise:** Turn vague EF Core performance concerns into generated SQL evidence and a prioritized fix list.  
**Price hypothesis:** €39 intro / €79 standard  
**Status:** available for early-access purchase request; full paid kit is not published in this public repo.

## What the full kit is designed to include

- Buyer README.
- Main worksheet/checklist/report template.
- Filled sample report.
- Scoring rubric.
- Intake template.
- Local generated-SQL evidence table.
- Read-only EF Core/SQL snippets for `ToQueryString()`, Query Store correlation, and migration preflight.
- Offline scorer for sanitized EF Core review evidence.
- Support boundaries.
- ZIP package with checksum.

## Public sample excerpt

```markdown
# Sample filled report — EF Core Performance Review Pack

## Context

Example buyer: fictional B2B SaaS team using EF Core with Azure SQL.  
Scope: one slow read path and one pending migration.  
Evidence used: generated SQL captured locally with `ToQueryString()`, Query Store runtime summary, migration metadata preflight.  
Explicitly out of scope: production changes, customer data, proprietary query text, emergency DBA support.

## Summary

The review found one high-confidence query-shape issue and one migration-ordering risk. The recommended next action is local proof first: rewrite the read query as a projection, compare generated SQL, then verify Query Store reads/duration before proposing any index or production deployment.

## Findings

| ID | Finding | Evidence | Severity | Recommendation | Effort |
|---|---|---|---|---|---|
| EF-001 | Recent-orders page generated an Include-heavy SQL shape wider than the screen needs. | `ToQueryString()` capture with provider/version, Query Store top logical-read entry, redacted query tag. | High | Test an explicit projection and compare generated SQL + Query Store reads before adding indexes. | M |
| EF-002 | Pending NOT NULL column migration touches a non-empty table and has no recorded backfill/default ordering decision. | Row-count and column/default metadata; migration script review. | Medium | Use nullable-add → backfill → alter-not-null, or document a safe default/rollback boundary before deployment. | M |

## Not included

No private data, credentials, remote access, production changes, emergency support, legal/compliance certification, or guarantee that a specific index/query rewrite will fix performance.
```

## Boundaries

- Do not open GitHub issues with secrets, credentials, private infrastructure exports, customer data, logs containing personal data, proprietary code, IP addresses, topology, raw query text, or schema details.
- This preview is not emergency support, legal advice, compliance certification, or a production consulting engagement.
- Payment/download/support channels are not enabled in this preview repo.

## Validation question

If this kit would be useful, the safest public signal is a star, fork, or a GitHub issue containing only a generic, non-secret question about scope.

## How to request this kit

Open a **Purchase interest / early access** issue from this repository and select this product. Do not include private data, logs, credentials, proprietary code, IP addresses, topology, query text, schema details, or customer data.
