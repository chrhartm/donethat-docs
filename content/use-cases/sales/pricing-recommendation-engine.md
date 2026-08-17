---
title: Pricing recommendation engine
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - sales
  - propose
  - quality
domain: sales
domainOrder: 1
stage: propose
stageOrder: 4
outcome:
  - quality
value: 3
effort: 4
---
Machine learning suggests price and discount levels by segment, deal size, and historical win rates, using tools like Pricefx or DealHub.

## What it is, how it works

Pricing recommendation suggests a price and discount level for a specific deal, based on segment, deal size, competitive context, and what actually won at what price historically. It replaces discount decisions made on instinct under quarter-end pressure.

- Recommendations are learned from your own win and loss data at each price point.
- Guardrails come from approved bands, so the model advises inside policy rather than around it.
- The reasoning is shown, which matters when a rep needs to argue for an exception.

## When not to use it

- The model learns from deals you won, and you have no data on the price that would have won a deal you lost. That gap biases every recommendation.
- Optimizing each deal separately can erode price across a segment, since discounts become the norm the model then learns from.
- In regulated or public-sector selling, pricing consistency may be a legal requirement rather than a strategy choice.

## How to get started

- Start with recommendations to managers on approvals rather than to reps in the moment.
- Track realized price by segment over time, not just win rate, so erosion is visible.
- Review the floor quarterly with finance rather than letting the model define it.

## Best practices / further reading

- Recommended pricing flows into [auto-drafted proposal](./auto-drafted-proposal.md).
- Competitive pressure on price shows up first in [deal risk scoring](./deal-risk-scoring.md).
- Pricing platforms include [Pricefx](https://www.pricefx.com/) and [DealHub](https://dealhub.io/).
