---
title: Invoice data extraction
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - procurement
  - receive
  - speed
domain: procurement
domainOrder: 1
stage: receive
stageOrder: 7
outcome:
  - speed
value: 2
effort: 2
---
LLM and OCR extract line items, amounts, and tax from unstructured supplier invoices regardless of format, using tools like Rossum or Hypatos.

## What it is, how it works

Extraction reads supplier invoices in whatever format they arrive, PDF, scan, or email body, and returns line items, amounts, tax, and references as structured data. It's the step that makes everything downstream in accounts payable possible.

- OCR handles the scan, and a language model handles the layout variation that defeats template-based tools.
- Per-field confidence decides what posts automatically and what a clerk reviews.
- Purchase order references are extracted specifically, since matching depends on them.

## When not to use it

- Tax fields deserve more caution than the rest. An extraction error in a VAT amount becomes a filing problem, not just a data problem.
- Suppliers who send consistent structured invoices are better handled by an e-invoicing connection than by reading their PDFs.
- Handwritten or poorly scanned documents still fail, and a confident wrong number is worse than a rejection.

## How to get started

- Measure straight-through rate per supplier, not overall. A handful of suppliers usually account for most of the exceptions.
- Set the confidence threshold by field. Amounts warrant a stricter bar than descriptions.
- Push the worst offenders toward structured invoicing. Extraction is a workaround for a format problem you can sometimes just fix.

## Best practices / further reading

- Extracted data is the input to [three-way match automation](./three-way-match-automation.md), which is where the value is realized.
- Extraction errors show up as exceptions in [PO anomaly detection](./po-anomaly-detection.md).
- Tools in this space include [Hypatos](https://hypatos.ai/) and Rossum.
