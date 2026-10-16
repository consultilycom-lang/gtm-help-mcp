# Submitting gtm.help MCP: per-directory checklist
Prepared 15 Oct 2026. Nothing submitted. Replace `consultilycom-lang` with the real GitHub org/user once the repo exists.

## Blockers
| # | Blocker | Affects |
|---|---|---|
| B1 | **Public GitHub repo** (push this folder, e.g. `github.com/<org>/gtm-help-mcp`) | mcp.so, MCP Market, punkpeye main list, Cursor Marketplace |
| B2 | **Server card deployed** at `https://gtm.help/.well-known/mcp/server-card.json` (draft: `/workspace/gtm-mcp-kit/server-card.json`). **Dev must replace the guessed `inputSchema`s with the real `tools/list` output** (the argument names are my guesses). Serve as `application/json`, with CORS `*` and no auth. | Smithery (scan fallback), helps Glama and reviewers |
| B3 | **Unauthenticated MCP handshake.** `initialize` currently returns 401. punkpeye/awesome-remote-mcp-servers CI requires the endpoint to answer `initialize`, and Glama only indexes "healthy" connectors. Fix: allow `initialize` + `tools/list` without a token and keep OAuth for `tools/call`. Or give Glama test credentials. | punkpeye remote list, Glama (likely) |
| B4 | **Sign-ins** (Rhys's accounts): Smithery, Glama, MCP Market, mcp.so, OpenTools | those directories |
| B5 | **Official MCP Registry publish** (DNS TXT, see `/workspace/gtm-mcp-kit/NEXT-STEPS.md`) | PulseMCP auto-ingest, Glama registry link |
| B6 | **Cloudflare bot protection**: make sure `SmitheryBot/1.0` and Glama's checker aren't blocked (Smithery docs flag Bot Fight Mode) | Smithery, Glama |

## Per directory
| Directory | Method (verified 15 Oct) | Ready | Blocked by |
|---|---|---|---|
| **Smithery** | smithery.ai/new → paste `https://gtm.help/mcp`. URL publishing, no `smithery.yaml` needed for remote servers (that's only for Smithery-hosted builds). Auth servers: Smithery prompts you to sign in to scan, or reads the static server card. Uses Client ID Metadata Documents for OAuth. | URL, server card draft, description | B4. B2 recommended. B6. |
| **Glama** | glama.ai/mcp/connectors → Add MCP Server → **Connector**: name, short description, HTTPS streamable-http URL, optional private test credentials. Also auto-links from the Official Registry. | Form answers below | B4. B3 or test creds. B5 helps. |
| **mcp.so** | mcp.so/submit: needs a **GitHub repository URL** + name. Free review, or $39 for instant publish, badge and dofollow link. | Repo contents | B1, B4 |
| **PulseMCP** | **Still paused** (notice dated 3 Sep 2026). It ingests from the Official MCP Registry when it reopens. | server.json | B5 (then nothing more to do) |
| **OpenTools** | The opentools.com CLI/registry repo is **retired**; it points to the Official MCP Registry. The current listing route is **paid**: opentools.ai/friends/launch-mcp → sign in, enter name and URL → checkout (price only shown at checkout), then add description, docs, setup and tags. Includes X/LinkedIn launch posts. | Form answers below | B4. **Needs Rhys's go-ahead to pay.** |
| **punkpeye/awesome-mcp-servers** | CONTRIBUTING: the main list is **only for servers with a public, installable repo**. **Remote-only servers go to `punkpeye/awesome-remote-mcp-servers`.** PR edits README.md. Entries need a **Glama connector badge**. CI checks that the endpoint answers `initialize`. | Entry below | B3, Glama listing first, GitHub account |
| **wong2/awesome-mcp-servers** | README: **"We do not accept PRs. Please submit your MCP on the website: https://mcpservers.org/submit"** | mcpservers.org answers below | none (form, no account) |
| **MCP Market** | mcpmarket.com/submit: **GitHub repository URL** (+ email). Sign-in prompts present. | Repo contents | B1, B4 |

## Draft entries and form answers

### punkpeye/awesome-remote-mcp-servers (section `### 🎯 Marketing`, alphabetical)
```markdown
- [gtm.help](https://gtm.help/for-agents) `https://gtm.help/mcp`
  [![gtm.help MCP connector](https://glama.ai/mcp/connectors/help.gtm/gtm-help/badges/score.svg)](https://glama.ai/mcp/connectors/help.gtm/gtm-help)
  🔐 - Ranked growth plays for your business, buyer conversations to answer, and site analysis with costed plays.
```
- Legend: 🔐 = OAuth. The description must be one sentence, ≤120 characters, ending with a period.
- The badge path `help.gtm/gtm-help` is a guess. Use the namespace from the actual Glama connector URL once listed.
- PR title: `Add gtm.help remote MCP server`. Don't add the 🤖🤖🤖 suffix unless an agent opens the PR.

### punkpeye/awesome-mcp-servers (main list): only if they'd accept a docs repo. Scope says installable repos only, so **don't submit there**. If ever applicable (Marketing section; ☁️ = cloud service; 🎖️ = official; language emoji n/a):
```markdown
- [consultilycom-lang/gtm-help-mcp](https://github.com/consultilycom-lang/gtm-help-mcp) 🎖️ ☁️ - Official gtm.help server: ranked go-to-market plays, buyer-conversation drafts and free site analysis over OAuth.
```

### mcpservers.org (= wong2 list)
- Server Name: `gtm.help`
- Category: `Marketing`
- Short Description: `Your go-to-market plan inside any AI agent: analyse a site, get ranked costed growth plays, move them, and draft replies to Reddit/LinkedIn/X conversations. OAuth.`
- Repository, Website or Documentation: `https://gtm.help/for-agents` (or the GitHub repo once public)
- Official MCP Registry Name: `help.gtm/gtm-help` (only after publishing)
- Supports remote connections: ✅
- Contact Email: `team@gtm.help`
- Plan: Free (2-week review). $39 premium only if Rhys approves.

### mcp.so
- Repository URL: `https://github.com/consultilycom-lang/gtm-help-mcp`
- Name: `gtm.help`
- If asked: description as above, server URL `https://gtm.help/mcp`, transport Streamable HTTP, auth OAuth, category Marketing / Productivity, tags `marketing, growth, go-to-market, seo, reddit, linkedin`.

### MCP Market
- Type: MCP Server
- GitHub repository URL: `https://github.com/consultilycom-lang/gtm-help-mcp`
- Email: `team@gtm.help`

### Glama (Connector)
- Name: `gtm.help`
- Short description: `Ranked go-to-market plays, buyer-conversation drafts and free site analysis for your business.`
- Server URL: `https://gtm.help/mcp` (streamable-http)
- Credentials: OAuth (leave API key blank). Optionally share a test account privately.
- Category: Marketing. Thumbnail: `assets/logo.png`.

### Smithery
- URL: `https://gtm.help/mcp`
- Namespace/name: `@gtm-help/gtm-help` (or Rhys's chosen org)
- Display name `gtm.help`, description as above, homepage `https://gtm.help/for-agents`, icon `assets/logo.png`
- Complete the OAuth scan prompt when asked, or rely on the server card.

### OpenTools (paid)
- MCP name: `gtm.help`
- Public URL: `https://gtm.help/mcp`
- After checkout:
  - Description: long README intro.
  - Docs: `https://gtm.help/for-agents`.
  - Setup: the Cursor JSON snippet.
  - Tags: marketing, growth, go-to-market, SEO, AI search, Reddit, LinkedIn.
  - Features: the 15-tool table.

## Suggested order
1. Publish to the Official Registry (B5).
2. mcpservers.org form.
3. Deploy the server card and allow an unauthenticated handshake (B2, B3).
4. Smithery, then Glama.
5. Push the GitHub repo, then mcp.so and MCP Market.
6. punkpeye remote-list PR (after the Glama badge exists).
7. OpenTools if paying.
8. PulseMCP happens automatically when it reopens.
