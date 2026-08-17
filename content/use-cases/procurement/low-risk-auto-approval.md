---
title: Low-risk auto-approval
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - procurement
  - approve
  - speed
domain: procurement
domainOrder: 1
stage: approve
stageOrder: 2
outcome:
  - speed
value: 3
effort: 2
---
Rule-trained classifier auto-approves requests below defined risk and value thresholds with a full audit trail.

## What it is, how it works

Auto-approval clears requests that fall below defined risk and value thresholds without a human touching them. A trained classifier confirms the request matches the profile of things that always get approved, and the approval posts with a full audit trail.

- Thresholds are policy decisions, and the classifier enforces them rather than setting them.
- The audit record captures the rule, the score, and the inputs, because that record is what makes the control defensible.
- Anything outside the profile routes to a human instead of guessing.

## When not to use it

- If approvers are rubber-stamping today, automating that isn't a control improvement. It just removes the last chance to notice.
- Requests that are individually small but repeated can aggregate past a threshold, and a per-request check won't see it.
- Fraud tends to target exactly the band below the review threshold, which is why this needs pairing with anomaly detection.

## How to get started

- Find the band where approval has been unanimous for a year. That's your starting threshold, and it's usually lower than people expect.
- Sample approved requests monthly and review them properly. Automation without sampling degrades quietly.
- Publish the threshold. Hidden thresholds get gamed, and published ones set expectations.

## Best practices / further reading

- Pair with [approval anomaly flagging](./approval-anomaly-flagging.md) so the auto-approved band is still watched.
- [Split PO detection](./split-po-detection.md) catches the aggregation case that per-request thresholds miss.
- Approval automation is configured in [Zip](https://ziphq.com/) and [Tonkean](https://www.tonkean.com/).
