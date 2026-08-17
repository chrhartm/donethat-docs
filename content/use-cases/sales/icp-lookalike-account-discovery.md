---
title: ICP lookalike account discovery
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - sales
  - prospect
  - quality
domain: sales
domainOrder: 1
stage: prospect
stageOrder: 1
outcome:
  - quality
value: 3
effort: 2
---
Embedding search over firmographic data finds accounts matching the closed-won profile, using tools like Clay or 6sense.

## What it is, how it works

Lookalike discovery starts from the accounts you've actually won and finds others that resemble them. Embedding search over firmographic and technographic data ranks the market by similarity to your closed-won profile, rather than by whoever happens to be in your CRM already.

- The closed-won set defines the profile, so the model reflects who buys rather than who you targeted.
- Similarity spans industry, size, tech stack, and growth signals rather than a single filter.
- Output is a ranked list with the matching attributes shown per account.

## When not to use it

- With few closed-won accounts the profile is noise. Early-stage teams are better served by explicit hypotheses than by a model fitted to a dozen deals.
- Lookalikes reproduce your existing bias. If you've only sold to one vertical, the model will tell you to keep selling there, including when that's the wrong strategy.
- Fit is not intent. A perfect-fit account with no active need is still a cold call.

## How to get started

- Exclude churned accounts from the training set. Lookalikes of customers who left are not a target list.
- Check the top twenty against a rep's judgment. Disagreements usually reveal a qualification criterion nobody wrote down.
- Split by win rate rather than logo count, so large one-off wins don't distort the profile.

## Best practices / further reading

- Combine fit with timing from [buying signal trigger monitoring](./buying-signal-trigger-monitoring.md) before anyone does outreach.
- Ranked accounts feed [predictive SQL conversion score](./predictive-sql-conversion-score.md) once they enter the funnel.
- Account data platforms include [Clay](https://www.clay.com/).
