---
title: Meeting-to-Action-Item Agent
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - consulting
  - deliver
  - speed
domain: consulting
domainOrder: 19
stage: deliver
stageOrder: 7
outcome:
  - speed
value: 3
effort: 2
---
LLM transcribes meetings, extracts decisions and owners, and pushes action items directly to the project management tool, using tools like Otter.ai.

## What it is, how it works

Meeting automation transcribes the session, pulls out decisions and owners, and pushes action items into the project tool. It removes the note-taking task that gets skipped when the meeting runs long.

- Decisions and owners are extracted as structured fields, not as a summary paragraph.
- Items are written to the existing board rather than a separate document.
- A consultant confirms before anything is pushed.

## When not to use it

- Recording client meetings requires consent and often a contractual basis, and doing it quietly is a serious breach.
- A written record of every decision changes the engagement's evidentiary position. Legal may have a view on that.
- Actions pushed without review clutter the board and get ignored, which is worse than manual notes.

## How to get started

- Get explicit consent, and say what happens to the recording afterward.
- Keep a review step before items reach the board.
- Measure whether actions get closed, not how many were captured.

## Best practices / further reading

- Requests captured here should be checked by [scope creep detector](./scope-creep-detector.md).
- Decisions captured here feed [lessons learned synthesizer](./lessons-learned-synthesizer.md) at close.
- Transcription tools include [Otter.ai](https://otter.ai/).
