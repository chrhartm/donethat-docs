---
title: Consultant Preference and Interest Matcher
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - consulting
  - staff
  - quality
domain: consulting
domainOrder: 19
stage: staff
stageOrder: 3
outcome:
  - quality
value: 1
effort: 2
---
LLM reads unstructured bios and engagement history to surface soft-fit signals alongside hard-skill matching for role assignments.

## What it is, how it works

Preference matching reads bios, past engagement choices, and stated interests to surface soft-fit signals next to hard-skill matching. Two consultants can be equally qualified while only one actually wants the work, and that difference shows up in delivery.

- Signals come from unstructured text: bios, development conversations, engagement feedback.
- Interest is presented alongside capability, never blended into one score.
- The output is a prompt for a conversation, not an assignment.

## When not to use it

- Inferring what someone wants from their history is guesswork, and it can trap people in work they did once and never want to repeat.
- Career development data is sensitive. Using it for resourcing without saying so breaks trust badly.
- Asking people directly is cheaper and more accurate. Use the model where asking does not scale.

## How to get started

- Tell consultants their stated interests inform staffing, and let them correct the record.
- Keep it advisory next to hard-skill matching rather than an input to a combined score.
- Compare inferred interest against a short survey. If the model disagrees with people, believe people.

## Best practices / further reading

- Hard-skill fit is handled by [skills to project matching engine](./skills-to-project-matching-engine.md).
- Interview structure for role fit comes from [role specific interview question generator](./role-specific-interview-question-generator.md).
- Profile and development records are often kept in [Notion](https://www.notion.com/).
