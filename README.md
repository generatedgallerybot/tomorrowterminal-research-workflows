# Tomorrow Terminal research workflows

Free source-aware stock research templates for people who want cleaner first-pass company research.

This repo is for research workflow education only. It is not financial advice, a return prediction system, or a buy/sell recommendation engine.

## What is inside

- `templates/sec-filing-checklist.md`: a practical checklist for reading 10-K, 10-Q, 8-K, S-1, and earnings materials
- `templates/company-profile-template.md`: a source-aware company profile format
- `templates/filing-comparison-template.md`: a filing-to-filing comparison table
- `prompts/sec-research-prompt-pack.md`: prompts for source-grounded stock research
- `prompts/crowd-discussion-sanity-check.md`: a safe way to summarize Reddit, StockTwits, and news as attention context only
- `templates/agent-trading-control-checklist.md`: a guardrail checklist for paper-tested, source-aware agent execution workflows

## Principles

1. Keep the source trail attached.
2. Separate filing facts from management narrative.
3. Treat Reddit and StockTwits as attention context, not evidence of business quality.
4. Refuse to guess when a source does not support the answer.
5. Do not generate price targets, buy/sell calls, or return predictions.
6. Treat agent execution as controlled automation with paper mode, hard limits, audit logs, and a fast stop path.

## Related tool

I am building [Tomorrow Terminal](https://tomorrowterminal.com), an AI stock research workspace that combines filings, financials, market data, news, Reddit, and StockTwits into source-aware company profiles and watchlists. The agent-trading direction is built around paper-tested user-defined strategies, trade-only keys, hard risk limits, and audit logs, not return claims.

Use these templates manually, adapt them to your own process, or use them as a baseline for evaluating AI stock research tools.
