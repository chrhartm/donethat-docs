---
title: Overview
category: mcp
order: 1
lastUpdated: '2026-05-21'
summary: >-
  Connect Claude, ChatGPT, and other MCP clients to your DoneThat work history
  with OAuth 2.1.
tags:
  - mcp
  - oauth
  - integrations
---

DoneThat is a time tracker that automatically turns captured work activity into daily summaries, where a task means work that was already completed or performed, not a future to-do item.

The DoneThat MCP server lets AI assistants read and update your DoneThat data on your behalf. Connect with OAuth 2.1 using your existing DoneThat account. You do not paste API keys into the connector setup.

```
https://mcp.donethat.ai
```

The server uses **Streamable HTTP** transport at `/` and runs in **stateless** mode (no persistent MCP session required). Check availability at `/health`.

## Connect in Claude

1. Open **Settings → Connectors**.
2. Choose **Add custom connector**.
3. Paste the server URL: `https://mcp.donethat.ai`
4. Complete the OAuth sign-in flow with your DoneThat account when prompted.
5. Grant the scopes the connector requests.

## Connect in ChatGPT

1. Open **Settings → Connectors** (or the Apps/connectors area in your ChatGPT plan).
2. Add a custom MCP server and paste `https://mcp.donethat.ai`.
3. Sign in with your DoneThat account when OAuth opens.
4. Approve the requested scopes.

ChatGPT may render summary and report results in an embedded DoneThat widget for supported tools.

## Connect in Cursor or VS Code

Add an MCP server entry that points at the DoneThat URL. Exact UI labels vary by client; the server URL is always:

```json
{
  "mcpServers": {
    "donethat": {
      "url": "https://mcp.donethat.ai"
    }
  }
}
```

Your client discovers OAuth endpoints automatically. Sign in with DoneThat when prompted.

## Authentication

DoneThat MCP uses **OAuth 2.1** (authorization code with PKCE). You authenticate with your DoneThat account; the MCP host stores tokens on your behalf.

**Do not** paste DoneThat HTTP API keys into MCP connector settings. MCP OAuth scopes are separate from [HTTP API key scopes](/api-reference).

### Sign-in flow

When a connector starts OAuth, the MCP server sends you to the DoneThat web app at `https://app.donethat.ai`:

1. Sign in with **Google** or **email and password** (the same login you use for DoneThat).
2. Review the requested scopes on the consent screen.
3. Click **Authorize** to grant access.
4. The connector receives an access token and refresh token and can call MCP tools on your behalf.

No client secret is required. Connectors use a public OAuth client with PKCE.

Discovery and OAuth endpoints on the MCP host:

| Endpoint | Purpose |
| :--- | :--- |
| `GET /.well-known/oauth-protected-resource` | Protected resource metadata (RFC 9728) |
| `GET /.well-known/oauth-authorization-server` | Authorization server metadata (RFC 8414) |
| `GET /.well-known/openid-configuration` | Same metadata for OIDC discovery clients |
| `GET /oauth/scopes` | Human-readable scope list |
| `POST /oauth/register` | Dynamic client registration |
| `GET /oauth/authorize` | Authorization (browser sign-in) |
| `POST /oauth/token` | Token exchange and refresh |

Access tokens are short-lived. Refresh tokens allow renewal without signing in again until they expire or are revoked.

## Tools

| Tool | Description | Required scope(s) | Access |
| :--- | :--- | :--- | :--- |
| `generate_report` | Generate reports with activity, day, task, or week aggregation for the authenticated user. | `reports:read` | Read |
| `search_content` | Search recent task and activity history with a bounded lexical scan. | `search:read` | Read |
| `get_summary` | Read daily summaries for one local date. | `summaries:read` or `summaries:write` | Read |
| `get_message` | Fetch a daily or aggregate summary rendered as text, HTML, or Slack blocks. | `summaries:read` | Read |
| `generate_summary` | Generate the next draft daily summary. | `summaries:write` | Write |
| `approve_summary` | Approve a draft daily summary, optionally applying patch-style changes first. | `summaries:write` | Write |
| `edit_summary` | Edit an approved daily summary with patch-style changes. | `summaries:write` | Write |
| `add_manual_task` | Record uncaptured work with exact times or as a day-linked manual entry. | `tasks:write` | Write |
| `submit_feedback` | Send bug reports, product feedback, or feature requests to DoneThat support. | `feedback:write` | Write |

## Scopes

When you authorize a connector, DoneThat shows these OAuth scopes. Grant only what the integration needs.

| Scope | Grants |
| :--- | :--- |
| `reports:read` | Generate DoneThat reports for the authenticated account, including activity, day, task, and week views. |
| `summaries:read` | Fetch rendered daily and aggregate summaries, and retrieve existing daily summary data for read-only review. |
| `search:read` | Search the authenticated user's task and activity history in read-only mode. |
| `tasks:write` | Create manual DoneThat tasks with either exact times or day-linked durations. |
| `summaries:write` | Generate, approve, and edit DoneThat daily summaries for the authenticated account. |
| `feedback:write` | Send product feedback, bug reports, or feature requests to the DoneThat support team. |

These scopes differ from HTTP API key scopes documented in the [API reference](/api-reference).

## Data and privacy

The MCP server acts on behalf of your DoneThat account. Depending on granted scopes, it may:

- Read aggregated activity and report rows
- Read or write daily summaries
- Search task and activity history
- Create manual tasks
- Submit feedback to DoneThat support

DoneThat does not sell your data. See [Privacy](/privacy), [Terms](/terms), and [Data handling](/data) for how we collect, use, and protect information.

## Rate limits and troubleshooting

Requests are rate limited per account and client. If a tool call fails with a rate-limit error, wait and retry.

**Authentication errors:** Confirm you completed OAuth sign-in and approved the scopes the tool needs. Disconnect and reconnect the connector if tokens expired without refresh.

**Missing summary errors:** Tools that read a specific date return an error when no summary exists yet for that date. Use `generate_summary` (requires `summaries:write`) or create summaries in the DoneThat app first.

**Invalid dates:** Pass dates as ISO strings (for example `2026-03-23`).

**Manual tasks on a day without an approved summary:** `add_manual_task` in day-linked mode requires an approved daily summary for that date.

## Support

Questions about MCP setup, OAuth, or tool behavior: [Contact support](/support).

For programmatic HTTP access (API keys), see the [API reference](/api-reference).
