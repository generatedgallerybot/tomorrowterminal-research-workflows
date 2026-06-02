# Hyperliquid agent control surface checklist

Use this as a review checklist before connecting any AI-assisted workflow to Hyperliquid execution.

This is research and risk-review material only. It is not financial advice, a trading strategy, a return prediction system, or a buy/sell recommendation.

## Core idea

Hyperliquid makes execution programmable and always-on. That is powerful, but it means the product surface around the agent matters as much as the model.

A useful AI trading terminal should make these things visible:

- what the agent is allowed to do
- what it is forbidden to do
- why it wants to act
- what data it used
- what limits apply
- how to stop it fast
- what happened afterward

If those are not inspectable, keep the workflow in paper mode.

## 1. Account and key permissions

Before live execution:

- Use scoped execution permissions when available.
- Do not grant withdrawal permission.
- Do not grant custody over funds.
- Keep read-only and trading permissions separate when possible.
- Store keys outside prompts and chat logs.
- Rotate keys after testing, incidents, or unexpected behavior.
- Keep a documented owner/operator for every active key.

Questions:

- Can this key withdraw funds? If yes, stop.
- Can this key trade markets outside the intended set? If yes, restrict it.
- Can a human revoke or rotate it quickly?

## 2. Strategy scope

Every strategy should declare:

- strategy name
- market or symbol allowlist
- long-only, short-only, long/short, or market-neutral mode
- maximum account allocation
- maximum position size
- maximum order size
- maximum leverage, if applicable
- maximum daily loss
- maximum trades per day
- rebalance frequency
- allowed order types
- whether human approval is required

These limits should be enforced by code, not only by a prompt.

## 3. Paper mode parity

Paper mode is only useful if it resembles live mode.

Check:

- Same data path as live mode.
- Same signal generation path as live mode.
- Same risk checks as live mode.
- Same logs as live mode.
- Simulated fills are labeled clearly as simulated.
- Paper results cannot be confused with live PnL.

Avoid:

- backtest screenshots that imply future performance
- cherry-picked paper runs
- hiding failed or inactive strategies

## 4. Decision receipts

For every proposed action, record:

- timestamp
- strategy name
- market
- current position
- proposed order
- input data references
- model output, if used
- deterministic rules applied
- risk checks passed or failed
- whether the action was blocked, simulated, or executed

For AI-generated reasoning, require source context. If the system cannot show what it used, the action should be blocked or flagged.

## 5. Risk breakers

Minimum breakers:

- daily loss limit
- per-strategy loss limit
- max position limit
- max order size
- max trade count per day
- data freshness failure
- exchange/API error spike
- model/tool error spike
- abnormal slippage or fill behavior

When a breaker trips:

- pause strategy
- notify operator
- log reason
- require explicit restart

## 6. Stop controls

The operator should have:

- one-click pause strategy
- one-click cancel open orders
- one-click close-all / flatten
- visible current exposure
- visible pending orders
- visible last action and reason
- clear status: paper, paused, live, breaker tripped

A kill switch that is hidden under three menus is not a kill switch. It is a scavenger hunt.

## 7. Alerts

Alert on:

- every live order submitted
- every fill
- every rejected order
- every risk breaker
- every strategy pause/restart
- every key/permission change
- every data outage
- every unusual error loop

Alerts should include enough context to understand what happened without opening five dashboards.

## 8. Public scorecards

If the product publishes theses, calls, or model opinions, score them transparently.

Good scorecard behavior:

- includes misses
- defines evaluation window
- labels paper vs live clearly
- avoids implying future performance
- explains methodology
- shows stale or unresolved calls separately

Safer framing:

```text
The scorecard is for transparency, not a promise of future performance.
```

Avoid:

- “hit rate” as the main marketing hook
- PnL screenshots without context
- backtest-only claims
- cherry-picked wins

## 9. MCP/API agent access

If external agents can access the terminal through MCP or REST APIs, separate tools by risk level.

Low-risk tools:

- read market profile
- read filing summary
- read watchlist
- read scanner/discovery feed
- read scorecard

Medium-risk tools:

- draft strategy
- run paper simulation
- request research generation
- propose rebalance

High-risk tools:

- enable live strategy
- change limits
- place order
- cancel/replace order
- close position

High-risk tools should require explicit permissions, logs, and ideally human confirmation unless the user intentionally configured autonomous execution rails.

## 10. Launch copy sanity check

Safer phrases:

- guarded execution workflows
- user-set limits
- non-custodial execution
- no withdrawal permission
- paper mode first
- source-aware research
- activity logs
- one-click close-all
- research only, not financial advice

Avoid:

- guaranteed profits
- alpha bot
- market beating
- set and forget money machine
- autonomous money manager
- trade recommendations
- predictions framed as certainty

## Pre-live review

Before any AI-assisted Hyperliquid workflow goes live, answer:

1. Can I reconstruct every decision from logs?
2. Can I stop everything quickly?
3. Are limits enforced outside the model prompt?
4. Are keys scoped so funds cannot be withdrawn?
5. Are paper and live results clearly separated?
6. Are scorecards transparent about misses?
7. Would a skeptical user understand what the agent can and cannot do?

If any answer is no, keep it in paper mode.
