---
title: PO anomaly detection
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - procurement
  - order
  - quality
domain: procurement
domainOrder: 1
stage: order
stageOrder: 6
outcome:
  - quality
value: 3
effort: 2
---
ML flags POs where quantity, price, or supplier deviates from the underlying contract or historical category patterns before transmission.

## What it is, how it works

Anomaly detection checks a PO against its contract and against category history before it's transmitted. Quantity, unit price, and supplier are compared with what the contract permits and what similar orders have looked like, and outliers stop for review.

- Contract comparison is deterministic, so price and term breaches are caught with certainty rather than probability.
- Historical comparison catches the cases no contract covers, such as an order ten times the usual size.
- Review happens pre-transmission, which is the only point where correction is cheap.

## When not to use it

- Blocking transmission on a probabilistic flag will interrupt legitimate urgent orders. Separate hard contract breaches from statistical oddities and treat them differently.
- Seasonal categories generate predictable spikes that look anomalous to a model trained on annual averages.
- Without pre-transmission timing this is just reporting, and reporting after the supplier has shipped changes nothing.

## How to get started

- Enforce contract compliance first. It's rule-based, explicable, and catches real money without any model risk.
- Add statistical detection afterward, in warn-only mode, once people trust the deterministic checks.
- Measure how many flagged POs are actually amended. If nothing changes, the threshold is wrong.

## Best practices / further reading

- The contract side depends on [contract terms auto-applied to PO](./contract-terms-auto-applied-to-po.md).
- Sequences engineered around approval limits are the specific case handled by [split PO detection](./split-po-detection.md).
- Order controls are built into [Zip](https://ziphq.com/).
