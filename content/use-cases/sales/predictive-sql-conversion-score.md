---
title: Predictive SQL conversion score
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - sales
  - qualify
  - quality
domain: sales
domainOrder: 1
stage: qualify
stageOrder: 2
outcome:
  - quality
value: 3
effort: 5
---
Machine learning ranks leads by probability of becoming a sales-qualified opportunity, using tools like MadKudu or Einstein.

## What it is, how it works

Conversion scoring ranks leads by their probability of becoming a qualified opportunity, using fit attributes and behavioral signals learned from your own history. It decides what a rep works first when the queue is longer than the day.

- Fit and behavior are modeled together, since neither predicts well alone.
- Scores are calibrated against actual conversion, so a 70 should mean roughly seventy percent.
- The contributing factors are shown, which is what makes a rep trust the ranking.

## When not to use it

- The model learns from leads reps actually worked, so it inherits their bias. Leads nobody called never got the chance to convert, and the model reads that as failure.
- Low lead volume produces unstable scores that swing week to week.
- Scoring without changing routing changes nothing. The score has to alter who works what.

## How to get started

- Hold out a random sample worked regardless of score. Without it you can never separate model quality from self-fulfilling prophecy.
- Check calibration, not just ranking. A model that orders correctly but is wildly overconfident misleads capacity planning.
- Retrain on a schedule. Conversion patterns shift with the market and the model decays quietly.

## Best practices / further reading

- Fit inputs come from [ICP lookalike account discovery](./icp-lookalike-account-discovery.md).
- Low scores are candidates for [disqualification recommender](./disqualification-recommender.md) rather than automatic rejection.
- Lead scoring platforms include [Pricefx](https://www.pricefx.com/) for pricing and CRM-native scoring for fit.
