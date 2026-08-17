---
title: Save-play recommender
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - sales
  - renew
  - quality
domain: sales
domainOrder: 1
stage: renew
stageOrder: 8
outcome:
  - quality
value: 2
effort: 3
---
AI retrieves successful retention playbooks from past saves matched to the current risk pattern.

## What it is, how it works

Save play recommendation matches an at-risk account against past saves with a similar risk pattern and suggests what worked. It converts institutional memory about retention into something a new CSM can use.

- Matching is on risk pattern rather than on account size or industry.
- Recommendations include what was tried and what the outcome was, including the failures.
- Plays are drawn from your own history, so they reflect what works for your product.

## When not to use it

- Survivorship bias is severe here. You remember the saves, and the accounts where the same play failed are underrepresented in the record.
- A play that worked once is not evidence. Small samples produce confident nonsense.
- Discount-based saves are easy to recommend and expensive to normalize, and the model will find them because they worked.

## How to get started

- Record failed saves as deliberately as successful ones. Without them the recommendations are useless.
- Exclude discount plays from recommendations unless a human explicitly asks for them.
- Track cost per save, not just save rate. A retained account bought with margin may not be worth retaining.

## Best practices / further reading

- Risk patterns come from [churn risk prediction model](./churn-risk-prediction-model.md).
- Where the risk is a lost sponsor, [champion departure monitoring](./champion-departure-monitoring.md) names the specific play.
- Retention playbooks live in platforms such as [ChurnZero](https://www.churnzero.com/).
