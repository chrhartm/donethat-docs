---
title: Lessons Learned Synthesizer
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - consulting
  - close
  - quality
domain: consulting
domainOrder: 19
stage: close
stageOrder: 8
outcome:
  - quality
value: 2
effort: 1
---
LLM compiles a structured postmortem from project artifacts, timesheets, and meeting notes without manual facilitation.

## What it is, how it works

This builds the story of an engagement from what it left behind. Booked hours against the estimate, missed dates, the issue log, meeting notes. You get a draft retrospective without booking the session nobody has time for.

- The gap between quoted and actual hours is computed, not recalled.
- Issues are grouped by cause rather than listed chronologically.
- The output is a draft the team corrects, which is a much lower bar than writing one.

## When not to use it

- A postmortem that reads like a review makes teams defensive. The document is then worthless.
- The artifacts miss the real reasons. A soured client rarely shows up on a task board.
- A generated retrospective nobody discusses changes nothing. The conversation is the mechanism.

## How to get started

- Generate the draft, then run a short session to correct it. That is faster and better than either alone.
- Lead with estimate variance, since it is factual and immediately useful for pricing.
- Feed conclusions into the risk register template so the next engagement inherits them.

## Best practices / further reading

- Output seeds [risk register bootstrapper](./risk-register-bootstrapper.md) on future engagements.
- Effort variance improves [effort estimation from historical actuals](./effort-estimation-from-historical-actuals.md).
- Retrospectives are commonly written up in [Notion](https://www.notion.com/).
