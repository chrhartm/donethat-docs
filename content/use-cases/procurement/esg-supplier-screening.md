---
title: ESG supplier screening
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - procurement
  - source
  - quality
domain: procurement
domainOrder: 1
stage: source
stageOrder: 3
outcome:
  - quality
value: 2
effort: 3
---
NLP and external data sources classify shortlisted suppliers on sustainability, labor practices, and regulatory compliance.

## What it is, how it works

Screening rates shortlisted suppliers on sustainability, labor practice, and compliance. It reads disclosures, certifications, news, and third-party data. Buyers get a consistent starting point instead of a web search per vendor.

- Sources include public filings, certification registries, adverse media, and commercial ESG data.
- Each supplier gets a per-dimension classification with the underlying evidence attached.
- Screening is continuous where the data allows, so a supplier's position can change between sourcing events.

## When not to use it

- A score isn't a compliance opinion. Where the law imposes a duty to check, the model informs the work. It doesn't do it.
- Media matching trips on common company names. An unreviewed flag can knock out a good supplier for no reason.
- Most of the input is self-reported. So the screen partly measures how well a supplier discloses, not how well they behave.

## How to get started

- Define which dimensions actually gate a decision at your organization. Screening everything produces noise nobody acts on.
- Require the evidence link on every flag. A score with no traceable source won't survive a supplier challenge.
- Give suppliers a route to correct the record. Most disputes are stale data rather than disagreement.

## Best practices / further reading

- Screening pairs naturally with [supplier risk continuous monitoring](./supplier-risk-continuous-monitoring.md), which watches the same suppliers after award.
- Where ESG is a scored award criterion, feed the result into the [multi-criteria decision matrix](./multi-criteria-decision-matrix.md) rather than judging it separately.
- Supplier data platforms with ESG coverage include [Zycus](https://www.zycus.com/).
