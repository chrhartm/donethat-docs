---
title: Spend analytics and savings tracking
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - procurement
  - review
  - cost
domain: procurement
domainOrder: 1
stage: review
stageOrder: 8
outcome:
  - cost
value: 4
effort: 3
---
ML classifies actuals against contract prices to compute realized savings, price drift, and off-contract leakage by category, using tools like Suplari or Sievo.

## What it is, how it works

Spend analytics checks real transactions against contracted prices. It shows what was actually saved, where prices drifted, and how much spend went off-contract. This is the layer that decides whether a negotiated saving ever reached the accounts.

- Realized savings compares invoiced price against the contracted price for the same item, not against a forecast.
- Price drift is tracked over the contract term, since erosion is gradual and rarely noticed transaction by transaction.
- Category managers see their own leakage rather than a company-wide aggregate.

## When not to use it

- Savings numbers are political. Ship a tool that contradicts them without warning anyone, and the tool gets discredited rather than the numbers.
- Coding quality caps everything. If categories are wrong, every figure below them is wrong too.
- Cost avoidance isn't cash. Presenting the two in one total invites finance to dismiss both.

## How to get started

- Reconcile against the general ledger before publishing anything. Analytics that disagrees with finance loses that argument every time.
- Report realized savings separately from avoided cost, with the method for each stated.
- Fix [spend category auto-classification](./spend-category-auto-classification.md) first if coding is inconsistent, since it sets the ceiling here.

## Best practices / further reading

- Off-contract leakage is isolated by [maverick spend detection](./maverick-spend-detection.md).
- Platforms in this space include [Sievo](https://sievo.com/) and Suplari.
