---
title: Client Satisfaction Sentiment Monitor
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - consulting
  - deliver
  - quality
domain: consulting
domainOrder: 19
stage: deliver
stageOrder: 7
outcome:
  - quality
value: 4
effort: 4
---
LLM continuously analyzes client emails and meeting transcripts for satisfaction signals and escalation risk patterns.

## What it is, how it works

Satisfaction monitoring reads client emails and meeting transcripts for signals that the relationship is cooling: shorter replies, fewer attendees, escalating language, questions that sound like they came from procurement.

- Signals are behavioral, including response latency and meeting attendance, not only tone.
- Escalation patterns are distinguished from ordinary friction.
- Alerts go to the engagement lead with the evidence attached.

## When not to use it

- Scoring client emails is a trust question. Ask whether the relationship would survive the client finding out. Answer that first.
- Sentiment models are unreliable across cultures and second-language speakers, and confident scores on such material are misleading.
- A quietly unhappy client still writes politely. Tone analysis misses the case that matters most.

## How to get started

- Settle the ethics and the data handling before the tooling. This is the gating question.
- Weight behavioral signals over tone, since attendance and latency are harder to fake and easier to interpret.
- Treat every alert as a prompt to call the client, not as a finding.

## Best practices / further reading

- Sentiment shifts usually precede the delivery signals in [workstream delivery risk predictor](./workstream-delivery-risk-predictor.md).
- Post-engagement monitoring continues through [post-delivery relationship health monitor](./post-delivery-relationship-health-monitor.md).
