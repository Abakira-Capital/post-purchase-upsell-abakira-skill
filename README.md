# Post Purchase Upsell Abakira, merchant assistant

This plugin is for Shopify merchants who use [Post Purchase Upsell Abakira](https://apps.shopify.com/post-purchase-upsell-abakira), an app that shows a one-click offer right after checkout and adds the accepted product to the order the buyer already paid for. It also covers the app's offers on the thank-you page, the order status page and, for Shopify Plus stores, inside the checkout.

It's published by Abakira, the team that builds the app. It contains one skill and nothing else: no MCP server, no scripts, no hooks.

## What you can ask it

- "Where do I click to create a bundle on the thank-you page?" You get the path through the app's admin, screen by screen, ending at the Save button (top right of the funnel editor, and there's only one).
- "I don't know what to put in Post Purchase Upsell." It asks what you sell, your average order value, your plan and whether the store is on Shopify Plus. Then it asks for a products export and a 90-day orders export from your Shopify admin, sorts your catalogue (best sellers, cheap add-ons, products bought together, consumables), and proposes offers you can set up in a few clicks.
- "Nothing is showing up after checkout." It goes through the causes in the order we actually see them in support. The first one is almost always the same: the app was never selected in Shopify's post-purchase page editor.
- Questions about plans, A/B tests, quantity tiers, countdowns, the "Who sees it" rules, or why some orders never get the one-click page (Apple Pay, PayPal and a few other payment methods are excluded by Shopify, not by the app).

It answers in your language. The admin itself is available in English, French, Spanish, German, Portuguese and Dutch, and the skill knows the labels in all six.

## What it won't do

It can't see your store, your products, your orders or your plan. When it needs one of those facts it asks you, and it never guesses whether you're on Shopify Plus. It never changes a setting either: every answer ends with steps for you to follow in the app.

It never quotes a price. Prices change, and a number written into a skill goes stale without anyone noticing. It sends you to Home, then the plan gauge, then "View or change plan", where the current prices live.

If you share an orders export, remove the columns with buyer names, emails and addresses first. The skill asks for that and won't repeat buyer details back to you.

## Network access

The skill makes at most one request per conversation, and only if your assistant can browse the web. It fetches this public text file:

```
https://post-purchase-upsell.abakira.com/skill/version.txt
```

The file holds the date of the latest version of the skill. If that date is newer than the copy you have, the assistant tells you once and gives you the link to update. It's a plain GET with no parameters: nothing from your conversation, your store or your files is sent. If browsing is off or the request fails, the skill carries on without mentioning it.

Like any website, the server behind post-purchase-upsell.abakira.com (hosted on Vercel) can see the IP address and user agent of whoever makes that request. Our [privacy policy](https://post-purchase-upsell.abakira.com/privacy) covers it.

Apart from that request, the plugin doesn't send or store anything.

## Install

- **Claude (claude.ai, Cowork, Claude Code):** add it from the plugin directory once it's listed there. In Claude Code you can also install it straight from this repository:

  ```
  /plugin marketplace add Abakira-Capital/post-purchase-upsell-abakira-skill
  /plugin install post-purchase-upsell-abakira@abakira
  ```

- **ChatGPT, or any assistant that accepts skill uploads:** download the zip from [post-purchase-upsell.abakira.com/skill](https://post-purchase-upsell.abakira.com/skill). The same page has a plain-text version you can paste into a conversation if your assistant doesn't take uploads.

## Contents

```
.claude-plugin/plugin.json        plugin manifest
.claude-plugin/marketplace.json   lets Claude Code install from this repo
skills/post-purchase-upsell-abakira/
  SKILL.md                        rules and routing
  references/                     admin map, block editor, one-click tab,
                                  plans, funnel planning, A/B tests,
                                  troubleshooting, labels in six languages
assets/icon.png                   app icon
```

Everything is Markdown you can read before installing.

## Support

Write to support@abakira.com, or use the chat at the bottom right of any screen in the app's admin. More about the skill: [post-purchase-upsell.abakira.com/skill](https://post-purchase-upsell.abakira.com/skill).

## License

Free to use with Post Purchase Upsell Abakira. Not open source: see [LICENSE](LICENSE).
