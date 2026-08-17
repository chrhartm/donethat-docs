---
title: Historical performance retrieval
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
value: 2
effort: 3
---
RAG-based retrieval surfaces past delivery, quality, and dispute records for shortlisted suppliers from prior contracts.

## What it is, how it works

Retrieval surfaces what actually happened last time you used a supplier. A retrieval-augmented system searches prior contracts, delivery records, quality incidents, and dispute history, then gives the evaluation panel a summary with links to the underlying documents.

- Retrieval spans systems that don't normally talk to each other, including contract stores, ERP receipt data, and ticketing.
- Every claim in the summary points back to the record it came from.
- Suppliers with no history are reported as unknown rather than scored as neutral.

## When not to use it

- If performance data was never captured, retrieval has nothing to find, and a confident summary built on two records is misleading.
- Old incidents attached to a supplier who has since changed management or ownership can be unfair. Show dates prominently.
- Access rules matter. Dispute and legal records often shouldn't be visible to everyone on an evaluation panel.

## How to get started

- Start with goods receipt and invoice data. It's structured, it already exists, and it covers delivery accuracy and timing without new capture.
- Give the panel retrieval as a research tool before you attempt to score anything automatically.
- Check a few summaries against the source documents. Panels stop trusting the tool permanently after one wrong claim.

## Best practices / further reading

- The receipt-side signal is built by [receipt quality scoring](./receipt-quality-scoring.md), which turns delivery events into a running KPI.
- Retrieved history is one input to the [multi-criteria decision matrix](./multi-criteria-decision-matrix.md), alongside price and risk.
- Supplier performance records live in suites such as [Zycus](https://www.zycus.com/).
