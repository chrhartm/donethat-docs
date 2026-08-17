---
title: Reusable Case Study Drafter
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - consulting
  - close
  - speed
domain: consulting
domainOrder: 19
stage: close
stageOrder: 8
outcome:
  - speed
value: 1
effort: 1
---
LLM generates an anonymized client case study from project deliverables and outcomes, structured for BD and proposal reuse.

## What it is, how it works

Case study drafting produces an anonymized account of an engagement from its deliverables and outcomes, structured for proposal and business development reuse. Case studies are usually written months late by someone who was not there.

- The draft pulls problem, approach, and outcome from actual project artifacts.
- Client-identifying detail is stripped, with the specifics flagged for a human to check.
- Structure matches how proposals actually use case studies.

## When not to use it

- Anonymization is easy to get wrong. A sector, size, and geography combination can identify a client as surely as their name.
- Client consent is often required by the engagement terms, whatever the anonymization.
- Outcome claims need to be defensible. A generated benefit figure you cannot substantiate is a claim you should not make.

## How to get started

- Check the engagement terms on publicity before drafting.
- Have a partner who worked on the engagement verify the anonymization, not just the content.
- State outcomes only where the project measured them.

## Best practices / further reading

- Source material comes from [project knowledge base ingestion agent](./project-knowledge-base-ingestion-agent.md).
- Finished case studies are what [RAG proposal draft generator](./rag-proposal-draft-generator.md) retrieves.
- Case study libraries are commonly kept in [Notion](https://www.notion.com/).
