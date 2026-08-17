---
title: Agentic Research and Synthesis Agent
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - consulting
  - analyze
  - speed
domain: consulting
domainOrder: 19
stage: analyze
stageOrder: 5
outcome:
  - speed
value: 5
effort: 4
---
Multi-step agent runs web and internal document research and produces structured findings briefs for consultant review, using tools like McKinsey Lilli.

## What it is, how it works

A research agent runs multi-step investigation across public sources and internal documents, then produces a findings brief with citations. It compresses the desk research that fills the first week of most engagements.

- The agent plans its own search steps rather than answering a single query.
- Findings carry source links so a consultant can verify each claim.
- Internal documents are searched alongside public sources, which is what makes it firm-specific.

## When not to use it

- Every claim needs checking before it reaches a client. An agent that fabricates a plausible statistic will do so confidently, and the citation may not say what the brief claims.
- Client confidential material used as research input can leak across engagements unless access control is enforced properly.
- Fast synthesis of the wrong question wastes the week just as thoroughly as slow research would.

## How to get started

- Require a source link on every finding and spot-check a sample against the sources.
- Run it against a question you have already answered and compare the brief with what your team produced.
- Enforce engagement-level access boundaries on internal material before switching it on.

## Best practices / further reading

- Structure the research around branches from [MECE hypothesis tree generator](./mece-hypothesis-tree-generator.md).
- Document extraction at scale is handled by [unstructured document extraction pipeline](./unstructured-document-extraction-pipeline.md).
- Findings are commonly collected in [Notion](https://www.notion.com/).
