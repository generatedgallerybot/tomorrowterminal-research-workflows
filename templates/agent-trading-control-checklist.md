# Agent trading control checklist

Use this checklist before connecting any AI-assisted workflow to trade execution.

This is research workflow material only. It is not financial advice, a trading strategy, a return prediction system, or a buy/sell recommendation.

## 1. Start with paper mode

- The strategy can run without live capital.
- Paper behavior uses the same data path and decision path as live mode.
- Every simulated trade records the timestamp, input data, intended order, and reason.
- The system can explain why it did nothing.

## 2. Keep the source trail visible

For every strategy signal or rebalance decision, record:

- filing, news, market data, or user-defined rule that mattered
- exact metric or excerpt used
- date and source URL when available
- whether the signal was deterministic or model-generated
- any uncertainty or missing data

If the source trail is missing, the action should be blocked or flagged for review.

## 3. Scope permissions tightly

- Use trade-only keys.
- Do not give withdrawal permission.
- Do not give custody permission.
- Separate read keys from execution keys where possible.
- Rotate keys after testing or if logs show unexpected behavior.

## 4. Set hard limits before live use

Define these before the agent can place live orders:

- maximum account allocation
- maximum single-position allocation
- maximum order size
- maximum daily loss
- maximum number of trades per day
- allowed symbols or markets
- allowed order types
- allowed trading hours, if relevant

These should be enforced by code, not just included in a prompt.

## 5. Require a stop path

The operator should have:

- one-click flatten or cancel-all behavior
- one-click pause
- automatic pause on data failures
- automatic pause on execution failures
- automatic pause on daily loss limit
- clear notification when a breaker trips

## 6. Log every action

Each action should include:

- timestamp
- strategy name
- input data snapshot or references
- model output, if used
- deterministic rules applied
- order details
- result from broker or exchange
- failure reason, if any
- whether a human approved it

## 7. Avoid dangerous product claims

Do not describe an AI trading agent as:

- guaranteed profitable
- alpha-generating
- market-beating
- autonomous money management
- a replacement for research or judgment

Safer framing:

- source-aware research
- user-defined paper-tested strategies
- controlled execution
- audit logs
- human-set rails
- research only, not financial advice

## 8. Review questions

Before enabling live execution, ask:

1. Can I reconstruct why every trade happened?
2. Can the system refuse to act when sources are weak?
3. Are risk limits enforced outside the model prompt?
4. Can I stop or flatten quickly?
5. Would the logs make sense to someone who did not build the system?

If any answer is no, keep it in paper mode.
