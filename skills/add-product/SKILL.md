---
name: add-product
description: Add a product to the seller's SniperStack store, either by importing it from a Shopify, YouCan, Wildberries or 1688 link or from its details and photo links. Use when the seller wants to add, import or create a product in SniperStack.
---

# Add a product to SniperStack

Two tools from the SniperStack connector add products. Pick by what the seller has.

## From a link: `import-product`

Use it for a Shopify or YouCan product page (`/products/...`), a Wildberries listing
(`/catalog/{id}/detail.aspx`) or a 1688 offer page. Other links, such as AliExpress,
are refused: use `create-product` for those.

- `url`: the product page link.
- `price`: the selling price in the seller's store currency. **Always ask the seller
  for it.** Wildberries and 1688 publish no retail price, so the import cannot pick one.
- `compare_price` (optional): a "before" price shown struck through.

The import runs in the background; the product starts with status `importing`.

## From details: `create-product`

Use it when the seller gives the details themselves.

- Required: `name` (unique in the store), `category`, `price`, and `image_urls` —
  **2 to 8** direct public photo links (JPG, PNG or WebP). The first is the main photo.
- Optional: `description`, `compare_price`, `sku`, `country`, `currency`,
  `target_gender`.

The product starts with status `pending`.

## After adding

- AI analysis prepares the product for landing pages. It takes a few minutes, and the
  status then becomes `ready`.
- If the tool says the plan has no room, tell the seller they can upgrade the plan or
  delete a product. Do not retry.
- Give the seller the `edit_url` from the result, and offer the `launch-landing-page`
  skill once the product is `ready`.
