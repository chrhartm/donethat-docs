---
title: Auto-renew and anomaly detector
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - sales
  - renew
  - speed
domain: sales
domainOrder: 1
stage: renew
stageOrder: 8
outcome:
  - speed
value: 3
effort: 4
---
AI flags auto-renew clauses, price bumps, and missed renewal windows in the contract corpus, using tools like Sirion or LinkSquares.

## What it is, how it works

Renewal anomaly detection reads the contract corpus for auto-renew clauses, price escalators, and notice windows, then flags the dates and terms that will act on their own if nobody intervenes.

- Detection runs across all agreements rather than the ones someone remembered to diarize.
- Notice periods are calculated backward from renewal, which is the date that actually binds.
- Price escalators are surfaced with the resulting number, not just the clause.

## When not to use it

- Extraction accuracy decides everything. A missed notice window means a year of unwanted contract, so keep confidence thresholds strict.
- Non-standard agreements are where the risky clauses live and where extraction is weakest.
- Alerts with no owner expire quietly. That's the exact problem you bought the tool to fix.

## How to get started

- Run it retrospectively over existing contracts. Teams routinely find renewals they did not know were automatic.
- Alert at notice date minus a category-specific buffer, not at renewal date.
- Assign a named owner per contract rather than a shared queue.

## Best practices / further reading

- Extraction quality depends on [signed contract data extraction](./signed-contract-data-extraction.md).
- Precedent for renegotiating unfavorable terms is found via [clause precedent retrieval](./clause-precedent-retrieval.md).
- Contract analytics tools include [LinkSquares](https://www.linksquares.com/).
