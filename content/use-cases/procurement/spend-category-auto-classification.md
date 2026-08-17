---
title: Spend category auto-classification
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - procurement
  - request
  - speed
domain: procurement
domainOrder: 1
stage: request
stageOrder: 1
outcome:
  - speed
value: 2
effort: 2
---
ML classifies each request into a procurement taxonomy, such as UNSPSC, using request text and historical data.

## What it is, how it works

Classification assigns every request a taxonomy code, usually [UNSPSC](https://www.unspsc.org/) or an internal variant, from the request text and historical patterns. Consistent coding is what makes downstream spend analysis mean anything.

- The model reads description, supplier, and amount, then predicts the category node.
- Historical requisitions supply the labels, so accuracy tracks the quality of your past coding.
- Low-confidence predictions route to a human instead of guessing at a leaf node.

## When not to use it

- If your historical coding is inconsistent, the model learns the inconsistency. Clean a sample first and see how bad it is.
- Deep taxonomies degrade fast. Predicting a top-level family is reliable, predicting a four-level commodity code often isn't.
- Don't classify and forget. Categories that carry tax or regulatory meaning need review regardless of model confidence.

## How to get started

- Classify at the level your reporting actually uses. If nobody reports below segment level, don't predict below it either.
- Backfill historical spend first. That gives you a clean baseline and reveals how much of your old coding was wrong.
- Publish per-category accuracy so category managers know which numbers to trust.

## Best practices / further reading

- Classification quality sets the ceiling for [spend analytics and savings tracking](./spend-analytics-and-savings-tracking.md).
- Consistent coding is what lets [maverick spend detection](./maverick-spend-detection.md) tell leakage from a coverage gap.
- Tools built around spend taxonomy include [Sievo](https://sievo.com/) and [Zycus](https://www.zycus.com/).
