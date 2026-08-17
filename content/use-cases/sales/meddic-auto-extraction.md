---
title: MEDDIC auto-extraction
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
value: 5
effort: 2
---
An LLM extracts metrics, champion, pain, and decision criteria from calls and emails into CRM fields, using tools like Gong or Aviso.

## What it is, how it works

MEDDIC extraction reads call transcripts and email threads for the qualification fields reps are supposed to fill in: metrics, economic buyer, decision criteria, decision process, identified pain, and champion. It writes them to the CRM without anyone retyping the call.

- Extraction quotes the passage supporting each field, so a manager can check the basis.
- Empty fields are reported as gaps, which is the more useful output for coaching.
- Values update as the deal progresses rather than being set once after discovery.

## When not to use it

- Extraction confirms what was said, not what's true. A champion who says they're the economic buyer is recorded as claiming it, not being it.
- If your team doesn't run MEDDIC in practice, populating the fields creates the appearance of qualification without the discipline.
- Using extracted gaps punitively stops reps recording calls, and you lose the input entirely.

## How to get started

- Run it against closed-won and closed-lost deals and compare the field completeness. The difference is the argument for using it.
- Treat gaps as the primary output and surface them before the next call, when they can still be closed.
- Keep the rep able to override any field, with the override visible.

## Best practices / further reading

- Gaps identified here are what [discovery gap analyzer](./discovery-gap-analyzer.md) turns into specific questions for the next call.
- Extracted fields are inputs to [predictive SQL conversion score](./predictive-sql-conversion-score.md) and [deal risk scoring](./deal-risk-scoring.md).
- Conversation platforms that write to CRM fields include [Gong](https://www.gong.io/).
