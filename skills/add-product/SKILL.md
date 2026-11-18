---
name: add-product
description: Add a product to the seller's SniperStack store, either by importing it from a Shopify, YouCan, Wildberries or 1688 link or from its details and photos. Use when the seller wants to add, import or create a product in SniperStack.
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

The import runs in the background. The product starts with status `importing` and
becomes `ready` when it is in the store.

## From details: `create-product`

Use it when the seller gives the details themselves.

- Required: `name` (unique in the store), `category` and `price`.
- Photos: **2 to 8**, the first one is the main photo. Give them in one of three ways:
  - `images`: photos the seller attached in this chat, when the app can pass files to
    tools.
  - `upload_id`: when the seller has photos but no public links to them. Call
    `start-product-upload` first, show the seller its link, wait until they say the
    photos are uploaded, then pass its `upload_id`.
  - `image_urls`: direct public photo links (JPG, PNG or WebP).
- Optional: `description`, `compare_price`, `sku`, `country`, `currency`,
  `target_gender`.

The product is `ready` within seconds.

## After adding

- Check the status with `get-product`. `importing`, `pending` and `generating` mean
  SniperStack is still adding the product; `failed` means the seller must fix or add it
  again in the app. Do not loop on the tool: tell the seller to check back in a minute.
- If the tool says the plan has no room, tell the seller they can upgrade the plan or
  delete a product. Do not retry.
- Give the seller the `edit_url` from the result, and offer the `launch-landing-page`
  skill once the product is `ready`.
