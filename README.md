# Adflitz MCP: AI ad manager for Meta Ads, Google Ads, LinkedIn Ads, TikTok Ads and ChatGPT Ads

[Adflitz](https://adflitz.com) is an AI ad manager and ads MCP server for PPC and performance marketing. It connects your AI assistant to your paid-ads accounts (Meta, Google Ads, LinkedIn, ChatGPT Ads, TikTok, Pinterest, Snapchat, Reddit, X and Microsoft Ads). Your assistant handles ad reporting and campaign management, automates routine optimizations with autopilot rules, files change drafts, and a person approves them in Adflitz before anything is published.

[![Add to Cursor](https://cursor.com/deeplink/mcp-install-dark.svg)](https://cursor.com/en/install-mcp?name=adflitz&config=eyJ1cmwiOiJodHRwczovL2FkZmxpdHouY29tL2FwaS9tY3AifQ%3D%3D)
[![Install in VS Code](https://img.shields.io/badge/VS_Code-Install_Adflitz-0098FF?style=flat-square&logo=visualstudiocode&logoColor=white)](https://vscode.dev/redirect/mcp/install?name=adflitz&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fadflitz.com%2Fapi%2Fmcp%22%7D)
[![Install in VS Code Insiders](https://img.shields.io/badge/VS_Code_Insiders-Install_Adflitz-24bfa5?style=flat-square&logo=visualstudiocode&logoColor=white)](https://insiders.vscode.dev/redirect/mcp/install?name=adflitz&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fadflitz.com%2Fapi%2Fmcp%22%7D)

This repository contains the client configuration only. The server is hosted by Adflitz:

| | |
|---|---|
| MCP endpoint | `https://adflitz.com/api/mcp` (Streamable HTTP) |
| Sign-in | OAuth 2.1 with PKCE and dynamic client registration, or an `apk_…` API key as Bearer token |
| Scopes | `adflitz.read`, `adflitz.draft`, `adflitz.publish` |
| Docs | https://adflitz.com/docs/mcp |
| Server card | https://adflitz.com/.well-known/mcp/server-card.json |
| Privacy policy | https://adflitz.com/privacy |
| Terms of service | https://adflitz.com/terms |
| License | [MIT](LICENSE) |
| Support | contact@adflitz.com |

## Add it to your client

**Claude (claude.ai, Desktop, mobile):** Settings → Connectors → Add custom connector → `https://adflitz.com/api/mcp`.

**Claude Code:** `claude mcp add --transport http adflitz https://adflitz.com/api/mcp`

**ChatGPT:** Settings → Apps → Create (developer mode) → MCP server URL `https://adflitz.com/api/mcp`, authentication OAuth.

**Cursor:** [one-click install](https://cursor.com/en/install-mcp?name=adflitz&config=eyJ1cmwiOiJodHRwczovL2FkZmxpdHouY29tL2FwaS9tY3AifQ%3D%3D) (deep link: `cursor://anysphere.cursor-deeplink/mcp/install?name=adflitz&config=eyJ1cmwiOiJodHRwczovL2FkZmxpdHouY29tL2FwaS9tY3AifQ%3D%3D`), or add to `~/.cursor/mcp.json` (or install this repository as a plugin):

```json
{ "mcpServers": { "adflitz": { "url": "https://adflitz.com/api/mcp" } } }
```

**Gemini CLI:** `gemini extensions install https://github.com/Performancebude-PEBU-GmbH/adflitz-mcp`

**VS Code / Copilot:** [one-click install](https://vscode.dev/redirect/mcp/install?name=adflitz&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fadflitz.com%2Fapi%2Fmcp%22%7D) (deep link: `vscode:mcp/install?%7B%22name%22%3A%22adflitz%22%2C%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fadflitz.com%2Fapi%2Fmcp%22%7D`), or add an HTTP MCP server with the URL above.

**Grok, Perplexity, Mistral Le Chat:** add a custom MCP connector with the URL above.

## Tools

26 tools over OAuth: workspace overview, projects, connection status, ad accounts, campaigns, ad groups, ads, performance reports, platform options, drafts (create, list, get, approve, reject, publish), competitor ad library search, swipe-file boards, activity feed and autopilot rules. Every tool declares `readOnlyHint`, `destructiveHint` and `openWorldHint`. All changes go through drafts and approval. See the [server card](https://adflitz.com/.well-known/mcp/server-card.json) for the full list.

Agents installing Adflitz: see [llms-install.md](llms-install.md).

Licensed under the [MIT License](LICENSE). © 2026 PEBU GmbH. Adflitz is a service of PEBU GmbH. [Privacy](https://adflitz.com/privacy) · [Terms](https://adflitz.com/terms)
