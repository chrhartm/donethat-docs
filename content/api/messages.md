---
title: Messages
category: api
order: 3
lastUpdated: '2026-05-19'
summary: >-
  Generate formatted day, week, month, quarter, or year summaries - the same
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

**Authentication:** pass your API key in the `x-api-key` header (required for GET and POST).

## Request parameters

Parameters can be passed as query string (GET) or JSON body (POST).

| Parameter | Type | Required | Description |
| :--- | :--- | :--- | :--- |
| `date` | string | No | Calendar date as `YYYY-MM-DD` (in your account timezone). Defaults to **yesterday**. Other formats return `400`. |
| `level` | string | No | Exactly one of: `day`, `week`, `month`, `quarter`, `year`. Defaults to `day`. |
| `format` | string | No | Exactly one of: `html`, `text`, `slack`. Defaults to `html`. |

### Empty request default

A GET or POST with no parameters (or an empty JSON body) returns **yesterday's daily summary** as HTML. This matches the usual automation use case: "send me what DoneThat recorded for my last full day."

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

- `content`: the formatted summary. A string for `html` and `text`; a **JSON array of Slack Block Kit blocks** for `slack` (not a plain string).
- `metadata.subject`: suggested subject line for email delivery.

`404` is returned when no summary exists yet for the requested date and level (for example, the current day before a summary has been generated).

## Errors

See [Overview](/api-reference/overview#response-shape). Common cases: `401` (invalid API key), `403` (missing scope), `404` (no summary for that date/level).

## Examples

Fetch the default summary (yesterday, day level, HTML):

```bash
curl -X GET "https://api.donethat.ai/message" \
     -H "x-api-key: YOUR_API_KEY"
```

Fetch a specific day as plain text via GET:

```bash
curl -X GET "https://api.donethat.ai/message?date=2026-02-02&level=day&format=text" \
     -H "x-api-key: YOUR_API_KEY"
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
