---
title: Search
category: api
order: 5
lastUpdated: '2026-05-19'
summary: Search your DoneThat task and screenshot history.
method: POST
path: /search
scopes:
  - 'search:read'
tags:
  - api
  - search
---

The search endpoint performs bounded lexical search across your DoneThat task and screenshot history.

```
POST https://api.donethat.ai/search
```

**Required scope:** `search:read`

Pass your API key in the `x-api-key` header.

## Request body

```json
{
  "query": "customer onboarding",
  "context": "enterprise pilot",
  "limit": 20,
  "days": 7,
  "sources": ["tasks", "screenshots"]
}
```

| Field | Type | Required | Notes |
| :--- | :--- | :--- | :--- |
| `query` | string | Yes | Search phrase. Empty queries are rejected. |
| `context` | string | No | Optional ranking hint. It refines ordering but does not broaden matching. |
| `limit` | number | No | Defaults to `20`; maximum `50`. |
| `days` | number | No | Defaults to `7`; maximum `30`. |
| `sources` | string[] | No | `tasks`, `screenshots`, or both. Defaults to both. |

## Response

```json
{
  "success": true,
  "query": "customer onboarding",
  "context": "enterprise pilot",
  "days": 7,
  "sources": ["tasks", "screenshots"],
  "totalMatches": 3,
  "results": [
    {
      "source": "tasks",
      "id": "task_123",
      "timestamp": "2026-05-19T09:00:00.000Z",
      "title": "Draft customer onboarding plan",
      "snippet": "Drafted the onboarding checklist for the enterprise pilot...",
      "matchedFields": ["title", "description"],
      "metadata": {
        "minutes": 45,
        "taskGroupId": "project_123",
        "visible": true
      }
    }
  ],
  "message": "Found 3 matches for \"customer onboarding\" in the last 7 days."
}
```

Results are ranked by match quality, then newest first. `totalMatches` is the total number found before applying `limit`.

Task result `metadata` may include `minutes`, `taskGroupId` (project id), and `visible`. Screenshot result `metadata` may include `taskId`, `categoryName`, and `categoryEmoji`.

## Example

```bash
curl -X POST "https://api.donethat.ai/search" \
     -H "Content-Type: application/json" \
     -H "x-api-key: YOUR_API_KEY" \
     -d '{
       "query": "customer onboarding",
       "days": 14,
       "sources": ["tasks"]
     }'
```

## Errors

```json
{
  "success": false,
  "error": "query must not be empty."
}
```
