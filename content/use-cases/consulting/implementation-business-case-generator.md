---
title: Implementation Business Case Generator
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - consulting
  - recommend
  - cost
domain: consulting
domainOrder: 19
stage: recommend
stageOrder: 6
outcome:
  - cost
value: 4
effort: 2
---
LLM and rules engine builds NPV, payback, and sensitivity analysis from recommendation inputs and client financial parameters.

## What it is, how it works

This builds the money argument for a recommendation. Net present value, payback, and sensitivity, using the client's own cost of capital. It is the artifact a CFO needs before approving anything.

- The inputs come from the client, not from defaults.
- Assumptions are listed separately from results, because that is what gets challenged.
- Sensitivity shows which assumptions the case actually depends on.

## When not to use it

- Overstated benefits die in the first finance review, and they take your credibility with them. Careful cases survive.
- Some recommendations are not justified financially, and forcing a case onto a compliance or capability argument looks naive.
- A case built on benefit estimates the client does not recognize will be dismissed regardless of the arithmetic.

## How to get started

- Source every input and show where it came from. Untraceable numbers do not survive finance.
- Lead with the conservative case and keep the upside as upside.
- Ask the client's finance team to review the assumptions before the recommendation meeting.

## Best practices / further reading

- Outcome modeling feeds this via [multi-scenario outcome modeler](./multi-scenario-outcome-modeler.md).
- Whether the client can actually execute is assessed by [client organizational readiness classifier](./client-organizational-readiness-classifier.md).
- Case models are usually shared as spreadsheets via [Dropbox](https://www.dropbox.com/) or an equivalent.
