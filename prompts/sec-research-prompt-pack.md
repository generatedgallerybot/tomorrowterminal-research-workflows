# SEC filing research prompt pack for source-aware stock research

Created: 2026-05-26
Product adjacency: Tomorrow Terminal, https://tomorrowterminal.com
Purpose: useful public artifact for people doing first-pass equity research. This is workflow education, not investment advice.

## Who this is for

Use this when you want to understand a company from primary sources without letting an AI model invent confidence. The goal is not to decide whether a stock is good or bad. The goal is to build a cleaner research trail from SEC filings, financial statements, market data, news, and crowd discussion.

## Non-negotiable rule

Every answer must include:

- Source type, for example 10-K, 10-Q, 8-K, S-1, earnings release, transcript, news article, or company page
- Filing or publication date
- Exact excerpt or table row used
- A short explanation of why it matters
- Confidence level
- What is still unknown

If the model cannot cite the source, it should say so and stop.

## 10 minute first-pass workflow

1. Identify the business
   - Read the company description, segment note, and latest risk factors.
   - Output a one-paragraph plain-English business model.

2. Find what changed
   - Compare the latest 10-Q or 10-K against the prior period.
   - Focus on revenue, gross margin, cash flow, debt, customer concentration, and share count.

3. Check liquidity and dilution risk
   - Pull cash, debt, operating cash flow, recent financing, shelf registrations, warrants, and ATM programs.

4. Read management's own warnings
   - Extract the 5 to 10 risk factors most directly tied to revenue, survival, regulation, or financing.

5. Separate facts from narrative
   - Create two columns: verified facts and management claims.

6. Inspect market and crowd context
   - Summarize recent news, Reddit, and StockTwits discussion as attention context only.
   - Do not treat crowd excitement as evidence of business quality.

7. Write the research memo
   - Summarize what is known, what changed, what could matter next, and what needs human review.

## Prompt 1: source-grounded company snapshot

```text
You are helping with source-aware equity research. This is not investment advice.

Given the company ticker and the provided filings or source excerpts, create a company snapshot.

Required output:
1. Business model in plain English
2. Main revenue streams
3. Customer or segment concentration if disclosed
4. Key recent change from the latest filing
5. 5 source citations with source type, filing date, exact excerpt, and why it matters
6. Unknowns or areas needing human review

Rules:
- Do not use unstated facts.
- Do not make price targets, buy or sell recommendations, or return predictions.
- If evidence is missing, write "not established from provided sources."
```

## Prompt 2: compare this filing to the prior one

```text
Compare the latest filing against the prior comparable filing.

Focus areas:
- Revenue growth or decline
- Gross margin or operating margin change
- Cash and debt
- Operating cash flow
- Share count and dilution
- Segment performance
- New or removed risk language
- Material legal, regulatory, or customer changes

Output a table with:
- Topic
- Latest period fact
- Prior period fact
- Direction of change
- Exact source excerpt or table row
- Why a researcher should care
- Confidence

Rules:
- Do not infer causation unless management explicitly states it.
- Flag accounting changes separately from operating changes.
- If a metric is not comparable, explain why.
```

## Prompt 3: risk factor triage

```text
Extract and triage the most important risk factors from this filing.

Return:
1. Top 10 risk factors ranked by directness to business performance, financing, regulation, or survival
2. For each risk, include the exact excerpt, filing date, and a plain-English translation
3. Mark whether the risk is generic, company-specific, or newly intensified
4. Identify any risks that connect to recent news or financial statement changes

Rules:
- Do not exaggerate generic legal boilerplate.
- Do not minimize company-specific risks.
- Do not provide investment advice.
```

## Prompt 4: liquidity and dilution checklist

```text
Review the provided filings for liquidity and dilution indicators.

Check for:
- Cash and equivalents
- Debt maturity schedule
- Operating cash flow trend
- Going concern language
- Shelf registration
- ATM offering program
- Warrants or convertibles
- Recent private placements
- Share count changes
- Management comments about funding needs

Output:
- Evidence found
- Exact source excerpt
- Why it matters for research
- What cannot be concluded from the available sources

Rules:
- Do not call dilution good or bad.
- Do not predict financing events.
- Only state what filings support.
```

## Prompt 5: management claim audit

```text
Audit management's narrative against reported numbers.

Create three sections:
1. Claims supported by numbers
2. Claims not yet proven by numbers
3. Claims that need more source context

For each item, include:
- Management claim
- Relevant metric or filing excerpt
- Whether the evidence supports, partially supports, or does not establish the claim
- Human follow-up question

Rules:
- Be skeptical but fair.
- Avoid snark.
- Do not use stock price movement as proof of business quality.
```

## Prompt 6: crowd discussion sanity check

```text
Summarize recent Reddit, StockTwits, and news discussion around this ticker as attention context only.

Output:
- Main topics people are discussing
- Claims that require filing verification
- Obvious rumors or unsupported statements
- Links between crowd attention and recent company events
- What should be checked in primary sources before trusting the discussion

Rules:
- Do not treat crowd sentiment as investment evidence.
- Do not amplify rumors as facts.
- Do not recommend trades.
```

## Prompt 7: final research memo template

```text
Write a first-pass research memo from the provided source-backed notes.

Sections:
1. What the company does
2. What changed recently
3. Financial condition snapshot
4. Key risks
5. Management claims that deserve follow-up
6. Crowd and news context
7. Open questions for a human researcher
8. Source list

Rules:
- Keep the memo source-aware.
- Include exact citations for important claims.
- Use cautious language.
- No buy, sell, hold, price target, or expected return language.
```

## Red flags that should force a human review

- The model cites a filing but cannot quote the excerpt
- The model mixes quarterly and annual numbers without labeling them
- The model treats adjusted EBITDA as cash flow
- The model ignores share count changes
- The model makes a recommendation from social sentiment
- The model summarizes a risk factor without checking whether it changed
- The model uses news as proof when the primary filing says something narrower

## Clean output checklist

Before sharing a research note, verify:

- Every major claim has a source
- Dates are visible
- Excerpts are short and exact
- Unknowns are listed instead of guessed
- Crowd chatter is clearly labeled as chatter
- The conclusion does not become financial advice

## Why I made this

I have been working on Tomorrow Terminal, a source-aware stock research workflow that combines filings, financials, market data, news, Reddit, and StockTwits into one company profile. This prompt pack is the manual version of the standard I want AI research tools to meet: useful summaries, visible evidence, and no magic predictions.

Research only. Not financial advice.
