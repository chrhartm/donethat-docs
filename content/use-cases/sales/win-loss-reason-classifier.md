---
title: Win/loss reason classifier
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - sales
  - close
  - quality
domain: sales
domainOrder: 1
stage: close
stageOrder: 6
outcome:
  - quality
value: 2
effort: 1
---
AI categorizes closed deals by reason from communications history and updates competitive intel.

## What it is, how it works

Win-loss classification reads the communication history of closed deals and categorizes why they ended as they did, rather than relying on the reason code a rep picked from a dropdown while closing the record.

- Classification uses the actual conversation, so it catches reasons reps do not select.
- Competitive intelligence is extracted as a side effect, including who you lose to and on what.
- Patterns aggregate by segment, which is where the actionable signal is.

## When not to use it

- The stated reason is rarely the real reason. Buyers say price when they mean value, and the model reads what was said.
- Loss reasons touch rep performance, and analysis that reads as blame will be resisted.
- Small deal counts produce patterns that are noise, and acting on them is worse than not looking.

## How to get started

- Compare model classifications against rep-selected reason codes. The gap is the finding.
- Segment before concluding. Aggregate loss reasons across different motions hide more than they show.
- Feed conclusions to product and marketing, not only to sales.

## Best practices / further reading

- Losses attributed to unanswered questionnaires point at [security and RFP auto-responder](./security-and-rfp-auto-responder.md).
- Qualification-stage losses suggest tuning [disqualification recommender](./disqualification-recommender.md).
- Conversation history for this analysis usually comes from [Gong](https://www.gong.io/).
