---
title: DoA compliance enforcement
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
AI cross-checks each approver against the delegation-of-authority matrix and flags unauthorized approvals before they post.

## What it is, how it works

DOA enforcement checks each approver against the delegation-of-authority matrix before an approval posts. Where someone approves beyond their limit, or approves something they requested, the system catches it at the point of approval rather than at audit.

- The matrix is read as data, so limits change without redeploying anything.
- Self-approval and circular approval chains are detected explicitly.
- Blocked approvals produce a clear message naming the limit and the correct approver.

## When not to use it

- This is a hard control, not an advisory one. If your DOA matrix is out of date, enforcement will block legitimate work on day one.
- Acting delegations during leave are where most DOA breaches originate, and a matrix that doesn't model them will be worked around.
- Where the matrix genuinely is ambiguous, resolve it with finance before automating. The system can't interpret intent.

## How to get started

- Reconcile the matrix against the current org chart before switching anything on. This is the whole job, and it's usually overdue.
- Run in detection mode for a month and count the breaches. The number is generally uncomfortable and makes the case for enforcement.
- Model delegation explicitly, including start and end dates, so cover during absence is legitimate rather than a breach.

## Best practices / further reading

- Enforcement is the boundary [risk-based approval routing](./risk-based-approval-routing.md) has to operate within.
- Breaches that recur in one area usually indicate a threshold set wrong, which shows up in [approval anomaly flagging](./approval-anomaly-flagging.md).
- Authority matrices are enforced in platforms such as [Zip](https://ziphq.com/).
