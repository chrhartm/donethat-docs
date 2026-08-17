---
title: Risk-based approval routing
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
value: 4
effort: 3
---
Agentic AI scores request risk by value, supplier novelty, and policy gaps, then routes to the correct approver tier while skipping unnecessary layers, using tools like Zip or Tonkean.

## What it is, how it works

Risk-based routing decides who needs to approve a request rather than sending everything through a fixed chain. Value, supplier novelty, category, and policy gaps produce a risk score, and the score selects the approval path.

- Low-risk requests skip approval layers that add delay without adding scrutiny.
- High-risk requests gain reviewers, which is the half of the trade teams tend to forget.
- Every routing decision is logged with the score and the factors behind it.

## When not to use it

- Delegation-of-authority rules are usually a legal constraint rather than a preference. Risk routing operates inside them, never around them.
- Auditors will ask why a given request took a shorter path. If you can't reconstruct the reason, don't deploy it.
- Changing who approves what is an organizational change. Rolling it out as a technical one is how it gets reversed.

## How to get started

- Measure where time is actually lost first. If the delay is approvers not responding, routing won't fix it and [approver delay prediction](./approver-delay-prediction.md) is the closer match.
- Model the new routing against last quarter's requests and show finance which approvals would have been skipped.
- Keep a manual escalation path. People need somewhere to go when the routing is wrong.

## Best practices / further reading

- Routing must respect [DOA compliance enforcement](./doa-compliance-enforcement.md), which is the control that keeps it inside policy.
- The lowest-risk band is where [low-risk auto-approval](./low-risk-auto-approval.md) takes over entirely.
- Orchestration platforms include [Zip](https://ziphq.com/) and [Tonkean](https://www.tonkean.com/).
