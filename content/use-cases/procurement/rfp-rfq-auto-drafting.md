---
title: RFP/RFQ auto-drafting
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - procurement
  - source
  - speed
domain: procurement
domainOrder: 1
stage: source
stageOrder: 3
outcome:
  - speed
value: 3
effort: 2
---
LLM generates an RFP from a structured scope, drawing on clause libraries and past RFPs for the relevant category, using tools like Jaggaer JAI or GEP.

## What it is, how it works

Drafting turns a structured scope into a complete RFP document, pulling clauses from your library and reusing the structure of past events in the same category. The buyer edits a draft rather than starting from a blank template.

- Clause selection is driven by category, value band, and risk profile.
- Prior RFPs supply the section structure and the evaluation criteria that worked before.
- Output stays in your document format so the existing review process is unchanged.

## When not to use it

- A generated RFP inherits whatever is wrong with your clause library. If the library hasn't been reviewed recently, fix that first.
- Novel categories have no precedent to draw on, and the draft will read like a generic template because that's what it is.
- Legal review still applies. Speed at the drafting stage doesn't shorten the approval path for non-standard terms.

## How to get started

- Regenerate an RFP you've already issued and compare. The differences show you what the model gets wrong before it touches a live event.
- Keep the clause library as the single source of truth and generate from it, rather than letting the model write clauses freely.
- Track how much of the draft survives to issue. A high edit rate points at the library, not the model.

## Best practices / further reading

- Requirements written into the RFP should be the same ones checked by [compliance requirement extraction](./compliance-requirement-extraction.md) when bids come back.
- Evaluation criteria defined here become the scoring basis for [proposal scoring against RFP criteria](./proposal-scoring-against-rfp-criteria.md).
- Source-to-contract suites offering this include [GEP](https://www.gep.com/) and [Zycus](https://www.zycus.com/).
