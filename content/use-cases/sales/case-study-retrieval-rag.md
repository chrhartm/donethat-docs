---
title: Case-study retrieval RAG
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - sales
  - propose
  - quality
domain: sales
domainOrder: 1
stage: propose
stageOrder: 4
outcome:
  - quality
value: 3
effort: 3
---
Retrieval-augmented generation pulls vertical-matched proof points from the sales-asset library on demand, using tools like Highspot or Seismic.

## What it is, how it works

Retrieval pulls the right proof point out of the asset library on demand: a customer story in the same vertical, at a similar size, solving the problem this prospect described. Reps stop sending whichever case study they happen to remember.

- Retrieval matches on vertical, size, and use case rather than keyword overlap.
- Approved assets only, so nothing unreviewed reaches a customer.
- Results include why each asset was matched, which helps the rep frame it.

## When not to use it

- Retrieval cannot invent proof you do not have. A thin library returns weak matches confidently, and reps learn to stop asking.
- Customer references carry usage restrictions. A system that ignores which logos may be named publicly creates a real problem.
- Stale case studies get resurfaced indefinitely unless something expires them.

## How to get started

- Audit the library first. Most teams find fewer usable assets than they assumed.
- Tag by vertical, size, and problem rather than by product line, since that is how reps search.
- Track which retrieved assets actually get sent. Low usage points at the library, not the retrieval.

## Best practices / further reading

- Retrieved proof drops into drafts from [auto-drafted proposal](./auto-drafted-proposal.md).
- Gaps in coverage are worth feeding back to marketing as a content brief.
- Which proof points win is visible through [win loss reason classifier](./win-loss-reason-classifier.md).
- Sales content platforms include [Seismic](https://seismic.com/).
