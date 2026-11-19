# Adflitz MCP connector

[Adflitz](https://adflitz.com) connects your AI assistant to your paid-ads accounts (Meta, Google and LinkedIn). Your assistant reads performance, files change drafts, and a person approves them in Adflitz before anything is published.

This repository contains the client configuration only. The server is hosted by Adflitz:

| | |
|---|---|
| MCP endpoint | `https://adflitz.com/api/mcp` (Streamable HTTP) |
| Sign-in | OAuth 2.1 with PKCE and dynamic client registration, or an `apk_…` API key as Bearer token |
| Scopes | `adflitz.read`, `adflitz.draft`, `adflitz.publish` |
| Docs | https://adflitz.com/docs/mcp |
| Server card | https://adflitz.com/.well-known/mcp/server-card.json |
| Privacy policy | https://adflitz.com/privacy |
| Support | contact@adflitz.com |

## Add it to your client

**Claude (claude.ai, Desktop, mobile):** Settings → Connectors → Add custom connector → `https://adflitz.com/api/mcp`.

**Claude Code:** `claude mcp add --transport http adflitz https://adflitz.com/api/mcp`

**ChatGPT:** Settings → Apps → Create (developer mode) → MCP server URL `https://adflitz.com/api/mcp`, authentication OAuth.

**Cursor:** add to `~/.cursor/mcp.json` (or install this repository as a plugin):

```json
{ "mcpServers": { "adflitz": { "url": "https://adflitz.com/api/mcp" } } }
```

**Gemini CLI:** `gemini extensions install https://github.com/Performancebude-PEBU-GmbH/adflitz-mcp`

**Grok, Perplexity, Mistral Le Chat, VS Code / Copilot:** add a custom MCP connector with the URL above.

## Tools

26 tools over OAuth: workspace overview, projects, connection status, ad accounts, campaigns, ad groups, ads, performance reports, platform options, drafts (create, list, get, approve, reject, publish), competitor ad library search, swipe-file boards, activity feed and autopilot rules. Every tool declares `readOnlyHint`, `destructiveHint` and `openWorldHint`. All changes go through drafts and approval. See the [server card](https://adflitz.com/.well-known/mcp/server-card.json) for the full list.

© PEBU GmbH. Adflitz is a service of PEBU GmbH.
