---
title: Overview
category: api
order: 1
lastUpdated: '2026-05-19'
summary: 'Base URL, authentication, scopes, and conventions for the DoneThat HTTP API.'
tags:
  - api
  - authentication
---

The DoneThat HTTP API lets you read your activity data, generate summaries, manage projects, and search your task history programmatically. Endpoints are hosted at:

```
https://api.donethat.ai
```

All requests and responses use JSON. The API is currently in beta: endpoints and payloads may change, and rate limits apply per key.

## Authentication

All endpoints require an API key. Create one in the DoneThat app under **Settings → API Access**. Each key has a name and a set of scopes.

Pass the key in the `x-api-key` request header only. The API does not accept API keys in query strings, form fields, or JSON bodies.

```bash
curl -X POST "https://api.donethat.ai/report" \
     -H "Content-Type: application/json" \
     -H "x-api-key: YOUR_API_KEY" \
     -d '{ ... }'
```

## Scopes

When you create an API key, pick the minimum scopes the integration needs. Requests without the right scope return `403`.

| Scope | Grants |
| :--- | :--- |
| `reports:read` | Read aggregated activity via `/report`; also accepted by `/message`. |
| `messages:read` | Read formatted summaries via `/message`. |
| `projects:read` | List and read projects via `/projects`. |
| `projects:write` | Create, update, and archive projects via `/projects`; also accepted by the deprecated `/project` endpoint. |
| `search:read` | Search tasks and screenshots via `/search`. |

## Response shape

All endpoints except the deprecated `/project` route use the same JSON envelope:

**Success:**

```json
{
  "success": true
}
```

Success payloads add endpoint-specific fields (for example `rows`, `projects`, `project`, or `results`).

**Failure:**

```json
{
  "success": false,
  "error": "Human-readable error message"
}
```

Rate-limited responses (`429`) also include `retryAfterSec` (seconds) and a `Retry-After` HTTP header when applicable.

Wrong HTTP methods return `405` with the same failure envelope.

The deprecated [`/project`](/api-reference/project) endpoint uses a different request and response format than `/projects`.

## Field naming

- `/report` row objects use `snake_case` (for example `project_id`, `task_id`).
- `/projects` objects use `camelCase` (for example `teamId`, `portfolioId`).

Map fields explicitly when connecting DoneThat to other tools: naming differs between endpoints (see below).

## Rate limits

Requests are rate limited per API key. When exceeded, the API returns `429` with `success: false`, `error: "rate_limited"`, and `retryAfterSec` (and a `Retry-After` header when applicable). Back off and retry after `retryAfterSec` seconds.

Large `/report` requests can take a long time to complete. Prefer `day` aggregation and narrower date ranges when polling for new rows.

## Endpoints

- [Reports](/api-reference/reports): pull aggregated activity rows.
- [Messages](/api-reference/messages): generate formatted day/week/month summaries.
- [Projects](/api-reference/projects): list, create, update, and archive projects.
- [Project (deprecated)](/api-reference/project): operation-based project endpoint for existing integrations.
- [Search](/api-reference/search): search task and screenshot history.
