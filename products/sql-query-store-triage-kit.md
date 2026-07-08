# SQL Server Query Store Triage Kit — public preview

**Buyer:** Small .NET/SQL teams with slow Azure SQL or SQL Server queries and no DBA on standby.  
**Promise:** Find the top workload-backed query problems in 30 minutes without blindly applying missing-index recommendations.  
**Price hypothesis:** €49 intro / €99 standard  
**Status:** available for early-access purchase request; full paid kit is not published in this public repo.

## What the full kit is designed to include

- Buyer README.
- Buyer quickstart with local evidence prerequisites, scorer command, expected PASS output, and safety boundaries.
- Main worksheet/checklist/report template.
- Filled sample report.
- Scoring rubric.
- Intake template.
- Support boundaries.
- Read-only SQL snippet files for Query Store workload triage and index/write-risk checks.
- Offline sanitized-evidence scorer for Query Store/index evidence completeness.
- Candidate index decision record template that turns noisy DMV signals into `reject` / `park` / `collect_more_evidence` / `propose_scoped_change` decisions.
- Sanitized JSON fixture showing the expected local evidence shape.
- ZIP package with checksum.

## Current private-kit hardening

The private source-of-truth kit now includes a concrete `snippets/` section with:

- Query Store state and capture-setting checks.
- Top workload-backed statements by logical reads, CPU, writes, duration, and executions.
- Multiple-plan / duration-variance candidates for deeper execution-plan inspection.
- Missing-index signal review that explicitly treats recommendations as clues, not implementation scripts.
- Existing-index inventory, foreign-key supporting-index gaps, and write-pressure checks.
- A local scorer that rejects customer-data scope and blind index creation before a buyer treats evidence as decision-ready.
- A candidate index decision record requiring Query Store evidence, overlap/write-risk review, rehearsal/rollback notes, and explicit owner approval before any SQL/index/query change.
- A buyer quickstart that shows the offline scorer command and the minimum redacted evidence packet needed before discussing any query/index change.

These snippets and the scorer are local-only. They still require the buyer to run diagnostics against their own database and redact outputs. Do not paste raw output into GitHub issues if it contains query text, schema names, customer data, proprietary code, IP addresses, or topology.

## Public sample excerpt

```markdown
# Sample filled report — SQL Server Query Store Triage Kit

## Context

Example buyer: fictional small team / household operator.  
Category: B2B developer/database operations.  
Goal: Find the top workload-backed query problems in 30 minutes without blindly applying missing-index recommendations.

## Summary

The review found one workload-backed Query Store hotspot, one missing-index signal that needs overlap/write-risk review, and one low-priority foreign-key indexing follow-up. No production change should be made from DMV output alone.

## Findings

| ID | Finding | Evidence | Severity | Recommendation | Effort |
|---|---|---|---|---|---|
| SQL-QS-001 | Redacted query is a top logical-read consumer. | Query Store runtime export with query text redacted. | High | Capture actual execution plan and compare a query-shape/index candidate before proposing changes. | M |
| SQL-QS-002 | Missing-index DMV signal overlaps an existing composite index. | Missing-index export + existing-index inventory + write-pressure check. | Medium | Treat as a decision-table candidate; require key-order/include/write-cost review. | M |
| SQL-QS-003 | One FK path lacks same-order supporting index evidence. | FK support check found a gap, but no matching workload signal yet. | Low | Park as follow-up unless workload evidence points to this table path. | S |

## Candidate decision record excerpt

| Candidate | Decision | Why | Required approval before action |
|---|---|---|---|
| SQL-QS-002 missing-index overlap | `collect_more_evidence` | Query Store hotspot and missing-index clue exist, but existing composite-index overlap and write pressure need a scoped rehearsal. | Database owner approval, rollback path, and post-change Query Store monitoring plan. |

## Recommended next action

Run the offline scorer against sanitized local evidence. If it does not return `PASS`, collect better Query Store/runtime/index evidence before discussing any SQL/index change.

## Not included

No private data, credentials, remote access, emergency support, or legal/compliance certification.
```

## Boundaries

- Do not open GitHub issues with secrets, credentials, private infrastructure exports, customer data, logs containing personal data, or proprietary code.
- This preview is not emergency support, legal advice, compliance certification, or a production consulting engagement.
- Payment/download/support channels are not enabled in this preview repo.

## Validation question

If this kit would be useful, the safest public signal is a star, fork, or a GitHub issue containing only a generic, non-secret question about scope.

## How to request this kit

Open a **Purchase interest / early access** issue from this repository and select this product. Do not include private data, logs, credentials, proprietary code, IP addresses, topology, or customer data.
