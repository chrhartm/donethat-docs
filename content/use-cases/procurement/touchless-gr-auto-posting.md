---
title: Touchless GR auto-posting
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - procurement
  - receive
  - speed
domain: procurement
domainOrder: 1
stage: receive
stageOrder: 7
outcome:
  - speed
value: 3
effort: 4
---
When three-way match passes, an agentic system posts the goods receipt in the ERP and triggers the payment workflow without human intervention.

## What it is, how it works

Touchless posting completes the receipt in the ERP and releases the payment workflow when the three-way match passes cleanly. It's the last step of the order-to-pay chain, and it only makes sense once everything before it is reliable.

- Posting is conditional on a clean match, with no tolerance applied at this stage.
- The agent acts through ERP interfaces, so standard authorization and audit apply.
- Anything that doesn't post cleanly goes to a human queue rather than retrying.

## When not to use it

- This is the last automation to build, not the first. Automating posting on top of an unreliable match propagates errors straight into payment.
- Physical verification still matters for some categories. A clean document match isn't evidence that the right goods arrived.
- Segregation of duties needs review before deployment. If one system now raises, receives, and pays, the control design has changed and audit will say so.

## How to get started

- Confirm the match rate is stable and well understood before enabling posting.
- Enable it for one supplier with clean history and high volume, then widen slowly.
- Sample posted receipts against physical stock monthly. Document-only assurance drifts without a physical check.

## Best practices / further reading

- The precondition is [three-way match automation](./three-way-match-automation.md) operating reliably.
- Exceptions that block posting are classified by [delivery discrepancy classification](./delivery-discrepancy-classification.md).
- Touchless posting depends on the ERP and suites such as [Zycus](https://www.zycus.com/).
