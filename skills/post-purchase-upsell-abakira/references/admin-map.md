# Admin map

## The seven menu entries

Always in this order, top of every admin screen:

| Label | Route | What it's for |
|---|---|---|
| Home | `/app` | The list of funnels — start here |
| Results | `/app/stats` | Numbers, and the eligibility panel (which orders can even see a one-click offer) |
| Buyer page | `/app/text` | Rewrite every piece of buyer-facing text (not button labels — Shopify doesn't allow that), and set the banner image at the top of the one-click page |
| Checkout | `/app/checkout` | Checkout logo width, and the shipping protection product; only in the menu with the `Scale Plus` plan |
| Warehouse sync | `/app/threepl` | 3PL connector (Picqer) — `Scale` plan |
| Subscription app | `/app/subscriptions` | Recharge connector — `Scale` plan |
| Setup | `/app/setup` | The four-step onboarding checklist |

## Home — the funnel list

`/app` lists every funnel: name, targeting condition, whether it's active, and an
"Edit offers (N)" button that opens its editor. Funnels are evaluated top to bottom;
the first active one whose condition matches wins. A funnel with **no condition**
matches everyone — so it must be last, and the app warns if one isn't. Reordering
works with both drag-and-drop and up/down arrows (arrows are the reliable one on
touch devices).

## The funnel editor — `/app/funnel/:id`

Up to four tabs, always in this order:

1. **"In the checkout"** — only present with the `Scale Plus` plan. Absent for
   everyone else.
2. **"One-click post-purchase"** — the tree of accepted/declined offers. It runs on
   different logic from the other three tabs — don't assume it behaves like them.
3. **"Thank-you page"** — blocks, plus a "Who sees it" targeting section unique to
   this tab.
4. **"Order status"** — blocks, same editor as thank-you, no targeting section.

Tabs 1, 3 and 4 share one block editor.

**One Save button**, top right, for the whole page. It writes all four tabs at once
— there's nothing to save per-tab.

## Results (`/app/stats`)

Numbers per funnel, and the **eligibility panel**: what share of recent orders could
even see the one-click page (Shopify excludes Apple Pay, Google Pay, PayPal, Amazon
Pay, buy-now-pay-later methods, gift cards, orders with no shipping address, local
delivery, multi-currency/duty orders, POS, and anything under $0.50 — this is a
platform limit, not a bug). If a merchant's buyers pay mostly by wallet, expect this
number to be low; that's Shopify, not the app.

## Buyer page (`/app/text`)

Two things live here, and they save together.

**The top banner** (added 2026-09-02), above the language selector because it is
*not* per-language: a brand strip across the top of the one-click page, the same on
every step. The merchant picks a file from their own store or uploads one — the app
never asks for a URL. Shopify requires the banner component itself to stay, so the
intro text, the product name and the discount keep showing next to the image; a
merchant who bakes them into the picture ends up with them twice, and screen readers
see none of it. Wide and short: anything taller pushes the buy button below the fold
on a phone.

**Every buyer-facing sentence**, editable, pre-filled in the store's published
languages — confirmation text, offer descriptions, the note on the order, error
messages. Button labels are the one exception: Shopify doesn't let any app make
those merchant-editable.

⚠️ Choosing or uploading an image needs the merchant's approval of the file
permission, added 2026-09-01. A merchant who installed before that sees "The app
needs your approval to read and add store files" until they close and reopen the
app.

## Setup (`/app/setup`)

Four steps, in order:

1. **"Select this app on your post-purchase page"** — done in Shopify's own
   checkout editor, not in this app. Skip this and *nothing will ever show up*,
   silently. This is the single most common reason a merchant reports "it's not
   working."
2. **"Create your first offer"**
3. **"Test it with a real order"**
4. **"Know what your buyers will and will not see"** — the eligibility limits again.

## Ready-made click paths

**"Create a bundle on the thank-you page"**
`/app` → open (or create) a funnel → "Thank-you page" tab → "Add a block" →
**Bundle** → "Add a product" for each item (2 to 4) → set "Bundle discount (%)" →
Save (top right).

**"Add a one-click offer for what a buyer just bought"**
`/app` → open a funnel → "One-click post-purchase" tab → add a node at the root →
pick the offer type → Save.

**"Target buyers who spent over a certain amount"**
`/app` → "Add funnel" → set the targeting condition on the funnel itself (not on a
block) → build its content → Save. Requires the `Pro` plan or above.

**"See if my offers are converting"**
`/app/stats` → pick the funnel.

**"Rewrite what buyers see on the offer"**
`/app/text` → edit the relevant field → Save.

**"Enable checkout blocks"**
Requires both Shopify Plus and the `Scale Plus` plan — confirm both before
promising this to a merchant.
