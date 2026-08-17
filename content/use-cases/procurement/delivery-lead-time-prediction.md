---
title: Delivery lead time prediction
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - procurement
  - order
  - speed
domain: procurement
domainOrder: 1
stage: order
stageOrder: 6
outcome:
  - speed
value: 4
effort: 4
---
ML predicts actual delivery dates using supplier history, carrier data, and logistics signals, enabling proactive escalation.

## What it is, how it works

Lead-time prediction estimates when an order will actually arrive, rather than repeating the date the supplier promised. Supplier history, carrier performance, route, and seasonality produce a predicted date and a confidence range that planners can act on.

- The model learns per supplier and per route, since a supplier reliable on one lane may not be on another.
- A range matters more than a point estimate, because planning decisions depend on the worst case.
- Divergence between predicted and promised dates is itself the escalation trigger.

## When not to use it

- Without goods receipt timestamps there's no training data, and lead-time prediction is the use case most often blocked by this gap.
- New suppliers and new routes have no history, and confidence should be reported as low rather than defaulted to the category average.
- Prediction without a planning response is decoration. Someone has to act on the early warning for it to be worth building.

## How to get started

- Check that your receipt data records actual dates rather than posting dates. This single data-quality question decides feasibility.
- Start with the ten suppliers carrying the most critical volume rather than the whole base.
- Compare predicted against promised on live orders and show planners the gap. That comparison is what earns adoption.

## Best practices / further reading

- Receipt-side accuracy is measured by [receipt quality scoring](./receipt-quality-scoring.md), which also feeds this model.
- Persistent lateness against promise is a performance record for [historical performance retrieval](./historical-performance-retrieval.md).
- Supplier performance data feeds platforms such as [Zycus](https://www.zycus.com/).
