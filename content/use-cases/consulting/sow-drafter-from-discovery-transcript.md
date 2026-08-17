---
title: SOW Drafter from Discovery Transcript
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - consulting
  - scope
  - speed
domain: consulting
domainOrder: 19
stage: scope
stageOrder: 2
outcome:
  - speed
value: 3
effort: 2
---
LLM extracts deliverables, exclusions, and assumptions from a discovery call transcript and drafts a structured SOW.

## What it is, how it works

SOW drafting turns a discovery call into a structured scope document. Deliverables, exclusions, assumptions, and dependencies are extracted from what was actually said, which is usually more precise than what anyone remembers a week later.

- Extraction targets the SOW's own sections rather than producing a call summary.
- Exclusions get pulled out explicitly, since those are what prevent disputes later.
- Anything discussed vaguely is flagged as needing confirmation rather than written as agreed.

## When not to use it

- A draft SOW is a commercial document. Sending one that captures a misheard commitment creates a real liability.
- Recording client calls needs consent and often a contractual basis. Settle that before deployment.
- Discovery calls that stayed at a high level do not contain a scope, and the draft will invent specificity that nobody agreed to.

## How to get started

- Draft from a call where you already have a signed SOW and compare the two.
- Require a partner to confirm the exclusions section explicitly. That single step prevents most scope disputes.
- Keep effort and price out of the generated draft.

## Best practices / further reading

- Run the draft through [assumption gap detector](./assumption-gap-detector.md) before it reaches the client.
- Effort figures should come from [effort estimation from historical actuals](./effort-estimation-from-historical-actuals.md), not from the transcript.
- Transcription tools include [Otter.ai](https://otter.ai/), and signature flows run through [DocuSign](https://www.docusign.com/).
