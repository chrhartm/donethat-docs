---
title: Demand aggregation signal
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - procurement
  - request
  - cost
domain: procurement
domainOrder: 1
stage: request
stageOrder: 1
outcome:
  - cost
value: 4
effort: 4
---
ML clusters similar requests across business units within a time window and surfaces consolidation opportunities to procurement.

## What it is, how it works

Aggregation looks across business units for requests that should have been one purchase. The model clusters similar requisitions inside a rolling time window, then tells a category manager there's a consolidation worth chasing before the individual POs go out.

- Similarity is computed on item description, category, and specification, not just exact part numbers.
- The time window is the real design decision. Too short and you catch nothing, too long and you delay everyone.
- Output is a ranked queue of opportunities with estimated combined volume.

## When not to use it

- Aggregation trades speed for price. If the requester needs the item this week, holding it to build a bundle costs more than it saves.
- It only pays where volume actually moves price. Commodity categories with published rate cards won't reward the wait.
- Without a category manager who owns the follow-through, the queue becomes another dashboard nobody works.

## How to get started

- Run it in observation mode for a quarter. Log the opportunities it finds and price what consolidation would have saved, without changing anyone's workflow.
- Pick one category with obvious fragmentation, usually IT hardware or office supplies, and act on that queue alone.
- Set an explicit hold rule so requesters know the maximum delay a bundle can impose.

## Best practices / further reading

- Pair it with [market price benchmarking](./market-price-benchmarking.md) so you know what the combined volume ought to cost.
- Consolidation opportunities that recur every quarter belong in a contract, which makes them a [category opportunity](./category-opportunity-identification.md) instead.
- Consolidation analysis features appear in [Sievo](https://sievo.com/).
