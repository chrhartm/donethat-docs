---
title: Scope Risk Classifier
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - consulting
  - scope
  - quality
domain: consulting
domainOrder: 19
stage: scope
stageOrder: 2
outcome:
  - quality
value: 2
effort: 3
---
LLM classifies each scope element by delivery risk, including ambiguity, dependencies, and client readiness, against past project patterns.

## What it is, how it works

Scope risk classification rates each element of a scope on how likely it is to cause trouble: ambiguous wording, dependencies on client action, unproven data access, or readiness the client has not demonstrated. Patterns come from your own past overruns.

- Each scope line gets a risk level with the reason attached.
- Client-dependency risk is separated from technical risk, because the mitigations differ completely.
- Risky elements can be repriced, re-worded, or moved to a later phase.

## When not to use it

- Every engagement carries risk. A classifier that flags most of the scope has told you nothing you can act on.
- The model cannot see client politics, which is frequently the real risk.
- Used to justify padding every estimate, it becomes a commercial problem rather than a delivery tool.

## How to get started

- Train on engagements that overran and what caused it. Without that history this is generic advice.
- Act on the top three risks per SOW by changing the wording or the phasing.
- Check at close whether the flagged elements were the ones that actually hurt.

## Best practices / further reading

- Risk levels should widen the ranges in [effort estimation from historical actuals](./effort-estimation-from-historical-actuals.md).
- Unstated assumptions are a separate check in [assumption gap detector](./assumption-gap-detector.md).
- Scope elements are usually tracked in [Smartsheet](https://www.smartsheet.com/) or a similar planning tool.
