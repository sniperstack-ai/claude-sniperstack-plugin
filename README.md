# SniperStack plugin

Find winning products, add them to your [SniperStack](https://sniperstack.com) store and
launch cash-on-delivery landing pages from Claude, ChatGPT or Codex.

The plugin connects your assistant to the SniperStack MCP server at
`https://mcp.sniperstack.com/` and adds three skills that guide it through the work.

## What it can do

| Tool | What it does | Needs an account |
| --- | --- | --- |
| `get-marketplace-radar` | Best sellers on AliExpress, 1688, Alibaba, Wildberries and Temu | No |
| `list-products` | Your products, with status and landing page count | Yes |
| `create-product` | Add a product from its details and 2 to 8 photo links | Yes |
| `import-product` | Import a product from a Shopify, YouCan, Wildberries or 1688 link | Yes |
| `create-landing-page` | Create a landing page for a product that is ready | Yes |

| Skill | Use it to |
| --- | --- |
| `find-winning-products` | Shortlist products that can sell by cash on delivery |
| `add-product` | Pick the right way to add a product, and add it |
| `launch-landing-page` | Check the product is ready and launch its page |

The assistant cannot read your orders, your buyers, your payments or your settings.

## Install

### Claude Code

```bash
claude plugin marketplace add sniperstack-team/sniperstack-plugin
claude plugin install sniperstack@sniperstack
```

Then run `/mcp`, choose **sniperstack** and sign in.

### Claude (web and desktop) without the plugin

Settings → Connectors → **Add custom connector**, and paste `https://mcp.sniperstack.com/`.

### ChatGPT and Codex

Install **SniperStack** from the plugin directory once it is listed. To test this
repository locally, add it as a repo marketplace (`.agents/plugins/marketplace.json`).

## Sign in

The first time the assistant uses a tool, it opens SniperStack in your browser. Sign in,
check the permissions, and click **Allow**. Only the account owner can connect; team
members cannot.

To disconnect, open **AI connection (MCP)** in your SniperStack account and click
**Disconnect**, or remove the connector in your assistant. Access ends at once.

Without an account, `https://mcp.sniperstack.com/public` offers the Marketplace Radar only.

## Privacy and terms

- [Privacy policy](https://sniperstack.com/en/privacy-policy#ai-assistants)
- [Terms of service](https://sniperstack.com/en/terms-of-service)

## Support

Open an issue in this repository, or contact us through [sniperstack.com](https://sniperstack.com).

## Repository layout

| Path | For |
| --- | --- |
| `.claude-plugin/plugin.json`, `.mcp.json` | Claude Code |
| `.claude-plugin/marketplace.json` | Claude Code marketplace (`sniperstack`) |
| `plugin.json`, `mcp.json` | OpenAI plugins (ChatGPT, Codex) |
| `.agents/plugins/marketplace.json` | OpenAI repo marketplace |
| `skills/` | Shared by both |
| `assets/` | Icon and logo |
