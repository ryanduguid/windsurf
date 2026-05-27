# Smithery submission — one-time setup

Smithery is the de-facto upstream MCP registry that Windsurf, Cursor, Claude Desktop, Cline, and other MCP-aware tools pull from. **Publishing to Smithery makes OpenAccountants discoverable across ALL of them with one submission.**

## Step-by-step (5 minutes)

1. Open https://smithery.ai/new
2. Paste the server URL: `https://www.openaccountants.com/api/mcp`
3. Smithery's autoscanner will introspect the server and pre-fill:
   - Name: OpenAccountants
   - Description: from the MCP server's `initialize` response
   - Tool list: from `tools/list`
   - Categories: pulled from our `/.well-known/mcp/server-card.json`
   - Icon, branding, publisher info: pulled from the same server-card
4. Confirm or edit the metadata. The server-card.json should make this near-zero-edit.
5. Click **Publish**.

Smithery requires no GitHub repo, no Dockerfile, no smithery.yaml for URL-based servers — they proxy through Smithery Gateway, which is fine since we're rate-limited anyway.

## After it's live

- Visit your Smithery listing to verify the metadata looks right
- Smithery exposes a deeplink format: `https://smithery.ai/server/openaccountants` (or similar — the actual URL comes from Smithery on publish)
- That deeplink works in any MCP-aware tool: Cursor's marketplace, Windsurf's MCP browser, Cline, etc.

## What this gives us

| Tool | Effect of Smithery listing |
|---|---|
| **Windsurf** | Surfaced in the in-app MCP marketplace browser |
| **Cursor** | Discoverable via Cursor's MCP search (complementary to our submitted plugin) |
| **Claude Desktop** | Smithery deeplinks work in Claude Desktop's plugin install flow |
| **Cline** | Smithery is Cline's primary MCP registry |
| **Any future MCP-aware tool** | Smithery is becoming the canonical registry, so listing here future-proofs us |

## What you (Michael) need to do

1. Sign up at smithery.ai (use `michael@openaccountants.com` or whatever — no special requirements)
2. Follow the 5-step flow above
3. Tell me the resulting Smithery URL — I'll add it to all our other distribution channels' READMEs

## Notes

- Smithery's autoscanner might fail to introspect our MCP server because of the rate limit (60/min). If so, manually paste the contents of `https://www.openaccountants.com/.well-known/mcp/server-card.json` into the override field.
- Smithery offers free hosting/proxy for MCP servers. **Skip that** — we have our own infrastructure and don't want them in the path.
