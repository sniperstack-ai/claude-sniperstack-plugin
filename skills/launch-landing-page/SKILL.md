---
name: launch-landing-page
description: Create a cash-on-delivery landing page for a product in the seller's SniperStack store. Use when the seller wants to launch, sell or make a landing page for a product.
---

# Launch a landing page

## 1. Find the product

Call `list-products` from the SniperStack connector. Use `search` to find the product
by name or SKU, or `status: "ready"` to see which products can get a page now.

- Only a product with status `ready` can get a landing page.
- `importing`, `pending` or `generating` means the AI analysis is still running. Tell
  the seller to wait a few minutes and check again; do not loop on the tool.
- `failed` means the analysis failed. Send the seller to the product's `edit_url`.

## 2. Create the page

Call `create-landing-page` with the product's `id` as `product_id`.

- `content_source`: `ai` (default) writes the copy and makes section images;
  `manual` uses the product's own name, description and photos with no AI.
- `theme` (optional): the page design. Left out, SniperStack picks the design
  recommended for the product. It cannot be changed later, so only set it when the
  seller asks for a specific design.
- `country` (optional): sets the page language and currency. Defaults to the
  product's country.
- `image_count` (optional, AI only): 0 to 4 section images. Each theme allows only
  some counts; if the tool refuses the number, use one it lists or leave it out.

With `ai`, the page goes live at once with `generation_status: "generating"` and
fills in over a few minutes. Give the seller both links from the result:
`public_url` (the page buyers see) and `builder_url` (where they edit it).

If the tool says the plan has no room, tell the seller they can upgrade the plan.
