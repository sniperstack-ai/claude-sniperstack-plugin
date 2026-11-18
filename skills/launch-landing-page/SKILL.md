---
name: launch-landing-page
description: Create a cash-on-delivery landing page for a product in the seller's SniperStack store. Use when the seller wants to launch, sell or make a landing page for a product.
---

# Launch a landing page

## 1. Find the product

Call `list-products` from the SniperStack connector. Use `search` to find the product
by name or SKU, or `status: "ready"` to see which products can get a page now.

- Only a product with status `ready` can get a landing page.
- `importing`, `pending` or `generating` means SniperStack is still adding the
  product. Tell the seller to wait a minute and check again; do not loop on the tool.
- `failed` means the seller must fix or add the product again. Send them to its
  `edit_url`.

## 2. Ask before creating

- `content_source`: `ai` (default) writes the page copy with AI. `manual` uses the
  product's own name, description and photos, with no AI.
- For an `ai` page, **ask the seller how many section images** SniperStack should
  generate, and pass it as `image_count` (0 to 4; some designs allow fewer). Do not
  choose for them. Images cost credits; 0 keeps the product's own photos and costs
  nothing.
- `image_quality` (optional): `low` (default), `medium` or `high`. The tool's
  description gives the credits per image. Medium and high need a paid plan.

## 3. Create the page

Call `create-landing-page` with the product's `id` as `product_id`, plus the choices
above.

- `theme` (optional): the page design. Left out, SniperStack picks the design
  recommended for the product. It cannot be changed later, so only set it when the
  seller asks for a specific design.
- `country` (optional): sets the page language and currency. Defaults to the
  product's country.

With `ai`, the page goes live at once with `generation_status: "generating"` and fills
in within a few minutes. The first `ai` page for a product takes about a minute longer.
Give the seller both links from the result: `public_url` (the page buyers see) and
`builder_url` (where they edit it). Use `list-landing-pages` to check when the page is
`ready`.

If the tool says the plan has no room, or there are not enough credits, tell the seller
they can upgrade the plan. Do not retry.
