---
title: Agentic Re-Staffing on Scope Change
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - consulting
  - staff
  - speed
domain: consulting
domainOrder: 19
stage: staff
stageOrder: 3
outcome:
  - speed
value: 5
effort: 5
---
Agent detects scope change events, re-runs staffing optimization across the portfolio, and flags required consultant swaps for approval.

## What it is, how it works

Re-staffing responds to a scope change by recomputing the staffing plan across the portfolio and proposing the swaps required. Scope changes ripple, and the ripple is usually handled by whoever notices first.

- The agent detects the change from SOW amendments and project data rather than waiting for a request.
- Proposed swaps account for the knock-on effect on other engagements.
- Every change is proposed for approval, never executed.

## When not to use it

- This is the most invasive automation in the staffing set. Moving people between clients affects relationships and careers, and it must stay a human decision.
- Portfolio-wide optimization can produce a technically optimal plan that is socially impossible.
- Frequent re-staffing damages delivery. Stability has a value the model cannot see.

## How to get started

- Run it in advisory mode for two quarters and compare its proposals against what resourcing actually did.
- Add a stability penalty so the agent prefers plans that move fewer people.
- Require partner approval on any move affecting a client-facing lead.

## Best practices / further reading

- Capacity signals come from [utilization and bench risk predictor](./utilization-and-bench-risk-predictor.md).
- Fit scoring for replacements comes from [skills to project matching engine](./skills-to-project-matching-engine.md).
- Portfolio resourcing tools include [Float](https://www.float.com/) and [Runn](https://www.runn.io/).
