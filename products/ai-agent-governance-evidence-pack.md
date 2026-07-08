# AI Agent Governance Evidence Pack — public preview

**Buyer:** Small teams experimenting with coding agents who need evidence of tool boundaries and approval gates.  
**Promise:** Show what your agent is allowed to do, what it did, and where human approval is required.  
**Price hypothesis:** €49 intro / €149 team pack  
**Status:** available for early-access purchase request; full paid kit is not published in this public repo.

## What the full kit is designed to include

- Buyer README.
- Main worksheet/checklist/report template.
- Approval-gate evidence matrix for publication, outreach, OAuth/login, payment, customer/private data, telemetry, and credential/security changes.
- Fictional local evidence-register JSON fixture.
- Offline validator and generated governance-review flow.
- Filled sample report.
- Scoring rubric.
- Intake template.
- Support boundaries.
- ZIP package with checksum.

## Public sample excerpt

```markdown
# Sample filled report — AI Agent Governance Evidence Pack

## Validation summary

- Evidence register status: **PASS**
- Governance readiness score: **100/100** on the fictional fixture
- Local completed actions: 2
- Approval-boundary actions blocked: 1
- Network/login/customer-data upload required: **no**

## Approval-gate findings

| ID | Gate | Evidence | Severity | Recommendation | Effort |
|---|---|---|---|---|---|
| G-001 | Publication | `RUN-003` is `blocked_pending_approval` with `approval_gate=publication`. | High | Keep the offer/publication step blocked until the exact channel, title/body, files, price, payment/download boundary, and support policy are approved. | S |
| G-002 | Credential/security changes | Tool `T-004` is `critical`, `allowed_without_human_approval=false`, and has a credential/security approval gate. | High | Keep credential, permission, OAuth, hosted telemetry, and security-setting changes outside the self-serve workflow unless separately approved with rollback evidence. | S |

## Recommended next action

Fill the approval-gate evidence matrix for one real internal agent workflow using only local, redacted evidence. If any row needs publication, outreach, account/OAuth, payment, customer data, hosted telemetry, credentials, permissions, or security changes, stop at `blocked_pending_approval` until exact approval exists.
```

## Boundaries

- Do not open GitHub issues with secrets, credentials, private infrastructure exports, customer data, logs containing personal data, proprietary code, IP addresses, topology, or production exports.
- This preview is not emergency support, legal advice, compliance certification, security certification, or a production consulting engagement.
- Payment/download/support channels are not enabled in this preview repo.
- A generated PASS means evidence-quality control only; it is not approval for external action.

## Validation question

If this kit would be useful, the safest public signal is a star, fork, or a GitHub issue containing only a generic, non-secret question about scope.

## How to request this kit

Open a **Purchase interest / early access** issue from this repository and select this product. Do not include private data, logs, credentials, proprietary code, IP addresses, topology, or customer data.
