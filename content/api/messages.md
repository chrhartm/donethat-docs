---
title: Messages
category: api
order: 3
lastUpdated: '2026-05-19'
summary: >-
  Generate formatted day, week, month, quarter, or year summaries — the same
  content shown on the Summaries tab.
method: GET / POST
path: /message
scopes:
  - 'messages:read'
  - 'reports:read'
tags:
  - api
  - messages
  - summaries
---

The messaging endpoint returns a structured summary for a given date and aggregation level, in HTML, plain text, or Slack-block format. It produces the same content shown on the in-app Summaries tab.

```
GET  https://api.donethat.ai/message
POST https://api.donethat.ai/message
```

**Required scope:** `messages:read` or `reports:read`

**Authentication:** `x-api-key` header **or** `apiKey` query parameter — useful when wiring into GET-only integrations.

## Request parameters

Parameters can be passed as query string (GET) or JSON body (POST).

| Parameter | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| `date` | string | Yes | The date for which to fetch the summary, e.g. `2026-02-02`. |
| `level` | string | Yes | Aggregation level: `day`, `week`, `month`, `quarter`, or `year`. |
| `format` | string | No | Output format: `html`, `text`, or `slack`. Defaults to `html`. |

## Response

```json
{
  "success": true,
  "level": "day",
  "format": "text",
  "content": "John's daily summary: Feb 2. Total work recorded: 8.5h...",
  "metadata": {
    "subject": "John's daily summary: Feb 2"
  }
}
```

- `content` — the formatted summary. A string for `html` and `text`; an array of Slack Blocks (JSON) for `slack`.
- `metadata.subject` — suggested subject line for email delivery.

## Examples

Fetch today's summary as plain text via GET:

```bash
curl -X GET "https://api.donethat.ai/message?date=2026-02-02&level=day&format=text&apiKey=YOUR_API_KEY"
```

Fetch this week's aggregate as Slack blocks via POST:

```bash
curl -X POST "https://api.donethat.ai/message" \
     -H "Content-Type: application/json" \
     -H "x-api-key: YOUR_API_KEY" \
     -d '{
       "date": "2026-02-02",
       "level": "week",
       "format": "slack"
     }'
```
