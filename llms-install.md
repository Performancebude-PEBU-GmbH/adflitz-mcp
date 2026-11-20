# Installing Adflitz (instructions for AI agents)

Adflitz is a **remote MCP server**. There is nothing to download, build or run locally and no API key is required.

- **Endpoint:** `https://adflitz.com/api/mcp`
- **Transport:** Streamable HTTP
- **Authentication:** OAuth 2.0 (authorization code + PKCE) with dynamic client registration (RFC 7591). The client discovers everything from `https://adflitz.com/.well-known/oauth-protected-resource` and `https://adflitz.com/.well-known/oauth-authorization-server`.
- **Account:** the user signs in (or signs up) with an Adflitz account in the browser window that opens during the OAuth flow, then picks the account/project and the permission level (`adflitz.read`, `adflitz.draft` or `adflitz.publish`).
- **Platforms:** Meta, Google Ads, LinkedIn, ChatGPT Ads, TikTok, Pinterest, Snapchat, Reddit, X and Microsoft Ads. The user connects their ad accounts inside Adflitz.
- **Safety:** every change is filed as a draft and a person approves it in Adflitz before anything is published.

Do not ask the user for tokens or passwords. Add the server with the config for the client in use, then let the client start the OAuth sign-in.

## Cursor

Add to `~/.cursor/mcp.json` (or `.cursor/mcp.json` in a project):

```json
{
  "mcpServers": {
    "adflitz": {
      "url": "https://adflitz.com/api/mcp"
    }
  }
}
```

Cursor opens the browser for OAuth the first time a tool is used.

## VS Code (GitHub Copilot)

Add to `.vscode/mcp.json` (or run **MCP: Add Server** and choose HTTP):

```json
{
  "servers": {
    "adflitz": {
      "type": "http",
      "url": "https://adflitz.com/api/mcp"
    }
  }
}
```

## Claude Code

```bash
claude mcp add --transport http adflitz https://adflitz.com/api/mcp
```

Then run `/mcp` inside Claude Code and choose **Authenticate** for `adflitz`.

## Claude Desktop / claude.ai

Settings → Connectors → **Add custom connector** → URL `https://adflitz.com/api/mcp`.

If you configure Claude Desktop by file, use the `mcp-remote` bridge:

```json
{
  "mcpServers": {
    "adflitz": {
      "command": "npx",
      "args": ["-y", "mcp-remote", "https://adflitz.com/api/mcp"]
    }
  }
}
```

## Cline

Open **MCP Servers → Remote Servers → Edit Configuration** (`cline_mcp_settings.json`) and add:

```json
{
  "mcpServers": {
    "adflitz": {
      "url": "https://adflitz.com/api/mcp",
      "type": "streamableHttp",
      "disabled": false
    }
  }
}
```

Cline starts the OAuth flow from the server's **Authenticate** button.

## Gemini CLI

```bash
gemini extensions install https://github.com/Performancebude-PEBU-GmbH/adflitz-mcp
```

Or add it by hand to `~/.gemini/settings.json`:

```json
{
  "mcpServers": {
    "adflitz": {
      "url": "https://adflitz.com/api/mcp",
      "type": "http"
    }
  }
}
```

Run `/mcp auth adflitz` in Gemini CLI to sign in.

## Verify

After sign-in, call the `adflitz_overview` tool. It returns the workspace, accounts and the permissions that were granted.

## Links

- Docs: https://adflitz.com/docs/mcp
- Server card: https://adflitz.com/.well-known/mcp/server-card.json
- Privacy policy: https://adflitz.com/privacy
- Terms of service: https://adflitz.com/terms
- Support: contact@adflitz.com
- License: MIT (see `LICENSE`)
