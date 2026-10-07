# Plans, and the Shopify Plus question

## What each plan unlocks

No prices here — see "Where to check the price" below. Higher plans include
everything the ones below them include.

- **Free** — 100 offers *shown* to buyers per month, 1 funnel, 1 level of the
  one-click tree (root only).
- **Pro** — unlimited offers shown, up to 3 levels / 7 offers in the one-click
  tree, up to 20 funnels, targeting conditions on funnels, the "intelligent"
  thank-you rules (conditioned on what happened at the one-click step).
- **Scale** — everything in Pro, plus A/B testing on blocks, the warehouse (3PL)
  connector, and the subscription connector.
- **Scale Plus** — everything in Scale, plus blocks in the checkout itself and the
  delivery-protection feature. This is the one plan that only does anything for a
  **Shopify Plus** store — see below.

The plan name to use in conversation is exactly **"Scale Plus"**, two words. Its
internal handle (`scale_plus`) or any other spelling is not what the merchant sees
in Shopify's plan picker.

## Where to check the price

Never state a number. Send the merchant to: **Home (`/app`) → the plan gauge at
the top → "View or change plan"**. That page is always current; anything written
here would not be.

## The two independent facts

These answer two *different* questions, and getting them confused is the single
most common way to misconfigure the checkout tab:

1. **Is the store on Shopify Plus?** — a fact about the **Shopify platform**,
   decided by Shopify, not by this app. Checkout UI extensions (which is what "In
   the checkout" blocks and delivery protection actually are) only render on
   Shopify Plus stores, full stop — no plan on this app changes that.
   - How the merchant checks it themselves: their **Shopify admin → Settings →
     Plan and billing**. If it says Shopify Plus (including a Plus trial or Plus
     sandbox), they're capable.
   - How it shows up inside this app: if the **"Delivery protection"** menu entry
     is visible but opens to a red banner reading **"Your store is not on Shopify
     Plus,"** the store is not Plus-capable. If the menu entry isn't there at all,
     that means the *other* fact (below) is missing instead — check that one.

2. **Which Post Purchase Upsell plan is the merchant on?** — a fact about **this
   app's billing**, decided by us. Checked via **Home → the plan gauge**, or
   directly: is "Delivery protection" in the menu at all? It's only shown to
   merchants on `Scale Plus`.

## Every combination, and what actually happens

| Shopify Plus? | PPU plan `Scale Plus`? | What happens |
|---|---|---|
| No | No | Nothing checkout-related is offered — correct, nothing to build here |
| No | Yes | Everything in the admin saves normally, but **no buyer will ever see it** — the platform silently never renders the extension. This produces zero errors and zero support tickets; it just doesn't work. Don't let a merchant pay for this without being Plus first. |
| Yes | No | The right platform, missing the app plan — the fix is upgrading inside this app |
| Yes | Yes | Checkout blocks and delivery protection both work |

**Never recommend anything on the "In the checkout" tab, or delivery protection,
without the merchant having confirmed both facts separately, using the checks
above.** If either is missing or unconfirmed, work on the thank-you and
order-status tabs instead — they need neither.
