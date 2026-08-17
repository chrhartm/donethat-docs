---
title: Policy pre-check at intake
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - procurement
  - request
  - quality
domain: procurement
domainOrder: 1
stage: request
stageOrder: 1
outcome:
  - quality
value: 3
effort: 3
---
At submission, AI cross-references the request against approved supplier lists, spend thresholds, and category rules before routing.

## What it is, how it works

Pre-check runs your procurement rules at submission instead of at approval. The request is compared against approved supplier lists, spend thresholds, and category policy, and the requester sees the problem while they still have the context to fix it.

- Checks run synchronously, so the feedback arrives in the form rather than in an email two days later.
- Violations are explained in plain language with the rule that triggered them.
- Clean requests skip straight to routing, which is where most of the cycle-time gain comes from.

## When not to use it

- If your policy is ambiguous or contested, automating it just makes the ambiguity faster. Fix the policy first.
- Hard blocks on edge cases train people to route around procurement entirely. Warn by default, block only where the risk is real.
- Policies that change frequently need an owner for the rule set, otherwise the checker drifts out of date and quietly misfires.

## How to get started

- Write down the five rules that generate the most approval rejections today. Those are the ones worth checking at intake.
- Start in warn-only mode and count how often requesters fix the issue without escalation.
- Review the false-positive log weekly for the first month. Early tuning determines whether people trust it.

## Best practices / further reading

- Requests that pass pre-check cleanly are the natural input for [low-risk auto-approval](./low-risk-auto-approval.md).
- Pre-check catches known rules. Patterns nobody wrote a rule for are the job of [off-contract spend prediction](./off-contract-spend-prediction.md).
