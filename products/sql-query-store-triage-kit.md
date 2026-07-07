# SQL Server Query Store Triage Kit — public preview

**Buyer:** Small .NET/SQL teams with slow Azure SQL or SQL Server queries and no DBA on standby.  
**Promise:** Find the top workload-backed query problems in 30 minutes without blindly applying missing-index recommendations.  
**Price hypothesis:** €49 intro / €99 standard  
**Status:** preview only; full paid kit not published here.

## What the full kit is designed to include

- Buyer README.
- Main worksheet/checklist/report template.
- Filled sample report.
- Scoring rubric.
- Intake template.
- Support boundaries.
- ZIP package with checksum.

## Public sample excerpt

```markdown
# Sample filled report — SQL Server Query Store Triage Kit

## Context

Example buyer: fictional small team / household operator.  
Category: B2B developer/database operations.  
Goal: Find the top workload-backed query problems in 30 minutes without blindly applying missing-index recommendations.

## Summary

The review found three likely sources of avoidable operational friction. None require external publication, credentials, or customer-data upload to evaluate.

## Findings

| ID | Finding | Evidence | Severity | Recommendation | Effort |
|---|---|---|---|---|---|
| F-001 | The current process lacks a clear evidence source. | No attached logs/export/screenshots in the worksheet. | Medium | Capture the minimum local evidence before deciding. | S |
| F-002 | The owner/action boundary is unclear. | Checklist item has no owner/due date. | Medium | Assign one owner and one review date. | S |
| F-003 | The recurring check is not scheduled. | No cadence in the follow-up section. | Low | Add a monthly or quarterly check depending on risk. | S |

## Recommended next action

Complete the evidence table and rerun the scoring rubric. If the score remains below 7/10, do not buy consulting or tooling yet — narrow the problem first.

## Not included

No private data, credentials, remote access, emergency support, or legal/compliance certification.
```

## Boundaries

- Do not open GitHub issues with secrets, credentials, private infrastructure exports, customer data, logs containing personal data, or proprietary code.
- This preview is not emergency support, legal advice, compliance certification, or a production consulting engagement.
- Payment/download/support channels are not enabled in this preview repo.

## Validation question

If this kit would be useful, the safest public signal is a star, fork, or a GitHub issue containing only a generic, non-secret question about scope.
