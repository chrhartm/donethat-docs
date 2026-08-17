---
title: Cross-system handoff agent
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - sales
  - handoff
  - speed
domain: sales
domainOrder: 1
stage: handoff
stageOrder: 7
outcome:
  - speed
value: 2
effort: 4
---
An agent transfers opportunity context, contacts, and notes from the CRM to the CS platform, using tools like Gainsight Horizon AI or Vitally AI.

## What it is, how it works

A handoff agent moves the account from the CRM into the customer success platform: contacts, opportunity history, notes, commitments, and documents, mapped into the fields CS actually uses rather than dumped as an attachment.

- Field mapping is explicit, so information lands where CS looks for it.
- Documents and call recordings are linked rather than copied.
- Failures surface as a queue instead of silently dropping records.

## When not to use it

- Integration work is the real cost, and it is usually underestimated. This is a data engineering project wearing an AI label.
- Transferring everything buries CS in noise. Selection is the valuable part, not completeness.
- If CS does not trust the transferred data, they redo discovery with the customer anyway, and you have automated a step nobody uses.

## How to get started

- Ask CS which five fields they currently chase sales for, and transfer only those first.
- Run it alongside the manual handoff for a month and compare what CS actually references.
- Monitor the failure queue rather than the transfer count.

## Best practices / further reading

- The narrative layer is [sales-to-CS handoff briefing](./sales-to-cs-handoff-briefing.md), which is the part humans read.
- Contract terms should arrive via [signed contract data extraction](./signed-contract-data-extraction.md).
- Customer success platforms on the receiving end include [Vitally](https://www.vitally.io/).
