---
title: Bid/No-Bid Opportunity Classifier
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - consulting
  - sell
  - cost
domain: consulting
domainOrder: 19
stage: sell
stageOrder: 1
outcome:
  - cost
value: 2
effort: 2
---
ML scores incoming opportunities on strategic fit, capability match, and win probability to filter the pipeline before proposal effort is committed.

## What it is, how it works

Bid screening scores an incoming opportunity before anyone writes a proposal. Fit, capability match, and win probability are learned from your own closed deals. The point is to stop spending partner hours on bids you were never going to win.

- Scoring runs on your win and loss history, not on generic market data.
- The output is a recommendation with reasons, so a partner can override it and say why.
- Low scores route to a short conversation rather than an automatic decline.

## When not to use it

- The model learns from bids you chose to pursue. You have no data on the ones you declined, so it can only rank inside your existing habits.
- Strategic bids break the logic. A loss-making entry into a new sector can be the right call, and no win-probability model will say so.
- Firms with low deal counts will get noise. If you bid twenty times a year, judgment beats the model.

## How to get started

- Backtest on last year's bids. If it cannot separate your wins from your losses, it is not ready.
- Report it as time reallocation, not as pipeline rejection. Partners hear the second one as a threat.
- Track what happened to overridden decisions. That record is what earns the model trust.

## Best practices / further reading

- Losing themes worth encoding as features come from [win loss pattern synthesis](./win-loss-pattern-synthesis.md).
- Opportunities that pass should go straight into [pre-pitch client context brief](./pre-pitch-client-context-brief.md).
- Pipeline data usually lives in the CRM alongside delivery tools such as [Kantata](https://www.kantata.com/).
