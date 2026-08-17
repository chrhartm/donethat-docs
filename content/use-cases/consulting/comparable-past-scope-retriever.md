---
title: Comparable Past Scope Retriever
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - consulting
  - scope
  - speed
domain: consulting
domainOrder: 19
stage: scope
stageOrder: 2
outcome:
  - speed
value: 2
effort: 3
---
Embeddings search over past SOWs surfaces effort actuals from comparable engagements by problem type and industry.

## What it is, how it works

Comparable retrieval finds past engagements that resemble the one being scoped, matched on problem type and sector, and surfaces what they actually cost. It answers the question partners ask first: have we done this before, and how did it go.

- Matching runs on problem shape rather than client name or industry label alone.
- Each result carries effort actuals, not the quoted figure.
- Engagements that overran are included prominently, since those are the instructive ones.

## When not to use it

- Confidentiality limits reuse. Some engagements cannot inform others even internally, and the retrieval needs to respect that.
- Superficial similarity misleads. Two supply chain diagnostics can differ by an order of magnitude in effort.
- Without actuals attached, retrieval only tells you that you did something similar, which is not useful.

## How to get started

- Index closed engagements with their actuals and their overrun reasons.
- Show date and team prominently. A comparable from five years ago under different delivery norms is weak evidence.
- Have a partner rate the top three matches. That feedback tunes the similarity model quickly.

## Best practices / further reading

- Retrieval feeds [effort estimation from historical actuals](./effort-estimation-from-historical-actuals.md).
- Indexing depends on [project knowledge base ingestion agent](./project-knowledge-base-ingestion-agent.md) running at close.
- Past engagement records are typically held in [Kantata](https://www.kantata.com/) or a document store.
