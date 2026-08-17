---
title: Recommendation Adversarial Stress-Tester
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - consulting
  - recommend
  - quality
domain: consulting
domainOrder: 19
stage: recommend
stageOrder: 6
outcome:
  - quality
value: 3
effort: 1
---
LLM challenges draft recommendations against client political constraints, implementation risks, and likely senior-stakeholder pushback.

## What it is, how it works

Stress testing argues against your own recommendation before the client does. The model plays the skeptical executive: raising implementation risk, political obstacles, and the objections a senior stakeholder is likely to open with.

- Objections are generated from the client's own context rather than from general risk categories.
- Each objection comes with the answer you would need, which is the actionable part.
- Weak evidence in the recommendation is called out specifically.

## When not to use it

- Stress-testing a recommendation you have not finished thinking through generates noise. Get the argument straight first.
- The model does not know the room. Personal history between stakeholders drives more objections than logic does.
- Run too late it produces anxiety rather than improvement.

## How to get started

- Feed it the client's stated constraints and known stakeholder positions.
- Ask for the three objections most likely to derail the meeting, not an exhaustive list.
- Rehearse the answers out loud. An unrehearsed answer to a predicted objection still fails.

## Best practices / further reading

- Political context comes from [client organizational readiness classifier](./client-organizational-readiness-classifier.md).
- The same adversarial approach applied to proposals is [proposal red team reviewer](./proposal-red-team-reviewer.md).
- General-purpose assistants used for adversarial review include [Claude](https://www.anthropic.com/).
