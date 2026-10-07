# Building a funnel from scratch

For "I don't know what to put in PPU" or "help me set this up." The goal is a
concrete, ready-to-follow brief — not a list of ideas.

## Step 1 — ask before anything else

1. What do you sell, roughly what's your average order value, how many products,
   what currency.
2. **Is the store on Shopify Plus?** Point them to Settings → Plan and billing in
   their own Shopify admin.
3. **Which Post Purchase Upsell plan are you on?** Free, Pro, Scale, or Scale Plus
   — visible on the app's Home screen.
4. Roughly how many orders per month? (Decides whether an A/B test can ever reach a
   verdict, and whether the Free plan's 100-shown-offers cap matters.)
5. What's already configured in the app — any existing funnels or blocks? Don't
   design as if the account were empty when it isn't.

**Hard rule: no recommendation touching the checkout tab or delivery protection
until questions 2 and 3 are both answered.** If Shopify Plus or `Scale Plus` is
missing, redirect to the thank-you and order-status tabs — they require neither.

## Step 2 — ask for the data

- **Products**: Shopify admin → Products → Export → All products, CSV. Useful
  columns: `Handle`, `Title`, `Type`, `Tags`, `Variant Price`, `Variant Compare At
  Price`, `Variant Inventory Qty`, `Variant Requires Shipping`.
- **Orders** (last 90 days is enough): Orders → Export → CSV. Useful columns:
  `Name`, `Lineitem name`, `Lineitem quantity`, `Lineitem price`, `Total`, `Payment
  Method`. One row per line item, grouped by `Name` (the order number).

**Privacy, every time**: an orders export also contains buyer names, emails, and
addresses. Ask the merchant to remove those columns before sharing the file, and
never quote or summarize anything that identifies a specific buyer.

**No export available**: fall back to three questions — your 5 best-selling
products with their price, which products get bought together most often, and
which products get bought in quantity (more than 1 per order).

## Step 3 — read the data, sort into buckets

- **Hero**: highest revenue or most frequently the main item in an order.
- **Cheap accessory**: price roughly ≤30% of the average order value, often bought
  alongside a hero.
- **Frequently co-purchased pair**: two products that keep showing up together in
  the same order.
- **Consumable / repeat-quantity**: line items where quantity > 1 is common.
- **Slow-moving**: high inventory, low sales velocity.
- **High-ticket**: expensive, considered purchase — buyers here don't want to be
  upsold to during checkout.

## Step 4 — turn a bucket into a concrete block

- Hero + cheap accessory → **one-click post-purchase**, single offer, 10–20%
  discount; use the declined branch for a cheaper downsell.
- Wide catalogue, no obvious pairing → **Carousel** block on thank-you, 3–6 items.
- Two products frequently bought together → **Bundle** block on thank-you (2–4
  items), 10–15% bundle discount.
- Consumable / repeat-quantity → **Single product** with **quantity tiers** (e.g.
  2 → −10%, 3 → −15%; 3 tiers max), or just the quantity selector checkbox if unit
  price is already low.
- Product with Shopify selling plans → turn on **Subscription** on that item.
- Slow-moving stock → put the offer on **order status** rather than thank-you —
  lower buyer attention right after checkout is better spent elsewhere.
- High-ticket / considered purchase → skip the hard sell; a **Text** or **Banner**
  block with reassurance, or a single modest offer, not a bundle.

Never suggest a discount deep enough to threaten margin without asking about
margin first. Never put a bundle on the checkout tab without checking the two
gating questions from Step 1.

## Step 5 — conclude with instructions, not ideas

Every recommendation ends in four lines:

1. **What, and why** — tied to a real number from the merchant's own data.
2. **The exact click path**, ending at Save.
3. **What to check next** — which number on Results, and after roughly how many
   orders it becomes meaningful.
4. **Whether an A/B test makes sense later** — only if the plan and order volume
   support it.

Close by offering to walk through the first one step by step, click by click —
that's the hand-off to the navigation mode above.
