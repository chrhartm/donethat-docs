---
title: Follow-On Opportunity Signal Detector
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
value: 3
effort: 2
---
LLM scans final deliverables and client conversations for unresolved problems that signal expansion or follow-on opportunities.

## What it is, how it works

Follow-on detection reads final deliverables and late-engagement conversations for problems you identified but did not solve. Those unresolved threads are the most natural next engagement, and they are usually forgotten a week after close.

- Detection looks for named problems that fell outside scope rather than general opportunity language.
- Each signal cites where the problem was raised.
- Output goes to the engagement partner, framed as a client conversation rather than a pipeline entry.

## When not to use it

- Pitching at close can read as mining the relationship, particularly if delivery was rocky. Read the room first.
- Problems left out of scope were sometimes left out for good reasons the model cannot see.
- A follow-on pushed before the current engagement lands well damages both.

## How to get started

- Run it after final delivery is accepted, not before.
- Route to the partner as a suggested conversation, never into a CRM as a qualified lead.
- Track which follow-ons the client actually wanted, and tune from that.

## Best practices / further reading

- Relationship state should gate the approach, per [post-delivery relationship health monitor](./post-delivery-relationship-health-monitor.md).
- Qualified opportunities go through [bid no bid opportunity classifier](./bid-no-bid-opportunity-classifier.md) like any other.
- Signals are usually logged into the CRM alongside [Kantata](https://www.kantata.com/) delivery records.
