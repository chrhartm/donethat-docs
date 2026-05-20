---
title: User
category: api
order: 6
lastUpdated: '2026-05-20'
summary: Read basic profile information for the authenticated API key owner.
method: GET
path: /user
scopes:
  - 'user:read'
tags:
  - api
  - user
---

The user endpoint returns basic profile information for the account that owns the API key.

```
GET https://api.donethat.ai/user
```

**Required scope:** `user:read`

Pass your API key in the `x-api-key` header. Only `GET` is supported; other methods return `405` with `{ "success": false, "error": "Method Not Allowed" }`.

## Response

```json
{
  "success": true,
  "name": "Alex Morgan",
  "email": "alex@example.com"
}
```

| Field | Type | Notes |
| :--- | :--- | :--- |
| `name` | string \| null | DoneThat settings name when set; otherwise Firebase Auth display name; otherwise the local part of the sign-in email. |
| `email` | string \| null | Primary sign-in email from Firebase Auth. |

Either field may be `null` when the underlying account data is missing.

## Example

```bash
curl -X GET "https://api.donethat.ai/user" \
     -H "x-api-key: YOUR_API_KEY"
```

## Errors

Uses the standard API envelope (`success`, `error`). Common cases:

| Status | Cause |
| :--- | :--- |
| `401` | Missing or invalid API key |
| `403` | Key lacks `user:read` |
| `405` | Method other than `GET` |
| `429` | Rate limit exceeded |
| `500` | Unexpected server error |
