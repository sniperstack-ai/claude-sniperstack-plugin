# SniperStack plugin

Find winning products, add them to your [SniperStack](https://sniperstack.com) store,
launch cash-on-delivery landing pages, and ask about your orders, operators, stock and
money, from Claude.

The plugin connects your assistant to the SniperStack MCP server at
`https://mcp.sniperstack.com/` and adds three skills that guide it through the work.
Every tool needs a SniperStack account: you sign in once, when you connect.

## What it can do

### Product research

| Tool | What it does |
| --- | --- |
| `get-marketplace-radar` | Best sellers on AliExpress, 1688, Alibaba, Wildberries and Temu |
| `get-top-selling` | Products winning on Facebook, Instagram and TikTok ads, in your market |

Both show 20 products per list. If your plan includes Spy, they show 50, with the
product links and the ad copy.

### Your store

| Tool | What it does |
| --- | --- |
| `list-products` | Your products, with status and landing page count |
| `get-product` | One product's details and status |
| `create-product` | Add a product from its details and 2 to 8 photos |
| `start-product-upload` | A link where you upload photos from your phone or computer |
| `import-product` | Import a product from a Shopify, YouCan, Wildberries or 1688 link |
| `create-landing-page` | Create a landing page for a product that is ready |
| `list-landing-pages` | Your landing pages, with views, orders and links |
| `list-orders` | Your orders, with the operator and call stage of each |

### Your ERP (if your plan includes it)

| Tool | What it does |
| --- | --- |
| `list-operators` | Your call operators, their hours, products and pay |
| `get-operator-performance` | Confirmation rate, response time, and when each operator started and stopped |
| `list-activity-log` | Who changed what, on which order or record, and when |
| `get-stock` | Stock on hand, its value, and what needs restocking |
| `get-cash-position` | Account balances, cash held by delivery companies, and who you still owe |
| `list-cash-movements` | Payouts, delivery company payments, deposits and transfers |
| `list-unpaid-parcels` | Delivered parcels a delivery company has not paid for, with the days left to claim |
| `get-profit` | Profit and loss for a period |

### Skills

| Skill | Use it to |
| --- | --- |
| `find-winning-products` | Shortlist products that can sell by cash on delivery |
| `add-product` | Pick the right way to add a product, and add it |
| `launch-landing-page` | Check the product is ready and launch its page |

### What the assistant can see and do

- For each order it sees the status, the buyer's name and phone number, the wilaya and
  commune, the product, quantity, total and date. It never sees the street address.
- The ERP tools only read. The assistant cannot change or cancel an order, record a
  payment, or change your stock.
- It cannot read your subscription billing or your account settings.
- A landing page made with AI can include generated section images. They cost
  credits, so the assistant asks you how many you want first.

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
