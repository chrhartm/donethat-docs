---
title: Effort Estimation from Historical Actuals
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - consulting
  - scope
  - cost
domain: consulting
domainOrder: 19
stage: scope
stageOrder: 2
outcome:
  - cost
value: 4
effort: 5
---
ML predicts task-level hours from scope inputs trained on the firm's historical project actuals and delivery patterns.

## What it is, how it works

Effort estimation predicts task-level hours from scope inputs, trained on what your engagements actually consumed rather than what they were quoted at. It exists because quoted hours and delivered hours diverge, and only one of them is in the proposal.

- Training data is timesheet actuals, so the model learns your real delivery cost.
- Predictions come with a range, because a point estimate on a bespoke engagement is false precision.
- Comparable past engagements are shown alongside, which is what makes the number arguable.

## When not to use it

- Timesheet data is often poor. If consultants book time in round numbers to the wrong codes, the model learns fiction.
- Genuinely novel work has no comparable history, and the model will anchor to something superficially similar.
- Estimates used to pressure delivery teams rather than to price work will corrupt the timesheets it depends on.

## How to get started

- Audit timesheet quality before anything else. This determines whether the project is feasible at all.
- Predict on completed engagements and compare against actuals. Consistent bias is correctable.
- Publish the range, never the midpoint alone.

## Best practices / further reading

- Comparable engagements are retrieved by [comparable past scope retriever](./comparable-past-scope-retriever.md).
- High-risk scope elements from [scope risk classifier](./scope-risk-classifier.md) deserve wider ranges.
- Timesheet actuals come from tools such as [Harvest](https://www.harvestapp.com/) or [Kantata](https://www.kantata.com/).
