# Agentic Investment Research QA Kit — public preview

**Buyer:** Builders of multi-agent stock/market research workflows who need more reliable, auditable output.
**Promise:** Find missing evidence, stale data, consensus collapse, overconfidence, and unsafe trading-advice drift before using an AI-generated research note.
**Price hypothesis:** €39 intro / €79 standard
**Status:** available for early-access interest; no checkout is enabled and the full kit is not published here.

## What the private full kit is designed to include

- Agent role-contract template.
- Evidence/source freshness scorecard.
- Bull/bear symmetry checklist.
- Critic and CEO synthesis rubrics.
- No-financial-advice boundary template.
- JSON report fixtures.
- Offline QA scorer for completed research packets.
- Safe and deliberately unsafe validation examples.
- Buyer README and support boundaries.

## Public sample

Use the free [`Agentic Investment Research Output Checklist`](../free/agentic-investment-research-output-checklist.md) before trusting an ensemble report.

A representative QA result looks like:

```text
score: 28/28
verdict: pass_internal_research_note
dangerous trading-language findings: 0
boundary: process-quality score only; not investment advice or profitability evaluation
```

The private validator is also tested against an intentionally unsafe fixture containing direct trade instructions, certainty/profit claims, and automated-execution language. That fixture must fail.

## What this product does not do

- No buy/sell/hold recommendations.
- No portfolio allocation or position sizing.
- No brokerage integration or automated order execution.
- No profitability, win-rate, or durable-edge claims.
- No evaluation of whether a security is a good investment.
- No personalized financial, legal, or tax advice.
- No intake of brokerage exports, account statements, API keys, personal financial data, or non-public company information.

## Safe validation question

Would a local tool that scores your own agent-generated research JSON for evidence quality, freshness, dissent, uncertainty, and unsafe advice drift save you time?

The safest public signal is a star or a generic GitHub issue. Do not include tickers you hold, positions, trades, account data, private research, credentials, or customer data.

## How to express interest

Open a **Purchase interest / early access** issue and select **Agentic Investment Research QA Kit**. Keep the use case generic and non-personal.
