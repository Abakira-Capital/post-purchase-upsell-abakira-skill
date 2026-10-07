# "Nothing is showing up"

Ranked by how often each cause is the real one. Ask the merchant to check them in
this order rather than guessing at the first idea that comes to mind.

## 1. Step 1 of Setup was never done

The most common cause by far. The app must be **selected in Shopify's own
post-purchase page editor** — this is a step inside Shopify's checkout customization
tool, not inside this app. Without it, the one-click page never renders, silently,
for anyone. Check: `/app/setup`, step 1.

## 2. The change was never saved

There's exactly **one Save button**, top right of the funnel editor. It's easy to
edit a block, navigate to a different tab, and lose the change without noticing.
Re-open the funnel and confirm the edit is still there.

## 3. On the Free plan, the monthly cap is reached

100 offers *shown* per month. Past that, offers stop appearing until the 1st of
the next month — this doesn't affect the merchant's orders, buyers just see one
fewer page. Check `/app/stats`.

## 4. The order wasn't eligible for the one-click page

Shopify doesn't show it for Apple Pay, Google Pay, PayPal, wallets, buy-now-pay-
later, gift cards, POS, local delivery, multi-currency orders, or orders under
$0.50. If the merchant's test order used one of these, that's the platform, not a
bug. Check the eligibility panel on `/app/stats`.

## 5. A "Who sees it" rule excludes the buyer

On the thank-you tab only. If a block is set to show only to, say, buyers who
accepted a specific offer, a buyer who saw no offer or a different one won't see
it. Check the block's "Who sees it" setting.

## 6. A funnel with no condition is catching everyone above the one that should

Funnels are evaluated top to bottom; the first matching one wins. If a
no-condition funnel sits above the one being tested, it silently wins every time.
Check the funnel order on `/app`.

## 7. The rule lives on a different funnel than the one actually taken

A thank-you or order-status rule only applies to the funnel it was configured on.
Confirm the test order actually went through the funnel that has the rule.

## 8. The countdown expired

If a block has "Urgency" enabled and its countdown reached zero, the block
disappears — that's by design, not a bug.

## 9. Checkout blocks or delivery protection, specifically

If it's the checkout tab or delivery protection that's the problem, stop and check
the two gating questions — Shopify Plus, and the `Scale Plus` plan — before
anything else. This is by far the most common cause on that surface specifically,
and it produces no error the merchant would ever see.
