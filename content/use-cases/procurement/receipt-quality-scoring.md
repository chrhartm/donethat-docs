---
title: Receipt quality scoring
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - procurement
  - receive
  - quality
domain: procurement
domainOrder: 1
stage: receive
stageOrder: 7
outcome:
  - quality
value: 3
effort: 3
---
ML aggregates delivery accuracy, damage rates, and timing compliance per supplier into a running quality KPI.

## What it is, how it works

Quality scoring turns individual receipt events into a running per-supplier KPI. Delivery accuracy, damage rate, documentation quality, and timing compliance combine into a score that updates continuously instead of being assembled by hand before a review meeting.

- Inputs are receipt events you already capture, so this rarely needs new data collection.
- Weighting differs by category, because timing matters more for some goods than damage does.
- Trend direction is reported alongside the level, since a declining good supplier needs attention sooner than a stable mediocre one.

## When not to use it

- Scores computed on small volumes swing wildly. Suppress the score below a minimum receipt count rather than publishing noise.
- Receiving-side errors show up as supplier defects. If your dock miscounts, you'll penalize suppliers for your own process.
- A score nobody discusses with suppliers changes nothing. The conversation is the mechanism, not the number.

## How to get started

- Publish scores internally for a quarter before sharing them with suppliers, so you can find the measurement errors first.
- Agree the weighting with category managers. They know which failures actually hurt.
- Share the method with suppliers when you share the score. Unexplained scores get disputed rather than acted on.

## Best practices / further reading

- Scores are the performance record surfaced by [historical performance retrieval](./historical-performance-retrieval.md) at the next sourcing event.
- Timing data feeds [delivery lead time prediction](./delivery-lead-time-prediction.md).
- Supplier scorecards are standard in [Zycus](https://www.zycus.com/).
