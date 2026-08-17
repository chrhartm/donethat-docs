---
title: Delivery discrepancy classification
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
value: 2
effort: 3
---
Vision and NLP classify goods receipt issues, such as short delivery, wrong item, or damage, from delivery notes and photographic evidence.

## What it is, how it works

Discrepancy classification sorts goods receipt problems into types: short delivery, wrong item, damage, or documentation error. It reads delivery notes and any photographs the receiving team captured, then assigns the category that determines how the claim is handled.

- Photographic evidence is the distinguishing input, since damage is visual and rarely described well in text.
- Classification drives routing, because a damage claim and a short delivery go to different people.
- The evidence stays attached to the record, which is what makes a supplier claim defensible later.

## When not to use it

- If dock staff don't photograph problems today, the model has nothing to read. Changing that habit is the real project.
- Judging damage from a photo is rough. Use it to route and rank, not to price a claim.
- Low discrepancy volumes don't justify the setup. Count your exceptions before building anything.

## How to get started

- Fix capture first. A simple phone workflow at the dock produces more value than any model applied to missing data.
- Start with the classification split that matters commercially, usually damage against shortage.
- Track how often the assigned category is corrected downstream. That's your accuracy signal.

## Best practices / further reading

- Classified discrepancies aggregate into [receipt quality scoring](./receipt-quality-scoring.md).
- Discrepancies are the exceptions that stop [three-way match automation](./three-way-match-automation.md) from completing.
- Receipt exceptions are managed in suites such as [Zycus](https://www.zycus.com/).
