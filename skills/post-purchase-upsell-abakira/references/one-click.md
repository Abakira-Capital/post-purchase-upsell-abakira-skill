# The one-click post-purchase tab

This tab is **structurally different** from the other three. It is not a list of
blocks — it's a binary tree of accepted/declined offers. Don't reuse the block
editor's logic here; the two share almost nothing.

## The tree

Each offer has its own two children: one for a buyer who just accepted it, one for
a buyer who just declined it. That branching *is* the targeting — there is no
separate condition to configure, unlike the other tabs.

Up to **3 levels**, **7 offers** total (1 + 2 + 4). A single buyer never sees more
than 3 of them, one per level, following the path their own answers create.

Shopify itself caps a checkout at **3 accepted offers per order** — the platform
limit, not ours. A merchant asking for a 4th accepted offer in a single order is
asking for something Shopify does not allow.

## What's allowed here that isn't allowed on blocks

- **Countdown timers** — allowed on this tab (App Store rule 5.6.6 only forbids
  them in the checkout UI extension, and this page isn't that).
- **Social proof** ("N% of buyers added this") — allowed here, and it's always
  measured from real store events, never a number the merchant types in.

## Bundle on this tab

**2 to 3 products** — not the 2–4 range of block bundles on the other tabs. Same
"Bundle discount (%)" field.

## Why some buyers never see this page

Shopify does not show the post-purchase page for Apple Pay, Google Pay, PayPal,
Amazon Pay, buy-now-pay-later methods (Klarna, Affirm, AfterPay…), gift cards,
orders with no shipping address, local delivery, multi-currency or duty orders,
POS sales, or orders under $0.50. This is a platform limit — the app cannot change
it, and it isn't a bug.

The eligibility panel on **Results** (`/app/stats`) tells the merchant what share
of their *own* recent orders are actually eligible. If a store is mostly Apple Pay
or PayPal, expect a low number — that's the platform, and it's worth saying so
before the merchant builds an elaborate tree that few buyers will ever see. In that
case, point them toward the thank-you and order-status tabs instead: those show to
every buyer regardless of payment method.
