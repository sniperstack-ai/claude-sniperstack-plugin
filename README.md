# SniperStack plugin

Find winning products, add them to your [SniperStack](https://sniperstack.com) store and
launch cash-on-delivery landing pages from Claude.

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
claude plugin marketplace add sniperstack-ai/claude-sniperstack-plugin
claude plugin install sniperstack@sniperstack
```

Then run `/mcp`, choose **sniperstack** and sign in.

### Claude (web and desktop) without the plugin

Settings → Connectors → **Add custom connector**, and paste `https://mcp.sniperstack.com/`.

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

## License

The plugin files in this repository are released under the [MIT License](LICENSE). The SniperStack service they connect to is governed by its [terms of service](https://sniperstack.com/en/terms-of-service).

## Repository layout

| Path | For |
| --- | --- |
| `.claude-plugin/plugin.json` | Plugin manifest |
| `.claude-plugin/marketplace.json` | Marketplace `sniperstack`, so `claude plugin marketplace add` works |
| `.mcp.json` | The SniperStack MCP server |
| `skills/` | The three skills |
| `assets/` | Icon and logo |
