---
title: Probabilistic forecast roll-up
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - sales
  - close
  - quality
domain: sales
domainOrder: 1
stage: close
stageOrder: 6
outcome:
  - quality
value: 5
effort: 5
---
AI replaces gut-feel forecasts with data-driven deal probability and ARR-weighted commit, using tools like Clari, Aviso, or BoostUp.

## What it is, how it works

Probabilistic forecasting replaces stage-weighted arithmetic with a model of each deal's actual close probability, then rolls those up into a committed number with a range rather than a single figure.

- Probability is learned from deal characteristics and engagement, not assigned by stage.
- The roll-up produces a range, which is what a forecast honestly is.
- Divergence between the model and the rep's own call is surfaced rather than hidden, and that conversation is often the real value.

## When not to use it

- Forecasting is political. A model that contradicts the sales leader's number will be overridden, and if that happens routinely the model is decoration.
- Low deal volume makes probabilistic roll-up unstable. Enterprise teams closing a few dozen deals a year get wide, unhelpful ranges.
- Reps who learn the model's inputs will manage them, which corrupts the signal.

## How to get started

- Run it alongside the existing forecast for two quarters without replacing anything. Accuracy comparison is the only argument that will land.
- Report the range and the confidence, not a point estimate, and hold the line on that.
- Investigate disagreements between model and rep individually. Both are informative.

## Best practices / further reading

- Deal-level inputs come from [deal risk scoring](./deal-risk-scoring.md).
- Coaching on specific at-risk deals is [last-mile deal coaching](./last-mile-deal-coaching.md).
- Forecasting platforms include [BoostUp](https://boostup.ai/) and [Clari](https://www.clari.com/).
