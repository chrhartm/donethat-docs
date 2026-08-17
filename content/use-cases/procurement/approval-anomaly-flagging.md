---
title: Approval anomaly flagging
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - procurement
  - approve
  - quality
domain: procurement
domainOrder: 1
stage: approve
stageOrder: 2
outcome:
  - quality
value: 3
effort: 2
---
ML detects unusual patterns in the approval queue, such as unusual amounts for a category or split-request attempts, and surfaces them for human review.

## What it is, how it works

Anomaly flagging watches the approval queue for requests that don't fit the pattern for their category: an unusual amount, a supplier that rarely appears, a sequence that looks like a threshold is being worked around. Flagged items go to a human, not to a rejection.

- The baseline is your own history per category, so what counts as unusual is specific to you.
- Sequence detection looks across requests rather than at each in isolation.
- Each flag states which feature was unusual, which is what makes review fast.

## When not to use it

- Anomalous isn't wrong. Most flags will be legitimate exceptions, and a team that treats flags as accusations will stop raising them.
- New categories have no baseline, and everything looks anomalous until enough history accumulates.
- Flagging without an owner produces a queue nobody works, which is worse than no detection at all.

## How to get started

- Run it silently for a quarter and review what it would have flagged. That tells you the false-positive rate before anyone is asked to act.
- Tune to a volume the reviewing team can genuinely handle each week.
- Track outcomes per flag type and switch off the categories that never find anything.

## Best practices / further reading

- The threshold-avoidance case is covered more directly by [split PO detection](./split-po-detection.md) at the order stage.
- Anomalies that turn out to be policy gaps belong upstream in [policy pre-check at intake](./policy-pre-check-at-intake.md).
- Approval analytics appear in [Zip](https://ziphq.com/).
