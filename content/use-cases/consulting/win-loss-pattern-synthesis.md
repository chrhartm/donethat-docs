---
title: Win/Loss Pattern Synthesis
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - consulting
  - sell
  - quality
domain: consulting
domainOrder: 19
stage: sell
stageOrder: 1
outcome:
  - quality
value: 3
effort: 3
---
LLM analyzes closed-deal data to surface recurring win themes and proposal weaknesses by client segment and deal type.

## What it is, how it works

Win-loss synthesis reads closed-deal records and surfaces what actually repeats: the themes that win in a sector, the proposal weaknesses that recur, the competitors who beat you and on what. It turns scattered debriefs into a pattern.

- Analysis spans proposals, debrief notes, and outcome data rather than a single feedback form.
- Patterns are reported by segment and deal type, since aggregate findings hide the useful signal.
- Both sides matter. What you reliably win on is as actionable as what you lose on.

## When not to use it

- Stated loss reasons are unreliable. Clients say price when they mean they did not believe you, and the model reads what was written.
- Small firms will not have the deal volume for stable patterns, and acting on noise is worse than not looking.
- Findings that read as blame get resisted. Frame them as proposal problems, not partner problems.

## How to get started

- Segment before concluding anything. Patterns across different practices cancel each other out.
- Compare model findings with what partners believe. Disagreements are the interesting part.
- Send conclusions to whoever owns the proposal library, since that is where a fix actually lands.

## Best practices / further reading

- Patterns become screening features in [bid no bid opportunity classifier](./bid-no-bid-opportunity-classifier.md).
- Recurring objections should be pre-empted by [proposal red team reviewer](./proposal-red-team-reviewer.md).
- Deal records are usually exported from the CRM into a tool such as [Airtable](https://airtable.com/) for this analysis.
