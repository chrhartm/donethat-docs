---
title: MCP
category: api
order: 7
lastUpdated: '2026-05-19'
summary: >-
  Connect Model Context Protocol clients to DoneThat using OAuth client
  credentials.
method: POST
path: /oauth/token
scopes:
  - 'reports:read'
  - read_summaries
  - 'search:read'
  - 'tasks:write'
  - 'summaries:write'
  - 'feedback:write'
tags:
  - api
  - mcp
  - oauth
---

DoneThat exposes a Model Context Protocol (MCP) server so AI assistants — Claude, Cursor, etc. — can read your activity data on your behalf. MCP clients authenticate via OAuth 2.0 client credentials.

The MCP base URL is:

```
https://mcp.donethat.ai
```

## Register a client

Create an MCP client in the DoneThat app under **Settings → MCP Clients**. You get back a `client_id` and a `client_secret`. The secret is shown once — copy it then.

Available scopes on an MCP client:

| Scope | Grants |
| :--- | :--- |
| `reports:read` | Read aggregated activity. |
| `read_summaries` | Read rendered summaries and existing daily summary data. |
| `search:read` | Search task and screenshot history. |
| `tasks:write` | Create manual DoneThat tasks. |
| `summaries:write` | Generate, approve, and edit daily summaries. |
| `feedback:write` | Send product feedback, bug reports, or feature requests. |

## Get an access token

Exchange the client credentials for an access token:

```
POST https://mcp.donethat.ai/oauth/token
```

Form fields (`application/x-www-form-urlencoded`):

| Field | Value |
| :--- | :--- |
| `grant_type` | `client_credentials` |
| `client_id` | Your client id |
| `client_secret` | Your client secret |

The response contains a short-lived `access_token`. Pass it in the `Authorization` header on subsequent MCP requests:

```
Authorization: Bearer <access_token>
```

## Example

```bash
curl -X POST "https://mcp.donethat.ai/oauth/token" \
     -d "grant_type=client_credentials" \
     -d "client_id=YOUR_CLIENT_ID" \
     -d "client_secret=YOUR_CLIENT_SECRET"
```

## Rotating and revoking

From **Settings → MCP Clients** you can rotate a client's secret (invalidates the old secret, returns a new one once) or revoke the client entirely. There is no programmatic management endpoint for clients today — do this from the app.
