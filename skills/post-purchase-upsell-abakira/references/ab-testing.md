# A/B testing a block

Requires the `Scale` plan or above. Available on any block (checkout, thank-you,
order-status) — not on the one-click tab, which has no A/B mechanism.

## Where

On the block's summary card in the funnel editor: **"Test this offer"** to start
one, **"See the test"** once it's running. Up to **4 versions** (A through D), each
its own product, discount, and wording. Buyers are split evenly across versions,
and the same buyer always sees the same one.

## Reading the result

A badge on the card shows the state: a trophy once a version is a confirmed winner,
"Too early" while there isn't enough data yet, or "Tie" if the versions are
statistically indistinguishable. Checkout tests are measured on actual **sales**,
not views — the app counts what each version sold and the revenue it brought in
over the last 60 days, not impressions (a view-counting network call on every
checkout render was ruled out on purpose).

## Without the `abTesting` right

Dropping below `Scale` doesn't delete a running test's configuration — version A
keeps serving, everything else is paused, not lost. Upgrading again resumes it as
it was.

## When to actually test

Testing needs volume. A store doing a handful of orders a month on the block being
tested will likely never reach a confident verdict — "Too early" forever isn't a
bug, it's math. Before proposing a test:

- Confirm the plan supports it (`Scale` or `Scale Plus`).
- Roughly estimate whether the funnel gets enough monthly traffic through that
  specific block to reach a result in a reasonable time.
- Test one variable at a time — offer, then discount depth, then wording. Changing
  all three across versions at once makes the result impossible to act on.
- Don't suggest a test as a first step on a brand-new funnel with no baseline yet.
