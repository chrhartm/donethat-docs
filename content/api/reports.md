---
title: Reports
category: api
order: 2
lastUpdated: '2026-05-19'
summary: >-
  Pull aggregated activity rows for a date range at minute, day, task, or week
  resolution.
method: POST
path: /report
scopes:
  - 'reports:read'
tags:
  - api
  - reports
---

The reports endpoint returns aggregated work data for a date range, at the resolution you ask for. It is the same data that powers the in-app stats views.

```
POST https://api.donethat.ai/report
```

**Required scope:** `reports:read`

## Request body

```json
{
  "dateRange": {
    "from": 1767225600000,
    "to":   1768608000000
  },
  "aggregationLevel": "day",
  "projectIds": ["..."],
  "teamIds": ["..."],
  "includeCategories": true,
  "includeProjects": true,
  "sort": "desc"
}
```

| Field | Type | Required | Notes |
| :--- | :--- | :--- | :--- |
| `dateRange.from` | number | Yes | Unix milliseconds. |
| `dateRange.to` | number | Yes | Unix milliseconds. |
| `aggregationLevel` | string | Yes | One of `minute`, `day`, `task`, `week`. |
| `projectIds` | string[] | No | Filter to specific projects. |
| `teamIds` | string[] | No | Only valid with `day`, `task`, or `week` aggregation. |
| `includeCategories` | boolean | No | Defaults to `true`. |
| `includeProjects` | boolean | No | Defaults to `true`. |
| `sort` | string | No | `asc` or `desc`. When omitted, rows are ordered by stable row `id` ascending. |

### Empty body default

If you send an empty JSON body, the endpoint returns a useful default report:

- `dateRange`: the last 7 days.
- `aggregationLevel`: `day`.
- `sort`: `desc`.

### Range limits

- `minute` resolution - up to 90 days.
- `day`, `task`, and `week` resolution - up to 365 days.
- `week` aggregation only processes full weeks; partial weeks at the edges are dropped.

## Response

```json
{
  "success": true,
  "rowCount": 42,
  "rows": [
    {
      "id": "day:2026-01-01",
      "date": "2026-01-01",
      "duration": 330,
      "duration_relative": 82.5,
      "projects": [
        { "name": "My Project", "minutes": 240 }
      ],
      "categories": [
        { "name": "Focus", "minutes": 210 }
      ],
      "tasks": [
        { "title": "Fix bug", "duration": 90 }
      ],
      "comment": "Shipped the bug fix and reviewed onboarding work."
    }
  ]
}
```

This example shows a day-level row. Row fields vary by `aggregationLevel`; minute-level rows include fields like `timestamp`, `timestampIso`, `time`, `task`, `headline`, and `description`.

Every row includes a stable `id` for deduplication. Minute rows also include `timestampIso`, the ISO 8601 UTC companion to `timestamp`.

Row objects use `snake_case` field names (see [Overview](/api-reference/overview#field-naming)).

When polling for new data, map `rows` and use each row's `id` as the deduplication key. Prefer `aggregationLevel: "day"` and narrow `dateRange` windows to stay within your client's HTTP timeouts.

## Example

```bash
curl -X POST "https://api.donethat.ai/report" \
     -H "Content-Type: application/json" \
     -H "x-api-key: YOUR_API_KEY" \
     -d '{
       "dateRange": { "from": 1767225600000, "to": 1768608000000 },
       "aggregationLevel": "day",
       "includeCategories": true,
       "sort": "desc"
     }'
```
