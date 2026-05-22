---
title: Search
category: api
order: 5
lastUpdated: '2026-05-22'
summary: Search your DoneThat task and activity history.
method: POST
path: /search
scopes:
  - 'search:read'
tags:
  - api
  - search
---

The search endpoint performs bounded lexical search across your DoneThat task and activity history.

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
  "sources": ["tasks", "activity"]
}
```

| Field | Type | Required | Notes |
| :--- | :--- | :--- | :--- |
| `query` | string | Yes | Search phrase. Required; empty or whitespace-only queries return `400`. Max **100** characters. |
| `context` | string | No | Optional ranking hint (max **100** characters). Refines ordering only; does not broaden matching. |
| `limit` | number | No | Defaults to `20`; maximum `50`. |
| `days` | number | No | Defaults to `7`; maximum `30`. |
| `sources` | string[] | No | `tasks`, `activity`, or both. Defaults to both. Invalid values return `400`. |

## Response

```json
{
  "success": true,
  "query": "customer onboarding",
  "context": "enterprise pilot",
  "days": 7,
  "sources": ["tasks", "activity"],
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
        "projectId": "project_123",
        "visible": true
      }
    }
  ],
  "message": "Found 3 matches for \"customer onboarding\" in the last 7 days."
}
```

Results are ranked by match quality, then newest first. `totalMatches` is the total number found before applying `limit`.

Task result `metadata` may include `minutes`, `projectId`, and `visible`. Activity result `metadata` may include `taskId`, `categoryName`, and `categoryEmoji`.

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
