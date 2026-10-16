# gtm.help in Claude (claude.ai, Claude Desktop, Cowork)

Official docs: [Get started with custom connectors using remote MCP](https://support.claude.com/en/articles/11175166-getting-started-with-custom-connectors-using-remote-mcp)

Custom connectors work on the Free, Pro, Max, Team and Enterprise plans. Free accounts are limited to one custom connector. A connector you add on claude.ai also appears in Claude Desktop and the mobile apps, because Claude connects from Anthropic's cloud and not from your computer.

## Pro and Max
1. Go to **Customize → Connectors**.
2. Click **+ Add**, then **Add custom connector**.
3. Name: `gtm.help`. URL: `https://gtm.help/mcp`. Click **Continue**.
4. Keep the detected authentication (OAuth) and the recommended OAuth client. Click **Add**.
5. Click **Connect** and sign in to gtm.help.
6. In a chat, open **+ → Connectors** and switch on gtm.help.

## Team and Enterprise
An Owner adds it once: **Organization settings → Connectors → Add → Custom → Web**, name `gtm.help`, URL `https://gtm.help/mcp`, Authentication **Sign in when needed**. Each member then opens **Customize → Connectors**, finds gtm.help and clicks **Connect**.

## Claude Code
```bash
claude mcp add --transport http gtm-help https://gtm.help/mcp
```
Then run `/mcp` inside Claude Code and finish the sign-in.

## Try it
- "Use gtm.help to analyse acme.com and give me three growth plays."
- "List my gtm.help workspaces and show the top plays on my plan."
- "Mark the cold outbound play as started."

## Notes
- gtm.help never posts for you. `draft_reply` writes a reply and gives you the link, and you post it yourself.
- Write tools (moving plays, notes, watchlist edits) ask for approval unless you choose "Allow always".
