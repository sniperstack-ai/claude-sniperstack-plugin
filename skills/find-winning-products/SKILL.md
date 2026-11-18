---
name: find-winning-products
description: Research products that sell right now, on AliExpress, 1688, Alibaba, Wildberries and Temu and in Facebook, Instagram and TikTok ads, with SniperStack, and shortlist the best candidates for a cash-on-delivery store. Use when the seller asks what to sell, wants winning or trending products, or wants product ideas for a market.
---

# Find winning products

Two tools from the SniperStack connector find products that sell:

- `get-marketplace-radar`: the current best sellers on the sourcing marketplaces,
  ranked by orders (by search position on Wildberries), with prices in USD.
- `get-top-selling`: the products winning on social ads in the seller's market: the
  advertisers pushing a product hardest and longest on Facebook and Instagram, and the
  best TikTok ads by click-through rate.

## Steps

1. Pick the tool by what the seller asks. "What sells on AliExpress" is the Radar;
   "what is winning in my market" is Top Selling. Use both when the seller just asks
   what to sell.
2. For the Radar, ask which marketplace the seller sources from, if they did not say.
   Pass it as `provider` (`aliexpress`, `1688`, `alibaba`, `wildberries`, `temu`), or
   leave it out to see all of them.
3. Top Selling covers the seller's own market. Pass `country` only when they ask about
   another market.
4. Shortlist 3 to 5 products. For each one, give:
   - the title, source and the numbers the tool returned (orders and price on the
     Radar; days running and creatives, or likes and click-through rate, on Top
     Selling);
   - why it can sell by cash on delivery: a visible problem it solves, a "wow"
     effect that shows well in a short video, and a price buyers accept without
     seeing the product first;
   - a rough selling price for the seller's market, clearly marked as an estimate.
5. On the Radar, prefer products marked `new_this_week`, and say so: they are rising,
   not saturated. On Top Selling, an ad still running after many days is a strong sign.
6. Never invent numbers. Every orders count, price, rating and ad figure comes from the
   tool.

## Next step

Offer to add a shortlisted product to the seller's store with the `add-product`
skill. A row marked `importable` can be added straight from its link.
