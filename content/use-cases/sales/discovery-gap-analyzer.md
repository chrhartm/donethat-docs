---
title: Discovery gap analyzer
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - sales
  - discover
  - quality
domain: sales
domainOrder: 1
stage: discover
stageOrder: 3
outcome:
  - quality
value: 1
effort: 1
---
An adversarial pass over transcripts highlights pain points the rep failed to probe.

## What it is, how it works

Gap analysis reads a discovery transcript and asks what the rep failed to probe. It's an adversarial pass rather than a summary: the output is the list of pains mentioned but never explored, and the qualification criteria nobody asked about.

- Analysis looks for absence, which is what summaries by definition miss.
- Each gap cites the moment in the call where the thread was dropped.
- Output is framed as questions for the next conversation.

## When not to use it

- Not every unexplored thread matters. A tool that flags twenty gaps per call gets ignored by the second week.
- Used in performance review it becomes a stick, and reps will stop recording calls rather than improve.
- Short transactional calls do not have enough substance for the analysis to say anything useful.

## How to get started

- Cap it at the three most consequential gaps per call. Fewer, better flags get acted on.
- Send it to the rep only at first, not to the manager. Trust has to come before oversight.
- Check whether flagged gaps get closed on the next call. That's the only measure that matters.

## Best practices / further reading

- Gaps line up with the fields left empty by [MEDDIC auto-extraction](./meddic-auto-extraction.md).
- Scoring the call against a named framework is [methodology scorecard](./methodology-scorecard.md).
- Conversation intelligence tools include [Gong](https://www.gong.io/).
