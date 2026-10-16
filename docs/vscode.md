# gtm.help in VS Code (GitHub Copilot agent mode)

Official docs: [Add and manage MCP servers in VS Code](https://code.visualstudio.com/docs/copilot/customization/mcp-servers)

## Option A: guided
1. Command Palette → **MCP: Add Server** (or **Chat: Open Customizations → MCP Servers → Add Server**).
2. Choose **HTTP**, then enter `https://gtm.help/mcp`.
3. Server ID: `gtm-help`. Pick where to save it (see below).
4. Trust the server and sign in to gtm.help when prompted.

## Option B: config file
VS Code now prefers the portable formats, which use `mcpServers`:

Workspace `.mcp.json` (repo root) or user `~/.copilot/mcp-config.json`:
```json
{
  "mcpServers": {
    "gtm-help": {
      "type": "http",
      "url": "https://gtm.help/mcp"
    }
  }
}
```

The older VS Code-specific `.vscode/mcp.json` or user-profile `mcp.json` use `servers`:
```json
{
  "servers": {
    "gtm-help": {
      "type": "http",
      "url": "https://gtm.help/mcp"
    }
  }
}
```

## Try it
Open Chat in Agent mode and ask: "Use gtm-help to list my workspaces."

## Troubleshooting
Command Palette → **MCP: List Servers** → `gtm-help` → **Show Output**.
