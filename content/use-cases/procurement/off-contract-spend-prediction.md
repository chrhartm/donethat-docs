---
title: Off-contract spend prediction
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
value: 2
effort: 3
---
ML flags requests likely to result in maverick spend based on requester behavior, category, and supplier history.

## What it is, how it works

Prediction flags requests that look likely to end up as maverick spend, based on requester history, category, and the supplier being named. It's a forward-looking companion to maverick detection, which finds the leakage after the money is gone.

- Features are behavioral: who is asking, for what, naming which supplier, against what contract coverage.
- A flag routes the request to a category specialist rather than blocking it.
- The specialist's decision feeds back as a label, so the model improves on your own outcomes.

## When not to use it

- Prediction on individuals is a surveillance question as much as a procurement one. Decide who sees the flags and on what basis before you switch it on.
- Where contract coverage is genuinely thin, the model is describing a sourcing gap rather than misbehavior. Fix the coverage instead.
- Small teams won't have the request volume to make the signal stable.

## How to get started

- Establish the actual off-contract rate first using [maverick spend detection](./maverick-spend-detection.md). Without it you can't tell whether prediction helps.
- Route flags to a helpful intervention, such as suggesting the contracted supplier, not to a rejection.
- Report at category level rather than by requester. It keeps attention on coverage gaps and avoids the surveillance framing.

## Best practices / further reading

- Pair with [policy pre-check at intake](./policy-pre-check-at-intake.md), which catches the rule-based cases this model doesn't need to learn.
- Spend visibility tooling includes [Suplari](https://www.suplari.com/).
