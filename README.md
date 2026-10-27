# OpenAccountants for Windsurf

Use [OpenAccountants](https://www.openaccountants.com) tax skills inside Windsurf via the Cascade panel's MCP support.

Skills include accountant-reviewed versions and source-cited drafts. Check the [current catalogue](https://www.openaccountants.com/skills) and [review method](https://www.openaccountants.com/review-method) for each skill's review status, reviewer, version and review date. Authorship or a jurisdiction lead's name does not establish professional review of every skill version.

## Install (manual, ~30 seconds)

Open `~/.codeium/windsurf/mcp_config.json` (create it if it doesn't exist) and add:

```json
{
  "mcpServers": {
    "openaccountants": {
      "serverUrl": "https://www.openaccountants.com/api/mcp"
    }
  }
}
```

Restart Windsurf. Open Cascade, type a tax question, and the agent will call OpenAccountants automatically.

## Install (via Marketplace, when listed)

1. Open Windsurf → click the **MCPs** icon in the Cascade panel's top-right menu (or open `Windsurf Settings → Cascade → MCP Servers`)
2. Search **OpenAccountants**
3. Click **Install**
4. Restart Cascade

> Status: marketplace listing pending — discoverable via [Smithery](https://smithery.ai) (the upstream registry Windsurf pulls from). Until then, use the manual install above.

## What you get

| Tool | Purpose |
|---|---|
| `start` | Front door — pass intent + jurisdiction → ready-to-execute plan |
| `list_skills` | List published skills filtered by jurisdiction / category |
| `get_skill` | Fetch full markdown + provenance footer for one skill |
| `get_skill_sections` | Same content split into sections (for very large skills) |
| `search_skills` | Keyword search across published skill content |

All read-only. Rate-limited at 60 req/min per IP. No auth, no signup.

## Try it

After installing, ask Cascade:

> *I'm a Maltese freelancer earning EUR 45,000 from foreign clients. What VAT obligations do I have, and is there a small-enterprise scheme I should consider?*

Cascade should call `start({intent: 'VAT', jurisdiction: 'MT'})`, then `get_skill({slug: 'malta-vat-return'})`, then walk you through Malta VAT Article 10 vs Article 11, the EUR 35,000 threshold, EU reverse charge logic, and the Calendly link for a verified Malta accountant.

## Disclaimer

These skills produce **working papers, not filed returns**. Every output preserves a "Talk to a verified accountant" footer with a Calendly link. No client–accountant relationship is created by reading or applying these skills.

## Links

- Website: [openaccountants.com](https://www.openaccountants.com)
- Skills source: [github.com/openaccountants/openaccountants](https://github.com/openaccountants/openaccountants); [content terms](https://github.com/openaccountants/openaccountants/blob/main/LICENSING.md)
- MCP server: `https://www.openaccountants.com/api/mcp`
- Universal server-card: `https://www.openaccountants.com/.well-known/mcp/server-card.json`
- Verified accountant network: [openaccountants.com/network](https://www.openaccountants.com/network)
- Book a verified accountant: [calendly.com/openaccountants-info/30min](https://calendly.com/openaccountants-info/30min)

## Licence

MIT for this repository. Skill content has separate terms from this wrapper. The source repository's [licensing document](https://github.com/openaccountants/openaccountants/blob/main/LICENSING.md) describes the source-available Open Accountants Skills License, commercial options, third-party copyleft exceptions and prior AGPL releases. Check the terms for the skill version you use.
