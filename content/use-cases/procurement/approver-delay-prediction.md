---
title: Approver delay prediction
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
value: 1
effort: 3
---
ML predicts approver response time based on calendar and workload and pre-escalates to a backup before the SLA is breached.

## What it is, how it works

Delay prediction estimates whether an approver will respond in time, using calendar load, current queue depth, and their own response history. Where a breach looks likely, it escalates to a backup before the SLA is missed rather than after.

- Prediction runs at routing time, so escalation happens early enough to matter.
- Calendar and workload signals carry most of the accuracy, particularly around leave.
- Escalation goes to a named backup defined in the delegation model, not to a generic queue.

## When not to use it

- Predicting individual response times is monitoring of individuals. That needs to be agreed openly, not introduced quietly.
- If approvals are slow because there are too many of them, this treats the symptom. [Risk-based approval routing](./risk-based-approval-routing.md) addresses the cause.
- Escalating too eagerly trains approvers to ignore their queue, since someone else will handle it.

## How to get started

- Check how much of your cycle time is actually approver wait. Often it's smaller than assumed, and the effort belongs elsewhere.
- Use calendar availability alone before modeling individual behavior. It's simpler, less intrusive, and captures most of the benefit.
- Agree escalation rules with approvers in advance so the first escalation isn't a surprise.

## Best practices / further reading

- Removing unnecessary approvals entirely beats predicting delay in them, which is the case for [low-risk auto-approval](./low-risk-auto-approval.md).
- Backup approvers must still satisfy [DOA compliance enforcement](./doa-compliance-enforcement.md).
- Approval orchestration tools include [Tonkean](https://www.tonkean.com/).
