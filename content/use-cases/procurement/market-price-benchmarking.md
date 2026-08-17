---
title: Market price benchmarking
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - procurement
  - source
  - cost
domain: procurement
domainOrder: 1
stage: source
stageOrder: 3
outcome:
  - cost
value: 4
effort: 3
---
AI pulls real-time market and historical pricing data to build a should-cost model before RFQ issuance.

## What it is, how it works

Benchmarking builds a should-cost view before the RFQ goes out. The model assembles market indices, your own purchase history, and comparable transactions into a defensible price range, so the buyer opens the negotiation knowing what good looks like.

- Internal price history is usually the strongest signal, and the one teams most often ignore.
- Commodity and index data anchor categories where raw material cost moves the price.
- The output is a range with its inputs shown, not a single number to be taken on faith.

## When not to use it

- Highly bespoke categories have no comparable transactions, and a confident range built on thin data is worse than admitting you don't know.
- Benchmarks age quickly in volatile categories. A model refreshed quarterly will mislead you in a market that moves monthly.
- Don't hand the range to suppliers as a target. It becomes the floor you negotiate up from.

## How to get started

- Start with a category you buy repeatedly. Your own history gives you a benchmark before any external data is purchased.
- Compare the model's range against the last three awards in that category. Consistent bias tells you what to correct.
- Record the range before the event and the outcome after, so the benchmark earns credibility from its own track record.

## Best practices / further reading

- The range is the input to [negotiation position generation](./negotiation-position-generation.md), which turns it into an opening position and a walk-away.
- Sustained gaps between benchmark and actual price are exactly what [spend analytics and savings tracking](./spend-analytics-and-savings-tracking.md) is built to surface.
- Should-cost and benchmarking features appear in [GEP](https://www.gep.com/) and [Sievo](https://sievo.com/).
