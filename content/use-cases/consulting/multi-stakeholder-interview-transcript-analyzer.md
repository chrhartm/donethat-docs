---
title: Multi-Stakeholder Interview Transcript Analyzer
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - consulting
  - analyze
  - quality
domain: consulting
domainOrder: 19
stage: analyze
stageOrder: 5
outcome:
  - quality
value: 4
effort: 2
---
LLM extracts themes, contradictions, and sentiment signals across multiple stakeholder interview transcripts simultaneously.

## What it is, how it works

This reads a whole set of interviews at once. It reports the themes, the places people disagree, and how views split by role. Read thirty transcripts one at a time and the disagreements are what you lose.

- Analysis runs across interviews rather than summarizing each one.
- Contradictions between stakeholders are the headline output, since those locate the real problem.
- Themes are reported with the quotes supporting them.

## When not to use it

- You promised interviewees something about confidentiality. Analysis that makes one person's view identifiable can break that promise.
- Sentiment scoring is weak across accents and languages. Be suspicious of a confident score.
- Themes are only as good as your sample. A skewed sample gives you a confident, skewed picture.

## How to get started

- Confirm what you told interviewees about attribution, and configure the output to match.
- Ask for contradictions first. Themes are easy to spot manually, disagreements are not.
- Check the top themes against the interviewer's own read before presenting anything.

## Best practices / further reading

- Themes should map back to branches in [MECE hypothesis tree generator](./mece-hypothesis-tree-generator.md).
- Contradictions often reveal readiness problems, assessed by [client organizational readiness classifier](./client-organizational-readiness-classifier.md).
- Recording and extraction tooling includes [Otter.ai](https://otter.ai/).
