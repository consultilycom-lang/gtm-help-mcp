# gtm.help in Cursor

Official docs: [Cursor: Model Context Protocol](https://cursor.com/docs/context/mcp)

Cursor supports remote Streamable HTTP servers with OAuth.

## Option A: mcp.json
Create `.cursor/mcp.json` in your project (project-only), or `~/.cursor/mcp.json` (all projects):

```json
{
  "mcpServers": {
    "gtm-help": {
      "url": "https://gtm.help/mcp"
    }
  }
}
```

Open **Customize** in the sidebar, make sure `gtm-help` is switched on, and complete the gtm.help sign-in when Cursor asks. No API key or headers are needed.

## Option B: cursor.directory
gtm.help is on [cursor.directory](https://cursor.directory/plugins/gtmhelp). Click **Add to Cursor** and authenticate.

## Try it
In Agent chat: "Using gtm-help, what should I ship this week?"

## Troubleshooting
Open the Output panel (Cmd/Ctrl+Shift+U) and choose **MCP Logs**. Most failures are a sign-in that wasn't finished, so toggle the server off and on to retry.
