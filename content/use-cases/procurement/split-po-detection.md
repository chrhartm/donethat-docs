---
title: Split-PO detection
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - procurement
  - order
  - quality
domain: procurement
domainOrder: 1
stage: order
stageOrder: 6
outcome:
  - quality
value: 2
effort: 2
---
Classifier identifies sequences of POs that appear structured to circumvent approval thresholds.

## What it is, how it works

Split detection finds sequences of orders that look structured to stay under an approval threshold: several POs to one supplier, close together, each just below a limit, that would have needed a higher approver as a single order.

- Detection works on sequences over a time window, so it sees what per-order checks cannot.
- Similarity of supplier, category, and requester is what links orders into a candidate sequence.
- Findings are presented with the combined value and the approval level it would have required.

## When not to use it

- Legitimate splitting is common. Phased delivery, budget-period boundaries, and separate cost centers all produce the same pattern.
- Treating detections as misconduct rather than as questions poisons the control. Most cases have an innocent explanation.
- Thresholds set unrealistically low cause splitting as a rational response, and detection then punishes people for a policy problem.

## How to get started

- Run it historically first. The base rate tells you whether this is a real problem at your organization or a theoretical one.
- Route findings to internal audit or a category lead rather than back to the requester.
- If one threshold generates most detections, the threshold is probably wrong. Fix the policy before tightening the control.

## Best practices / further reading

- This is the aggregation blind spot of [low-risk auto-approval](./low-risk-auto-approval.md), and the two belong together.
- Related patterns in the approval queue are covered by [approval anomaly flagging](./approval-anomaly-flagging.md).
- Threshold controls are configured in platforms such as [Zip](https://ziphq.com/).
