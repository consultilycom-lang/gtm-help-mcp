# gtm.help in ChatGPT

Official docs: [Connect and test your plugin](https://developers.openai.com/apps-sdk/deploy/connect-chatgpt)

Custom MCP servers depend on your ChatGPT plan and your workspace policy. On some plans you first need to turn on developer mode. If you don't see the option, ask your workspace admin.

## Steps
1. Open **ChatGPT → Plugins** (formerly Connectors/Apps).
2. Click **+**, then **Add custom MCP server**.
3. Name: `gtm.help`. Description: "Your growth plan and plays from gtm.help."
4. Connection: public endpoint, URL `https://gtm.help/mcp`.
5. Authentication: **OAuth** (no API key). Review the warning, then tick **I understand and want to continue**.
6. Select **Create as a plugin** and check the 16 tools it finds.
7. Start a new chat, type `@`, choose gtm.help and ask a question.

## Try it
- "@gtm.help analyse stripe.com and give me three growth plays."
- "@gtm.help what's next on my plan?"

## Troubleshooting
If the tools change, open the connection in Plugins and click **Refresh**.
