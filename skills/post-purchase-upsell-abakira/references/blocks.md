# Blocks — the editor shared by checkout, thank-you and order-status

One editor, reused on three tabs of the funnel editor ("In the checkout",
"Thank-you page", "Order status"). What follows applies to all three unless a
difference is called out.

## Adding a block

Five buttons under "Add a block" — five distinct block types, not a dropdown:

- **Text**
- **Banner**
- **Single product**
- **Carousel**
- **Bundle**

## Fields on a product item (Single product, Carousel, or an item inside a Bundle)

- **"Add a product"** — opens Shopify's native resource picker. Checking the whole
  product offers every variant; checking specific variants makes that the buyer's
  choice list.
- **"Subtitle"** — free text, `**bold**` markdown is rendered.
- **"Discount (%)"** — not shown on a Bundle item in the checkout tab specifically:
  there, a variant carries a single rate for the whole cart line, so per-item
  discounts inside a bundle aren't applied at checkout.
- **"Quantity tiers"** — up to **3** tiers per item (quantity + discount for that
  quantity). Not available on a Bundle item.
- **"Show a quantity selector for this product"** — a checkbox, off by default. If
  the item has quantity tiers, this checkbox is replaced by a note explaining the
  tiers already provide a selector with the discount shown per quantity — the two
  don't stack.
- **"Subscription"** — only appears if the product carries Shopify selling plans.

## Bundle-specific rules

A bundle block holds **2 to 4 products**. It has its own "Bundle discount (%)"
field (0 to 100 — 100 means the item is free, and that's a merchant decision the
app states plainly rather than hides). A bundle item never has quantity tiers, no
quantity selector, and no subscription option.

⚠️ Don't confuse this 2–4 range with the **one-click** post-purchase bundle, which
allows 2–3 products — a different limit, on a different tab.

## What differs by surface

| | Checkout | Thank-you | Order status |
|---|---|---|---|
| "Who sees it" targeting section | — | ✅ (5 rules, see below) | — |
| "Urgency" (countdown) | ❌ never — Shopify App Store rule 5.6.6 forbids countdown timers in checkout UI extensions | ✅ 30 seconds to 72 hours, counted from when the order was placed (same deadline on every visit/device) | ✅ same as thank-you |
| Bundle item discount shown | not applied per item (see above) | ✅ | ✅ |

## "Who sees it" (thank-you tab only)

Five options: **Everyone** (default) · buyers who did not see the one-click page ·
buyers who accepted a specific offer · buyers who accepted at least one offer ·
buyers who refused everything. This lets the same funnel show a different
thank-you message depending on how the one-click step went — most useful for a
"last chance at a better price" block aimed only at buyers who said no upstream.

## "Urgency" (thank-you and order-status only)

A countdown from 30 seconds to 72 hours. It's anchored to the order's timestamp,
not to when the page loads — reloading doesn't reset it. When it reaches zero the
block simply disappears; nothing about it is decorative.
