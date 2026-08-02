# Technical SEO Notes for Online Stores

Technical SEO on a store is mostly about one question: can a search engine find, crawl, render and choose the right URL for every product and category you want to sell? Content and links decide how well a page ranks. Technical work decides whether the page is eligible at all. This file is the mental model I use before touching anything.

## Start by counting

Before any audit, get three numbers and compare them:

1. How many products and categories you actually want indexed. Export from the store admin.
2. How many URLs are in your sitemaps.
3. How many URLs the search engine reports as indexed.

If you sell 480 products, submit 6,000 URLs and have 22,000 indexed, you do not have a content problem. You have a URL generation problem, and everything else you do will be diluted by it. Store platforms are very good at producing URLs nobody asked for.

## Where extra URLs come from

On WooCommerce and most other platforms the usual sources are filters and facets (colour, size, price, brand, in stock), sort orders, pagination, internal search results, session or tracking parameters appended by plugins and ad platforms, tag archives created automatically, and attribute archive pages that nobody links to but the theme still generates.

Each of these can multiply. Four filters with five values each can generate hundreds of combinations of the same twelve products. The crawler spends its time there instead of on your new products.

## Deciding what should be indexable

My rule is simple: a URL earns indexation if someone could plausibly search for exactly what it shows, and if it offers something the parent page does not.

"Blue running shoes" often passes that test. "Blue running shoes, sorted by price, page 3" never does. So:

- Category and subcategory pages: indexable, with unique introductory copy that helps a buyer choose.
- Filter combinations with real demand: indexable only if you deliberately build them as landing pages with their own copy and internal links.
- All other filter, sort and search URLs: kept out of the crawl, and not linked in a way that invites crawling.
- Pagination: crawlable so products can be discovered, but not something you promote.
- Internal search results: never indexable.

Decide the policy first, write it down, then implement. Most messy stores are messy because different people made different decisions over three years.

## Canonical tags do less than people think

A canonical tag is a strong hint, not an instruction. If the canonical points at a page that is substantially different from the current one, search engines can and do ignore it. Canonicals are for genuine duplicates: the same product reachable through two category paths, a printable version, an ordering parameter. They are not a cleanup tool for a bad URL structure, and they do not stop crawling. Fix the links and the parameters, then use canonicals to tidy the remainder.

## Robots.txt, noindex, and the mistake in between

These two are constantly confused, so it is worth being blunt about the difference. Blocking in robots.txt prevents crawling but not indexing: a blocked URL can still appear in results if other pages link to it, because the crawler is not allowed to read the page and see your noindex. A noindex tag prevents indexing but requires crawling: the crawler has to fetch the page to see the tag.

So never block a URL in robots.txt and rely on a noindex on that same URL. Pick one. For low value parameter URLs I prefer keeping them out of the crawl. For pages that must stay reachable for users but should not rank, such as internal search or thank-you pages, I use noindex and leave them crawlable.

## Redirects

Stores accumulate redirects faster than any other type of site: discontinued products, renamed categories, seasonal collections, platform migrations. Three rules keep it sane. Redirect to the closest equivalent page rather than the home page, because a home page redirect tells both the visitor and the search engine that you have nothing similar. Keep chains to one hop by updating old rules when you add new ones. Keep a record of every redirect with the date and the reason, because in two years nobody remembers.

When a product is genuinely gone with no replacement, a 404 is honest and fine. A product that will return should stay published with clear availability information rather than vanishing and reappearing. Those two sentences are the summary; the full decision for a product that stops selling, including seasonal ranges and what to do with its reviews and inbound links, is in [product-lifecycle-seo.md](product-lifecycle-seo.md).

## Sitemaps as a diagnostic

Treat sitemaps as a statement of intent: these are the URLs I believe deserve indexing. That makes them useful for diagnosis. Split them by type, so products, categories and content are separate and indexation reports tell you which type is struggling. Exclude anything noindexed, redirected or returning an error, because a sitemap full of errors trains everyone to ignore sitemap reports.

## Rendering

If your price, description or reviews load through JavaScript after the initial HTML, assume they may not be seen consistently. Test by fetching the rendered page and checking the important content is present. This matters most with headless setups, review apps and dynamic pricing widgets. The safest position is that anything you want indexed should exist in the server response.

## Duplicates of the whole store

One of the most common serious problems is an entire duplicate store: a staging subdomain, a development copy, or an old domain that was never redirected. Search for a distinctive phrase from your product copy in quotation marks and see what comes back. Protect staging environments with authentication; robots.txt is not protection.

## What I check in an audit, in order

1. Crawlability: robots.txt, server responses, blocked resources.
2. URL inventory: how many exist against how many should exist.
3. Indexation: what is indexed that should not be, and what is missing that should be there.
4. Duplication: parameters, staging copies, extra domains, products reachable at several paths.
5. Redirects: chains, loops, home page dumps.
6. Rendering: is the commercial content in the HTML.
7. Speed and stability, which has its own guide in this repository.
8. Structured data, which also has its own file.

Work top to bottom. There is no point polishing a title tag on a page that cannot be crawled.

## A note on tools

Every item above can be checked with a crawler, the search engine's own coverage report, and your server logs. Tools disagree with each other constantly. When they do, trust the server response and the search engine's own report over any third-party score.

Verify current behaviour against official documentation before acting on anything here. Search engines change how they handle these signals more often than the advice on the internet gets updated.
