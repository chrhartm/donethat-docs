---
title: Scope Creep Detector
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - consulting
  - deliver
  - cost
domain: consulting
domainOrder: 19
stage: deliver
stageOrder: 7
outcome:
  - cost
value: 3
effort: 2
---
LLM compares incoming client requests and meeting notes against the original SOW and flags out-of-scope items in real time.

## What it is, how it works

Creep detection compares incoming client requests against the signed SOW and flags what falls outside it, while the request is still fresh. Scope creep is rarely one big ask. It is twenty small ones nobody logged.

- Requests are checked against SOW deliverables and exclusions as they arrive.
- Each flag quotes the SOW language it falls outside.
- Output is a change-request prompt, not a refusal.

## When not to use it

- Reflexively refusing small requests damages the relationship more than absorbing them costs. The flag informs a judgment about goodwill.
- A SOW with vague deliverables cannot support this check, and the model will flag things that were arguably always in scope.
- Used to build a case against a client rather than to manage scope, it poisons the engagement.

## How to get started

- Route flags to the engagement lead, never to the client automatically.
- Track cumulative flagged effort rather than individual requests. The total is the argument.
- Raise it at the next milestone conversation rather than request by request.

## Best practices / further reading

- Clear exclusions upstream make this work, via [assumption gap detector](./assumption-gap-detector.md).
- Accumulated creep shows up as delivery risk in [workstream delivery risk predictor](./workstream-delivery-risk-predictor.md).
- Change requests are commonly tracked in [Jira](https://www.atlassian.com/software/jira) or [Wrike](https://www.wrike.com/).
