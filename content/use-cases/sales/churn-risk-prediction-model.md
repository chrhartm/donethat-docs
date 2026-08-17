---
title: Churn-risk prediction model
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - sales
  - renew
  - quality
domain: sales
domainOrder: 1
stage: renew
stageOrder: 8
outcome:
  - quality
value: 5
effort: 5
---
Multi-signal machine learning scores accounts on usage, sentiment, and ticket trends 90 days before renewal, using tools like ChurnZero, Gainsight, or Velaris.

## What it is, how it works

Churn prediction scores accounts on renewal risk months before the renewal date, combining product usage, support ticket patterns, sentiment, and relationship signals. The point is lead time: a risk found in the last month is usually already lost.

- Multiple signal families are combined, since usage alone misses relationship failures and vice versa.
- Scores carry the contributing factors so a CSM knows what to address.
- Prediction horizon is explicit, because a model that predicts churn a week out is not useful.

## When not to use it

- Usage-only models mistake efficient customers for disengaged ones, and they miss the account that uses the product daily while hating it.
- Prediction without capacity to intervene produces a list of accounts you will watch churn on schedule.
- Concentrated customer bases do not have the volume for a stable model, and judgment beats it.

## How to get started

- Fix the definition of churn first, including downgrades and partial non-renewals. Most disagreement about model accuracy is disagreement about the label.
- Validate the horizon. If the model only fires inside 30 days, it is reporting, not predicting.
- Pair every risk tier with an agreed play before deployment.

## Best practices / further reading

- The play itself is chosen by [save play recommender](./save-play-recommender.md).
- Contact loss is a specific strong signal handled by [champion departure monitoring](./champion-departure-monitoring.md).
- Unmet promises from [promised commitments extractor](./promised-commitments-extractor.md) are worth including as features.
- Retention platforms include [ChurnZero](https://www.churnzero.com/) and [Velaris](https://velaris.io/).
