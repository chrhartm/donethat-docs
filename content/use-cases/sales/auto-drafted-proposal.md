---
title: Auto-drafted proposal
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - sales
  - propose
  - speed
domain: sales
domainOrder: 1
stage: propose
stageOrder: 4
outcome:
  - speed
value: 4
effort: 2
---
AI generates SOWs and proposals from CRM opportunity data using approved templates, with tools like PandaDoc AI or Proposify.

## What it is, how it works

Proposal drafting assembles the SOW or proposal from CRM opportunity data using approved templates, so the rep starts from a populated document rather than last quarter's file with the wrong client name still in it.

- Scope, pricing, and terms are pulled from the opportunity record rather than retyped.
- Template selection follows deal type and size, which is where most manual errors occur.
- Non-standard terms are flagged for review instead of being quietly included.

## When not to use it

- Generated proposals inherit CRM data quality. Wrong opportunity data becomes a wrong document sent to a customer, which is a worse failure than an empty field.
- Complex custom scopes need drafting rather than assembly, and templating them produces documents that misdescribe the work.
- Approval workflow still applies. Faster drafting does not mean faster signature, and expecting it creates friction with legal and finance.

## How to get started

- Start with your most standard deal shape, where the template genuinely fits.
- Compare generated drafts against the last ten sent proposals and count the edits.
- Keep pricing locked to approved bands rather than freely generated.

## Best practices / further reading

- Pricing should come from [pricing recommendation engine](./pricing-recommendation-engine.md) rather than rep discretion.
- Proof points are inserted by [case study retrieval RAG](./case-study-retrieval-rag.md).
- The quantified value section is built by [ROI business case generator](./roi-business-case-generator.md).
- Document automation tools include [Proposify](https://www.proposify.com/).
