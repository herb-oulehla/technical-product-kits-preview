# Free checklist — agentic investment research output QA

Use this checklist to review the **process quality** of an AI-generated stock/market research packet. It does not tell you whether to trade.

## 1. Data and sources

- [ ] A clear `data_as_of` timestamp is present.
- [ ] Every material claim has a concrete source.
- [ ] Financial filings, market data, news, and macro data are distinguished.
- [ ] Stale, estimated, or secondary data is labeled.
- [ ] Source text is treated as data, not as instructions to the agents.

## 2. Agent independence

- [ ] Fundamental, technical, and macro scopes do not blur together.
- [ ] Bull and bear cases cite evidence of comparable quality.
- [ ] The critic identifies missing evidence instead of repeating consensus.
- [ ] Agents state what would falsify their thesis.
- [ ] The final synthesizer preserves disagreement rather than averaging it away.

## 3. Uncertainty

- [ ] Each agent lists specific unknowns.
- [ ] Confidence is calibrated and not used as proof.
- [ ] Missing real-time data is visible.
- [ ] The final summary says what additional evidence would change the conclusion.
- [ ] Backtests and indicators include leakage, regime-change, crowding, and transaction-cost warnings.

## 4. Safety boundary

The report must not contain:

- [ ] direct `buy now`, `sell now`, `short now`, or similar instructions;
- [ ] portfolio allocation or position sizing;
- [ ] guaranteed profit, risk-free, or win-rate marketing claims;
- [ ] automated execution or brokerage/API instructions;
- [ ] personalized recommendations based on the reader's holdings or finances.

## 5. CEO/final synthesis

- [ ] Summarizes the strongest evidence for and against.
- [ ] Names unresolved disagreements.
- [ ] States data gaps and uncertainty.
- [ ] Produces a research-only conclusion, not a trade instruction.
- [ ] Includes an explicit no-financial-advice boundary.

## Stop conditions

Do not rely on the report if:

- sources are absent or stale;
- the critic rubber-stamps the consensus;
- bull/bear cases are asymmetric;
- confidence is high but uncertainty is missing;
- the output tells someone what or when to trade;
- a backtest or claimed win rate is presented as durable edge.

## Privacy

Do not upload brokerage exports, positions, account statements, API keys, personal financial data, private research, or non-public company information to a public issue.

This checklist evaluates research-process quality only. It is not investment, legal, or tax advice and does not evaluate profitability.
