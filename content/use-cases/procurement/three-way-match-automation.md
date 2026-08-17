---
title: Three-way match automation
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - procurement
  - receive
  - cost
domain: procurement
domainOrder: 1
stage: receive
stageOrder: 7
outcome:
  - cost
value: 5
effort: 5
---
AI matches PO, goods receipt, and invoice across structured and unstructured formats, flags discrepancies, and routes exceptions, using tools like Coupa or SAP.

## What it is, how it works

Three-way match reconciles the purchase order, the goods receipt, and the invoice. AI extends the classic control to documents that aren't structured, tolerates the small differences that shouldn't stop a payment, and routes genuine discrepancies to whoever can resolve them.

- Matching runs across formats, so a scanned invoice can be matched against an ERP receipt without manual keying.
- Tolerances are configurable by category and value, since a rounding difference isn't a quantity dispute.
- Exceptions are classified by type, which is what makes them routable rather than just visible.

## When not to use it

- This is a financial control before it's an efficiency measure. Widening tolerances to raise the match rate weakens the control, and that trade needs finance to agree explicitly.
- Services without a goods receipt don't have three documents to match, and forcing the pattern creates fake receipts.
- Partial and consolidated deliveries break naive matching. Check how your suppliers actually ship before assuming a clean one-to-one.

## How to get started

- Quantify the current exception rate and what causes it. Most exceptions trace to a few suppliers or one process gap.
- Set tolerances with finance in writing, and review them on a schedule.
- Automate the clean matches first and leave every exception with a human until the classification is proven.

## Best practices / further reading

- Match quality depends on [invoice data extraction](./invoice-data-extraction.md) upstream.
- A passing match is the trigger for [touchless GR auto-posting](./touchless-gr-auto-posting.md).
- Price discrepancies often trace back to [contract terms auto-applied to PO](./contract-terms-auto-applied-to-po.md).
