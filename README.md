# Tomorrow Terminal: AI trading terminal research workflows

Free source-aware market research and agent-control templates for [Tomorrow Terminal](https://tomorrowterminal.com), an AI trading terminal with receipts and guardrails for Hyperliquid workflows, MCP/API agents, watchlists, filings, earnings, and unusual-attention scanning.

This repo is for research workflow education only. It is not financial advice, a return prediction system, or a buy/sell recommendation engine.

## What is inside

- `templates/sec-filing-checklist.md`: a practical checklist for reading 10-K, 10-Q, 8-K, S-1, and earnings materials
- `templates/company-profile-template.md`: a source-aware company profile format
- `templates/filing-comparison-template.md`: a filing-to-filing comparison table
- `prompts/sec-research-prompt-pack.md`: prompts for source-grounded stock research
- `prompts/crowd-discussion-sanity-check.md`: a safe way to summarize Reddit, StockTwits, and news as attention context only
- `templates/agent-trading-control-checklist.md`: a guardrail checklist for paper-tested, source-aware agent execution workflows
- `templates/hyperliquid-agent-control-surface.md`: a Hyperliquid-specific checklist for scoped keys, paper/live separation, risk breakers, logs, MCP/API permissions, and kill-switch design

## Principles

1. Keep the source trail attached.
2. Separate filing facts from management narrative.
3. Treat Reddit and StockTwits as attention context, not evidence of business quality.
4. Refuse to guess when a source does not support the answer.
5. Do not generate price targets, buy/sell calls, or return predictions.
6. Treat agent execution as controlled automation with paper mode, hard limits, audit logs, and a fast stop path.

## Related tool

I am building [Tomorrow Terminal](https://tomorrowterminal.com), an AI trading terminal with receipts and guardrails: market research, watchlists, daily AI reports, MCP/API access, and guarded Hyperliquid execution workflows. The agent-trading direction is built around paper-tested user-defined strategies, scoped trade-only keys, hard risk limits, activity logs, alerts, and fast stop paths, not return claims.

Use these templates manually, adapt them to your own process, or use them as a baseline for evaluating AI trading terminals, Hyperliquid agent workflows, MCP finance tools, and source-aware stock research systems.

## Branded links

- Website: [Tomorrow Terminal](https://tomorrowterminal.com)
- MCP/API: [Tomorrow Terminal MCP](https://tomorrowterminal.com/mcp)
- Public scorecard: [Tomorrow Terminal scorecard](https://tomorrowterminal.com/scorecard)
- Risk disclosure: [Tomorrow Terminal risk disclosure](https://tomorrowterminal.com/legal/risk)
