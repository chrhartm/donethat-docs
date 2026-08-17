---
title: Proposal Red-Team Reviewer
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - consulting
  - sell
  - quality
domain: consulting
domainOrder: 19
stage: sell
stageOrder: 1
outcome:
  - quality
value: 3
effort: 1
---
LLM stress-tests a draft proposal against likely evaluator objections and scoring criteria, surfacing gaps before submission.

## What it is, how it works

Red teaming argues against your own proposal before an evaluator does. The model plays the skeptical reviewer, tests each section against the stated scoring criteria, and names what a competitor would attack.

- Criticism is scored against the RFP's published criteria rather than general quality.
- Weak claims, unsupported credentials, and vague delivery language are called out specifically.
- The output is a list of objections to answer, not a rewrite.

## When not to use it

- Red teaming a bad proposal produces a long list and no direction. Fix the strategy first, then stress-test it.
- The model does not know the evaluators. Political and relationship factors sit outside what it can see.
- Applied too late it just generates anxiety. Run it while there is still time to change something.

## How to get started

- Feed it the actual scoring rubric. Without that it critiques style instead of scoring risk.
- Ask for the five objections most likely to cost points, not every possible criticism.
- Compare its objections against real evaluator feedback on past bids.

## Best practices / further reading

- Drafts come from [RAG proposal draft generator](./rag-proposal-draft-generator.md).
- Recurring objections belong in [win loss pattern synthesis](./win-loss-pattern-synthesis.md) as a pattern to fix at source.
- Response platforms with review workflows include [Loopio](https://www.loopio.com/).
