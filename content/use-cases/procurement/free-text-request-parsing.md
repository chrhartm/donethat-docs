---
title: Free-text request parsing
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - procurement
  - request
  - speed
domain: procurement
domainOrder: 1
stage: request
stageOrder: 1
outcome:
  - speed
value: 3
effort: 2
---
LLM converts unstructured input, such as "need a laptop for new hire", into a structured requisition with category, budget, and urgency fields.

## What it is, how it works

Intake parsing sits at the front door of procurement. Someone types what they need in plain language, and the model returns the fields your requisition form would otherwise have demanded: category, quantity, budget code, urgency, and a suggested supplier.

- The model maps free text to your requisition schema, not a generic one.
- Per-field confidence scores decide what gets auto-filled and what the requester confirms.
- Past requisitions are the training signal that makes category and supplier guesses useful.

## When not to use it

- Don't auto-submit. Parsing a request isn't approving it, and silent field-filling hides errors until someone in finance finds them months later.
- Low-volume categories rarely justify the setup. A category that sees a handful of requests a year gives the model nothing to learn from.
- Requests carrying personal or contract-sensitive detail need a policy decision about what leaves your tenant before you route free text to a model.

## How to get started

- Take 200 historical requisitions and check what the model would have filled in. That is your accuracy baseline and it costs nothing to produce.
- Ship it as a draft-filler first. Every field stays editable, nothing submits automatically.
- Track how many fields the requester changes. A falling edit rate means it's working. A flat one means your schema mapping is wrong.

## Best practices / further reading

- Route parsed output through [policy pre-check at intake](./policy-pre-check-at-intake.md) before it reaches an approver.
- Feed the structured result into [spend category auto-classification](./spend-category-auto-classification.md) so intake and taxonomy stay consistent.
- Intake platforms that do this include [Zip](https://ziphq.com/) and [Tonkean](https://www.tonkean.com/).
