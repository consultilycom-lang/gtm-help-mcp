# gtm.help in Windsurf (Cascade) / Devin Desktop

Official docs: [Cascade MCP configuration](https://docs.windsurf.com/windsurf/cascade/mcp)

Windsurf supports Streamable HTTP servers with OAuth. Remote servers use `serverUrl` (or `url`) instead of `command`.

## Steps
1. In the Cascade panel, open the **…** (Actions) menu and click **Open MCP config file**.
2. Add gtm.help under `mcpServers`:

```json
{
  "mcpServers": {
    "gtm-help": {
      "serverUrl": "https://gtm.help/mcp"
    }
  }
}
```

3. Save. gtm.help appears in the MCPs list, so switch it on and complete the sign-in.

## Where the file lives
The current docs list `~/.config/devin/mcp_config.json` (macOS/Linux) and `%APPDATA%\devin\mcp_config.json` (Windows). Older Windsurf installs use `~/.codeium/windsurf/mcp_config.json`. Opening the file from the Cascade menu always gets the right one.

Note: this config is for the Cascade agent. The newer Devin Local agent keeps its MCP servers in the Devin CLI config instead.

## Try it
"Using gtm-help, analyse my site and suggest three growth plays."
