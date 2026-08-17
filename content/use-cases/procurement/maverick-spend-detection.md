---
title: Maverick spend detection
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - procurement
  - review
  - cost
domain: procurement
domainOrder: 1
stage: review
stageOrder: 8
outcome:
  - cost
value: 5
effort: 2
---
ML detects spend occurring outside contracted suppliers or approved channels and quantifies the financial impact for CPO reporting.

## What it is, how it works

Maverick detection finds spend that happened outside contracted suppliers or approved channels, then quantifies what it cost. Off-contract buying is usually invisible in aggregate reporting because it's spread across many small transactions in the right categories.

- Detection compares actual transactions against contract coverage per category, not just against a preferred supplier list.
- Impact is priced against the contracted rate that should have applied, which turns a compliance finding into a number.
- Results roll up by category and business unit, since that's where the fix has to happen.

## When not to use it

- Off-contract often means no suitable contract exists. Reporting it as non-compliance when it's a coverage gap makes procurement look out of touch.
- Naming individuals turns a process problem into a personnel one and reliably stops cooperation.
- If contract data is incomplete, everything uncovered looks like leakage. Establish coverage before measuring compliance against it.

## How to get started

- Start with your largest categories by transaction count rather than value. That's where fragmented off-contract buying accumulates.
- Separate the finding into no-contract-exists and contract-ignored. The two need entirely different responses.
- Report the trend rather than the absolute number. The direction is what tells you if interventions are working.

## Best practices / further reading

- Coverage gaps found here are sourcing work, which is where [category opportunity identification](./category-opportunity-identification.md) picks up.
- The forward-looking counterpart at intake is [off-contract spend prediction](./off-contract-spend-prediction.md).
- Off-contract analysis is a standard feature in [Sievo](https://sievo.com/) and [Suplari](https://www.suplari.com/).
