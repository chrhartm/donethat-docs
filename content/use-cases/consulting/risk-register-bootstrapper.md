---
title: Risk Register Bootstrapper
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - consulting
  - kickoff
  - quality
domain: consulting
domainOrder: 19
stage: kickoff
stageOrder: 4
outcome:
  - quality
value: 2
effort: 2
---
LLM generates an initial risk register with likelihood and impact scores drawn from comparable project postmortems.

## What it is, how it works

Register bootstrapping produces a starting risk register from comparable past engagements, with likelihood and impact drawn from what actually went wrong before. It replaces the blank template that gets filled in with three generic risks and never revisited.

- Risks are retrieved from postmortems of similar engagements, not from a standard list.
- Likelihood reflects how often the risk actually materialized in your own history.
- Mitigations that worked before are attached to each risk.

## When not to use it

- A generated register nobody reviews is worse than a short one the team owns. The register is a habit, not a document.
- Without real postmortem history the output is generic risk boilerplate.
- Long registers dilute attention. Ten risks tracked beats forty listed.

## How to get started

- Cap the initial register at ten risks and make the team cut or keep each one.
- Draw likelihood from your own postmortems rather than from judgment.
- Review it at every milestone. A register updated once is decoration.

## Best practices / further reading

- Source material comes from [lessons learned synthesizer](./lessons-learned-synthesizer.md) on past engagements.
- Readiness gaps still open at kickoff belong here, via [pre-kickoff readiness gap detector](./pre-kickoff-readiness-gap-detector.md).
- Registers are commonly tracked in [Smartsheet](https://www.smartsheet.com/) or [monday.com](https://monday.com/).
