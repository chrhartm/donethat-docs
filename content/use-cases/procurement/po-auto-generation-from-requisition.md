---
title: PO auto-generation from requisition
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - procurement
  - order
  - speed
domain: procurement
domainOrder: 1
stage: order
stageOrder: 6
outcome:
  - speed
value: 1
effort: 3
---
Agentic system creates a PO in the ERP from an approved request and contract terms without manual re-entry, using tools like SAP Ariba or Coupa.

## What it is, how it works

Auto-generation creates the purchase order in the ERP directly from an approved requisition and its contract terms. Nobody retypes what has already been approved, which removes both the delay and the transcription errors that come with re-entry.

- Supplier, pricing, and terms are read from the contract rather than entered by hand.
- The PO posts through the ERP's own interfaces, so existing controls and numbering still apply.
- Failures route to a human queue with the reason attached instead of silently retrying.

## When not to use it

- Generation multiplies whatever is wrong upstream. If requisition data quality is poor, you'll create bad POs faster.
- ERP integration is the real cost here, and it's usually larger than the modeling work. Scope it honestly.
- Categories where the PO genuinely needs human judgment, such as complex services, don't benefit from removing the human.

## How to get started

- Start with catalog purchases against an existing contract. The data is clean and the terms aren't in question.
- Run generation in parallel with manual creation for a two weeks and compare the outputs field by field.
- Watch the exception queue rather than the success rate. Exceptions are where the design problems are.

## Best practices / further reading

- Terms come from [contract terms auto-applied to PO](./contract-terms-auto-applied-to-po.md), which is what makes generation safe.
- Check generated orders with [PO anomaly detection](./po-anomaly-detection.md) before transmission.
- Requisition-to-order automation appears in [Zip](https://ziphq.com/) and [Tonkean](https://www.tonkean.com/).
