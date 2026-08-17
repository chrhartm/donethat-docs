---
title: Pre-Kickoff Readiness Gap Detector
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - consulting
  - kickoff
  - quality
domain: consulting
domainOrder: 19
stage: kickoff
stageOrder: 4
outcome:
  - quality
value: 3
effort: 2
---
LLM verifies data access, stakeholder sign-offs, and environment readiness before day one and surfaces blockers for resolution.

## What it is, how it works

Readiness checking verifies the boring prerequisites before day one: data access granted, stakeholders signed off, environments provisioned, interviews scheduled. These are the things that silently cost the first two weeks of an engagement.

- The checklist is derived from the SOW's own dependencies rather than a generic template.
- Each gap names the owner and what unblocking requires.
- The check runs repeatedly in the run-up, not once.

## When not to use it

- Readiness gaps are usually client-side, and a report the client never sees changes nothing. This needs to become a shared document.
- Small engagements do not have enough setup to justify the tooling.
- A green checklist is not readiness. Access granted on paper and access working are different things.

## How to get started

- Derive the list from dependencies already named in the SOW, which is also a test of whether the SOW named them.
- Share it with the client sponsor weekly before kickoff.
- Verify access by using it, not by confirming it was granted.

## Best practices / further reading

- SOW dependencies are surfaced by [assumption gap detector](./assumption-gap-detector.md).
- Unresolved gaps at day one belong in the [risk register bootstrapper](./risk-register-bootstrapper.md).
- Readiness checklists are commonly shared with clients in [Smartsheet](https://www.smartsheet.com/).
