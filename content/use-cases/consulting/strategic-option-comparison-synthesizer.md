---
title: Strategic Option Comparison Synthesizer
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - consulting
  - recommend
  - quality
domain: consulting
domainOrder: 19
stage: recommend
stageOrder: 6
outcome:
  - quality
value: 3
effort: 2
---
LLM generates structured tradeoff analysis across strategic options using retrieved precedent cases and client-agreed evaluation criteria.

## What it is, how it works

Option comparison lays out the tradeoffs across strategic choices against criteria the client agreed to, drawing on precedent cases where similar choices played out. It structures the comparison so the discussion is about weighting rather than about what the options even are.

- Criteria come from what the client signed up to, not from a standard framework.
- Precedent cases are retrieved and cited, which is what distinguishes this from a generic matrix.
- Each option's weakest dimension is named explicitly.

## When not to use it

- Structured comparison implies the options are commensurable. Sometimes the real work is arguing that one option is a different kind of choice entirely.
- Criteria agreed early can become the wrong criteria as understanding develops, and the matrix will keep scoring against them.
- Precedent from other companies rarely transfers cleanly, and citing it as evidence overstates what it shows.

## How to get started

- Agree criteria and weights with the client before generating anything.
- Present the weakest dimension of your recommended option first. It builds more credibility than the strengths.
- Show how the ranking changes under different weights.

## Best practices / further reading

- Outcome ranges come from [multi-scenario outcome modeler](./multi-scenario-outcome-modeler.md).
- Stress-test the chosen option with [recommendation adversarial stress tester](./recommendation-adversarial-stress-tester.md).
- Comparison matrices are commonly built in [Airtable](https://airtable.com/).
