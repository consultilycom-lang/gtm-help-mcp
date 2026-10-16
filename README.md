<p align="center"><img src="assets/logo.png" width="120" alt="gtm.help logo"></p>

# gtm.help MCP server

Your go-to-market plan, plays and buyer conversations from [gtm.help](https://gtm.help), inside Claude, ChatGPT, Cursor, VS Code, Windsurf and any MCP client.

- **Endpoint:** `https://gtm.help/mcp`
- **Transport:** Streamable HTTP (remote, nothing to install)
- **Auth:** OAuth 2.1. Your client opens a gtm.help sign-in window on first use. No API key. Your agent acts as you and only sees your own workspaces.
- **Free to try:** `analyze_site` works for anyone who connects. Reading and updating your own plan needs an active gtm.help plan (7-day free trial).
- **Never posts for you:** agents draft replies; you post them yourself.

Full guides: https://gtm.help/for-agents

> This repository contains documentation and client configuration only. The server is hosted by gtm.help; its source code is not public.

## Tools (16)

| Tool | What it does |
|---|---|
| `analyze_site` | Give it any website and get three high-leverage growth plays back, costed and explained. Free for anyone connected. |
| `list_workspaces` | Every business on your account with its website, goal, stage and budget. |
| `get_business` | The full profile: audience, competitors, what has been tried and every note you have stored. |
| `get_plan` | The ranked, costed growth plays for a workspace, in the order to work them. |
| `get_play` | Everything about a single play: the steps, the tools, the budget and the metric. |
| `update_play_status` | Start, park, skip, reopen or finish a play, on the same board you see in the app. |
| `complete_play` | The quick shortcut for a finished play; the next one moves up. |
| `add_business_note` | Store a finding, a number or an idea so the plan remembers it. |
| `share_recap` | Make a public progress card to paste into a report, a post or a team chat. |
| `list_opportunities` | The Reddit threads, LinkedIn posts and X replies your agents ranked, by fit and how hot they are. |
| `draft_reply` | An answer written in your voice with the link to post it at. You post it; gtm.help never does. |
| `update_opportunity` | Record a conversation as replied, ignored or snoozed so it stops coming back. |
| `update_watchlist` | Read or change the keywords, topics, competitors, people and subreddits being watched. |
| `list_integrations` | Which tools are connected, whether they are healthy, and their latest synced numbers. |
| `list_invoices` | Invoices, tax and receipt links, for your own account only. |
## Install

### Claude (claude.ai / Claude Desktop)
Settings → Connectors → **Add custom connector** → name `gtm.help`, URL `https://gtm.help/mcp` → sign in. [Guide](https://gtm.help/for-agents/claude)

### Claude Code
```bash
claude mcp add --transport http gtm-help https://gtm.help/mcp
```
Then run `/mcp` to complete sign-in.

### Cursor
`.cursor/mcp.json` (project) or `~/.cursor/mcp.json` (global):
```json
{ "mcpServers": { "gtm-help": { "url": "https://gtm.help/mcp" } } }
```
Settings → MCP → enable `gtm-help` and sign in. [Guide](https://gtm.help/for-agents/cursor)

### VS Code (Copilot agent mode)
`.vscode/mcp.json`:
```json
{ "servers": { "gtm-help": { "type": "http", "url": "https://gtm.help/mcp" } } }
```
[Guide](https://gtm.help/for-agents/vscode)

### Windsurf
`~/.codeium/windsurf/mcp_config.json`:
```json
{ "mcpServers": { "gtm-help": { "serverUrl": "https://gtm.help/mcp" } } }
```
[Guide](https://gtm.help/for-agents/windsurf)

### Gemini CLI
```bash
gemini extensions install https://github.com/consultilycom-lang/gtm-help-mcp
```
Then run `/mcp auth gtm-help` in Gemini CLI to sign in.

### ChatGPT
Settings → Connectors → Create (developer mode, depending on plan) → transport Streamable HTTP, URL `https://gtm.help/mcp`, auth OAuth (leave API key blank). [Guide](https://gtm.help/for-agents/chatgpt)

### Codex CLI
`~/.codex/config.toml`: see the [Codex guide](https://gtm.help/for-agents/codex).

## Try it
- "Analyse stripe.com with gtm.help and give me three growth plays." (free)
- "List my gtm.help workspaces."
- "What should I ship this week?"
- "Mark the cold outbound play complete and share a recap."

## Files
- `server.json`: [Official MCP Registry](https://registry.modelcontextprotocol.io) entry (`help.gtm/gtm-help`)
- `server-card.json`: static server card (also served at `https://gtm.help/.well-known/mcp/server-card.json`)
- `.cursor-plugin/plugin.json` + `mcp.json`: Cursor plugin
- `assets/logo.png`: logo

## Support
team@gtm.help · https://gtm.help/contact · [Privacy](https://gtm.help/privacy) · [Terms](https://gtm.help/terms)
