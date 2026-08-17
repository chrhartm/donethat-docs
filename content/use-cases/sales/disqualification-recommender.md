---
title: Disqualification recommender
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - sales
  - qualify
  - quality
domain: sales
domainOrder: 1
stage: qualify
stageOrder: 2
outcome:
  - quality
value: 3
effort: 1
---
An adversarial review flags unfit deals with rationale before reps invest more cycles.

## What it is, how it works

Disqualification review looks for reasons a deal will not close and says so early. It's an adversarial pass over the opportunity, arguing the negative case with the evidence attached, so reps stop spending cycles on deals the data says are dead.

- The model argues against the deal deliberately rather than scoring it neutrally.
- Reasoning is explicit, which lets the rep rebut it with information the system lacks.
- Recommendations are advisory. Closing a deal is a human decision.

## When not to use it

- Disqualification advice built on thin history will kill good deals, especially in new segments where the pattern legitimately differs.
- Reps who feel judged will stop logging the information the model runs on.
- Long enterprise cycles look dormant while progressing. Time-based signals mislead badly in that context.

## How to get started

- Backtest against closed-lost deals. If it flags them late, it's not earning attention.
- Present it as time reallocation rather than pipeline reduction. The framing decides adoption.
- Let reps mark recommendations wrong and record why. That feedback is the fastest improvement path.

## Best practices / further reading

- Qualification fields from [MEDDIC auto-extraction](./meddic-auto-extraction.md) are the strongest input here.
- Late-stage equivalents are [deal risk scoring](./deal-risk-scoring.md) and [last-mile deal coaching](./last-mile-deal-coaching.md).
- Qualification signals are surfaced by [Gong](https://www.gong.io/) and [Clari](https://www.clari.com/).
