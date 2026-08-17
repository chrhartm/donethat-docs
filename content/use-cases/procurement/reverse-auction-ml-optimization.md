---
title: Reverse auction ML optimization
category: use-cases
lastUpdated: '2026-08-17'
tags:
  - ai
  - procurement
  - source
  - cost
domain: procurement
domainOrder: 1
stage: source
stageOrder: 3
outcome:
  - cost
value: 3
effort: 4
---
ML agent manages dynamic pricing events, adjusts reserve prices in real time, and flags bid gaming behavior, using tools like Keelvar.

## What it is, how it works

An agent runs the mechanics of a bidding event. It moves reserve prices as bidding develops and orders lots to keep competition alive. It also watches bid patterns for signs that suppliers are coordinating.

- Lot structure and timing are optimized against the bidding behavior actually observed in the event.
- Gaming detection looks for the timing and increment patterns typical of collusive bidding.
- Award recommendations can weigh non-price criteria rather than defaulting to lowest bid.

## When not to use it

- Auctions suit clear specs and several real bidders. On complex services they damage relationships and produce bids nobody can deliver.
- Suppliers you depend on read repeated auctions as a message. They price it back to you next cycle.
- Thin supplier markets make auctions counterproductive. With two bidders you're advertising your position, not creating competition.

## How to get started

- Choose a category with a tight specification, several qualified suppliers, and no switching risk. Standard hardware and freight lanes are typical starting points.
- Run the first event with a human controlling reserve changes and the model advising, so you can see whether its recommendations hold up.
- Publish the rules to bidders in advance. Auctions where suppliers can't see the mechanism attract fewer serious bids.

## Best practices / further reading

- Set the reserve using [market price benchmarking](./market-price-benchmarking.md) rather than last year's price.
- Award decisions still run through the [multi-criteria decision matrix](./multi-criteria-decision-matrix.md).
- [Keelvar](https://www.keelvar.com/) is a widely used platform for sourcing optimization and auction automation.
