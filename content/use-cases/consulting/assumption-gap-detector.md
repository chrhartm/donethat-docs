---
title: Assumption Gap Detector
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - consulting
  - scope
  - quality
domain: consulting
domainOrder: 19
stage: scope
stageOrder: 2
outcome:
  - quality
value: 2
effort: 1
---
LLM reviews a draft SOW and flags unstated assumptions likely to cause scope creep or delivery disputes.

## What it is, how it works

Gap detection reads a draft SOW for the things it does not say. Unstated assumptions about data access, client availability, decision rights, and environment readiness are the usual cause of scope disputes, and they are invisible precisely because nobody wrote them down.

- The model looks for absence, which is what a careful read most often misses.
- Each flag names the assumption and the dispute it tends to produce.
- Output is phrased as clauses to consider adding.

## When not to use it

- Not every unstated assumption needs a clause. A SOW that tries to name everything becomes unsignable.
- The model does not know your client relationship. Some assumptions are better handled in conversation than in contract language.
- Flagging thirty gaps guarantees the list gets ignored. Fewer, sharper flags get acted on.

## How to get started

- Run it against SOWs from engagements that went badly. The gaps it finds will look familiar.
- Cap the output at the five assumptions most likely to cause a dispute.
- Feed confirmed clauses back into your SOW template so the same gap does not recur.

## Best practices / further reading

- Drafts come from [SOW drafter from discovery transcript](./sow-drafter-from-discovery-transcript.md).
- Assumptions that survive into delivery are what [scope creep detector](./scope-creep-detector.md) watches against.
- SOW templates are commonly maintained in [Notion](https://www.notion.com/).
