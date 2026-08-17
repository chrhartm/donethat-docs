---
title: Negotiation position generation
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - procurement
  - select
  - cost
domain: procurement
domainOrder: 1
stage: select
stageOrder: 5
outcome:
  - cost
value: 3
effort: 1
---
LLM drafts BATNA analysis, target price range, and opening position from market data and supplier financials.

## What it is, how it works

Position generation drafts the preparation a buyer should do before a negotiation and rarely has time for: a target range, a walk-away point, an assessment of your alternatives, and the arguments the supplier is likely to make.

- The target range comes from benchmark data, the walk-away from your actual alternatives.
- Supplier financials and market position inform where they have room to move.
- Output is a briefing to be argued with, not a script to be read.

## When not to use it

- Don't take a generated walk-away point at face value. If the model doesn't know your switching costs, it doesn't know your alternatives.
- Long-term strategic relationships need judgment about the relationship, which no briefing captures.
- Treating the draft as settled strategy is the main failure mode. It's a starting point for the buyer's own thinking.

## How to get started

- Generate a position for a negotiation you've already completed and compare it against what actually happened.
- Have the buyer mark which arguments were useful. That feedback improves the next brief more than any configuration.
- Keep the range internal. Positions leak when they're pasted into supplier-facing documents.

## Best practices / further reading

- The target range should be built on [market price benchmarking](./market-price-benchmarking.md), not on last year's price.
- Where you have concentration exposure, [single source risk flagging](./single-source-risk-flagging.md) tells you how weak your alternatives really are.
- Market data for target ranges comes from platforms such as [Sievo](https://sievo.com/).
