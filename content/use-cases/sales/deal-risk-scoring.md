---
title: Deal risk scoring
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - sales
  - negotiate
  - quality
domain: sales
domainOrder: 1
stage: negotiate
stageOrder: 5
outcome:
  - quality
value: 4
effort: 3
---
Machine learning flags slipping deals from email tone, call sentiment, and engagement decay, using tools like Aviso or Clari Copilot.

## What it is, how it works

Deal risk scoring watches engagement rather than the rep's stage field. Email response times, call sentiment, meeting frequency, and the breadth of contact across the buying committee combine into a signal that a deal is slipping before the forecast says so.

- Signals are behavioral and drawn from activity data rather than self-reported status.
- Engagement decay tends to lead stage changes, which is where the early warning comes from.
- Scores name the contributing factors so the rep can act on the specific problem.

## When not to use it

- Enterprise deals go quiet for legitimate reasons, including budget cycles and holidays. A model trained on transactional velocity will scream through every August.
- Scoring that reaches managers before reps turns into an interrogation tool and reps respond by managing the signal.
- Sentiment analysis on calls is weak across accents and languages, and confident sentiment scores deserve suspicion.

## How to get started

- Backtest against deals that slipped last year. If the model flags them in the final week, it adds nothing.
- Show reps their own scores first, with the contributing factors, before any manager view exists.
- Tune per segment. One threshold across transactional and enterprise motions will fit neither.

## Best practices / further reading

- Committee coverage gaps from [buying committee mapping](./buying-committee-mapping.md) are among the strongest inputs.
- The forecast-level view is [probabilistic forecast roll-up](./probabilistic-forecast-roll-up.md).
- Revenue intelligence platforms include [Clari](https://www.clari.com/) and [Aviso](https://www.aviso.com/).
