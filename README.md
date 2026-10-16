<p align="center"><img src="assets/logo.png" width="120" alt="gtm.help logo"></p>

# gtm.help MCP server

Your go-to-market plan, plays and buyer conversations from [gtm.help](https://gtm.help), inside Claude, ChatGPT, Cursor, VS Code, Windsurf and any MCP client.

- **Endpoint:** `https://gtm.help/mcp`
- **Transport:** Streamable HTTP (remote, nothing to install)
- **Auth:** OAuth 2.1. Your client opens a gtm.help sign-in window on first use. No API key. Your agent acts as you and only sees your own workspaces.
- **Try it:** `analyze_site` works for anyone who connects. Reading and working your own plan needs a gtm.help subscription: Growth $97/month or $975/year billed yearly ($81.25/mo effective), 7-day free trial (card required). Agency 10 is $775/month for 10 businesses; Agency 25 is $1,950/month for 25 businesses.
- **Never posts for you:** agents draft replies; you post them yourself.

**Step-by-step install guides:** [docs/](docs/README.md) for [Claude](docs/claude.md) · [Cursor](docs/cursor.md) · [VS Code](docs/vscode.md) · [Windsurf](docs/windsurf.md) · [ChatGPT](docs/chatgpt.md) · [Lovable](docs/lovable.md). More at https://gtm.help/for-agents

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
| `submit_play_draft` | Hand back finished work for a play (a draft post, brief or page) so it is saved against the play. |
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

Full step-by-step guides live in [docs/](docs/README.md). Quick versions:

### Claude (claude.ai / Claude Desktop)
Customize → Connectors → **+ Add → Add custom connector** → name `gtm.help`, URL `https://gtm.help/mcp` → Connect and sign in. [Guide](docs/claude.md)

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
[Guide](docs/cursor.md)

### VS Code (Copilot agent mode)
`.mcp.json` at the workspace root (or `~/.copilot/mcp-config.json`):
```json
{ "mcpServers": { "gtm-help": { "type": "http", "url": "https://gtm.help/mcp" } } }
```
Legacy `.vscode/mcp.json` uses `"servers"` instead of `"mcpServers"`. [Guide](docs/vscode.md)

### Windsurf / Devin Desktop
Cascade panel → … → Open MCP config file:
```json
{ "mcpServers": { "gtm-help": { "serverUrl": "https://gtm.help/mcp" } } }
```
[Guide](docs/windsurf.md)

### Gemini CLI
```bash
gemini extensions install https://github.com/consultilycom-lang/gtm-help-mcp
```
Then run `/mcp auth gtm-help` in Gemini CLI to sign in.

### ChatGPT
Plugins → **+ → Add custom MCP server** → URL `https://gtm.help/mcp`, OAuth → Create as a plugin (availability depends on plan and workspace policy). [Guide](docs/chatgpt.md)

### Lovable
Connectors → **+ → MCP server** → URL `https://gtm.help/mcp`, OAuth → Add & authorize. [Guide](docs/lovable.md)

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
team@gtm.help · [Help](https://gtm.help/help) · [Privacy & security](https://gtm.help/security) · [DPA](https://gtm.help/dpa) · [Refunds](https://gtm.help/refunds) · [Terms](https://gtm.help/terms)
