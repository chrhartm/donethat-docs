---
title: Internal contradiction detection
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - procurement
  - evaluate
  - quality
domain: procurement
domainOrder: 1
stage: evaluate
stageOrder: 4
outcome:
  - quality
value: 3
effort: 3
---
AI cross-checks each vendor's executive summary, technical specification, and pricing for logical inconsistencies and flags them before scoring.

## What it is, how it works

Contradiction detection cross-reads the parts of a single bid that are usually reviewed by different people. The executive summary promises a timeline, the technical specification implies a longer one, and the pricing schedule assumes a third. The model finds the mismatch before scoring.

- Comparison runs across sections of the same proposal, not between competing bids.
- Typical findings are timeline, scope, resourcing, and volume assumptions that don't reconcile.
- Each flag quotes both passages so a reviewer can judge in seconds.

## When not to use it

- Not every inconsistency is a problem. Proposals are written by several authors and small mismatches are normal, so treat flags as questions rather than findings.
- Using contradictions to disqualify bidders invites challenge. They're better used to shape clarification questions.
- Very short proposals rarely contain enough material for the check to add anything.

## How to get started

- Apply it to the two or three largest bids in an evaluation, where the document volume defeats careful human cross-reading.
- Route every flag into the clarification round rather than the scoring sheet.
- Log which flags turned out to matter. That's the only way to judge whether the check earns its place.

## Best practices / further reading

- Contradictions found here often explain scoring disagreements surfaced by [proposal scoring against RFP criteria](./proposal-scoring-against-rfp-criteria.md).
- Assumptions that don't reconcile usually move the real cost, which is what [total cost of ownership modeling](./total-cost-of-ownership-modeling.md) is there to capture.
- Proposal analysis features appear in [Inventive AI](https://inventive.ai/).
