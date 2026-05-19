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

All requests and responses use JSON unless noted otherwise. The API is currently in beta — endpoints and payloads may change, and rate limits apply per key.

## Authentication

Most endpoints accept an API key. Create one in the DoneThat app under **Settings → API Access**. Each key has a name and a set of scopes.

Pass the key in the `x-api-key` header:

```bash
curl -X POST "https://api.donethat.ai/report" \
     -H "Content-Type: application/json" \
     -H "x-api-key: YOUR_API_KEY" \
     -d '{ ... }'
```

The `/message` endpoint also accepts the key as an `apiKey` query parameter, which makes it convenient to wire into tools that only support GET URLs (Zapier, Slack reminders, etc).

## Scopes

When you create an API key, pick the minimum scopes the integration needs. Requests without the right scope return `403`.

| Scope | Grants |
| :--- | :--- |
| `reports:read` | Read aggregated activity via `/report`; also accepted by `/message`. |
| `messages:read` | Read formatted summaries via `/message`. |
| `projects:read` | List and read projects via `/projects`. |
| `projects:write` | Create, update, archive, and delete projects via `/projects`; also accepted by the deprecated `/project` endpoint. |
| `search:read` | Search tasks and screenshots via `/search`. |

For MCP clients see the [MCP](/api-reference/mcp) page — those use OAuth client credentials instead of an API key.

## Response shape

Legacy endpoints (`/report`, `/message`, and `/project`) return a JSON envelope with `"success": true` on success. Newer REST endpoints (`/projects` and `/search`) use endpoint-specific shapes; see each page for the exact response.

Legacy failures return:

```json
{
  "success": false,
  "error": "Human-readable error message"
}
```

Newer REST failures return:

```json
{
  "error": "Human-readable error message"
}
```

Both styles use an appropriate HTTP 4xx or 5xx status.

## Endpoints

- [Reports](/api-reference/reports) — pull aggregated activity rows.
- [Messages](/api-reference/messages) — generate formatted day/week/month summaries.
- [Projects](/api-reference/projects) — list, create, update, archive, and delete projects.
- [Project (legacy)](/api-reference/project) — deprecated operation-based project endpoint.
- [Search](/api-reference/search) — search task and screenshot history.
- [MCP](/api-reference/mcp) — OAuth client credentials for Model Context Protocol clients.
