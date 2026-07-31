# Measurement Setup

Most SEO disappointment comes from measuring badly rather than working badly. If you cannot tell what changed, when, and what happened next, every conclusion is a guess. This file describes the minimum measurement setup I use before starting work on a store.

None of it requires paid tools.

## Before anything else

Own your own accounts. Analytics and Search Console should be created under an email address that belongs to the business, with the agency or freelancer added as a user. Losing historical data because a contractor moved on is a genuinely common and entirely avoidable disaster.

Verify the property at the domain level so that subdomains and protocol variants are covered, and check that only the canonical domain is being reported.

## The four numbers to record every month

Keep these in one simple sheet, one row per month.

1. **Clicks and impressions** from search for the whole site, over a fixed 28 day window.
2. **Indexed URL count**, and the number you intended to have.
3. **Speed measurements** for three fixed URLs: home, one category, one product.
4. **Revenue or orders from organic search**, if your analytics can attribute it honestly.

Four numbers, once a month, kept for two years, will tell you more than any dashboard.

## Fix your test set

Choose three URLs and never change them:

- The home page.
- A category page with a realistic number of products and filters enabled.
- A product page, ideally a variable product, because it is the heaviest template.

Measure the same three every time, on the same tool, with the same settings, on a mobile profile. Comparing a desktop score in March with a mobile score in April tells you nothing.

## The change log

This is the part everyone skips and the part that pays off most. One line per change, in a plain file or sheet:

date | what changed | which pages | why | expected effect | actual effect after 4 weeks

Include everything, not just SEO work: theme updates, plugin changes, price rises, a supplier switch, a delivery delay, a campaign. Traffic changes have causes that are frequently nothing to do with search.

## How to run a test properly

1. Write down the hypothesis in one sentence. "Rewriting titles on the twenty products with high impressions and low clicks will raise click-through."
2. Record the before figures for exactly those pages.
3. Make the change once, on one day.
4. Change nothing else on those pages for four weeks.
5. Compare, and write the result down whether or not it worked.

Four weeks is a minimum for most changes, and longer for anything involving indexing. Checking daily and reacting to noise is how people undo good work before it has had a chance.

## Reading the results honestly

**Impressions up, clicks flat.** Your listing is appearing but not being chosen. Title and description work.

**Clicks up, sales flat.** The page is attracting the wrong people, or promising something the product does not deliver.

**Position up, clicks down.** Often seasonal, or the result of a competitor's listing looking better. Compare against the same period last year before concluding anything.

**Everything flat.** The most common outcome for a single change on a small store. It is information, not failure. Note it and move on.

**A sudden drop across the whole site.** Check for technical causes first: a noindex left after a deploy, a robots.txt change, an expired certificate, a server error, a migration. Assume a mistake before assuming an algorithm.

## Segment before you panic

Whole-site numbers hide everything. Split by page type at minimum: home, categories, products, content. A store can have flat overall traffic while product pages collapse and one blog post carries the difference. That is a serious problem invisible at the total level.

## What not to measure

Do not track a single keyword position daily and treat it as the score. Positions vary by location, device, personalisation and time, and chasing one term distorts priorities.

Do not use a third-party site score as a target. Those numbers are useful as prompts to look at something, and meaningless as goals.

Do not report a metric to yourself or a client that you cannot act on. If a number never changes a decision, stop collecting it.
