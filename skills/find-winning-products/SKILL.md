---
name: find-winning-products
description: Research products that sell right now on AliExpress, 1688, Alibaba, Wildberries and Temu with the SniperStack Marketplace Radar, and shortlist the best candidates for a cash-on-delivery store. Use when the seller asks what to sell, wants winning or trending products, or wants product ideas for a market.
---

# Find winning products

Use the `get-marketplace-radar` tool from the SniperStack connector. It returns the
current best sellers per marketplace, ranked by orders (by search position on
Wildberries), with prices in USD.

## Steps

1. Ask which marketplace the seller sources from, if they did not say. Pass it as
   `provider` (`aliexpress`, `1688`, `alibaba`, `wildberries`, `temu`), or leave it
   out to see all of them.
2. Call `get-marketplace-radar`.
3. Shortlist 3 to 5 products. For each one, give:
   - the title, marketplace, sale price and orders count, as returned;
   - why it can sell by cash on delivery: a visible problem it solves, a "wow"
     effect that shows well in a short video, and a price buyers accept without
     seeing the product first;
   - a rough selling price for the seller's market, clearly marked as an estimate.
4. Prefer products marked `new_this_week`, and say so: they are rising, not saturated.
5. Never invent numbers. Every orders count, price and rating comes from the tool.

## Next step

Offer to add a shortlisted product to the seller's store with the `add-product`
skill. The Radar is a free preview; the full Radar is in the SniperStack app
(`full_radar_url` in the result).
