---
title: Single-source risk flagging
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - procurement
  - select
  - quality
domain: procurement
domainOrder: 1
stage: select
stageOrder: 5
outcome:
  - quality
value: 2
effort: 2
---
AI detects over-concentration on a supplier or region and recommends dual-source options based on spend share and criticality.

## What it is, how it works

This measures how much of a category, or how much critical supply, rests on one supplier or one region. When exposure crosses a threshold, it names dual-source candidates. It also estimates what qualifying them would take.

- Exposure is computed on spend share and on criticality, which often disagree. A small supplier can be a large risk.
- Geographic concentration is assessed alongside supplier concentration, since separate suppliers in one region aren't diversification.
- Recommendations name specific alternates rather than advising diversification in the abstract.

## When not to use it

- Single-sourcing is sometimes right. If volume buys a price no split award could match, the flag is information, not a problem.
- Qualifying a second supplier costs real money and time, and the model rarely knows those costs.
- Tier-one visibility hides the real risk. Two suppliers fed by one sub-tier plant are not dual sourcing.

## How to get started

- Rank categories by criticality first, then look at concentration. Concentration in a category nobody would miss isn't urgent.
- Set thresholds with the business, not inside procurement. Risk appetite isn't a procurement decision.
- Treat each flag as a question about what a disruption would actually cost.

## Best practices / further reading

- Where concentration is deliberate, [supplier risk continuous monitoring](./supplier-risk-continuous-monitoring.md) is the compensating control.
- Concentration is a scored dimension in the [multi-criteria decision matrix](./multi-criteria-decision-matrix.md).
- Concentration reporting is standard in [Zycus](https://www.zycus.com/).
