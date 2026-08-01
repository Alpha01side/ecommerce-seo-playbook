# Faceted Navigation and Filter URLs: A Decision Framework

[technical-seo-notes.md](technical-seo-notes.md) states the rule I use for indexation: a URL earns indexation if someone could plausibly search for exactly what it shows, and if it offers something the parent page does not. It also says to decide the policy and write it down before implementing anything. This file is how I write it down.

Filters are the largest single source of accidental URLs on a store, and the decision about them is usually made by whoever installed the filter plugin rather than by anyone who thought about it. The framework below produces one short table per store: every facet, the decision, the mechanism, and the date it was last reviewed. Once that table exists, the implementation is mechanical.

## Step 1: Count what the store can generate

You cannot write a policy about URLs you have not listed. Collect the inventory from four places, because none of them is complete on its own.

1. A crawl of the store with parameter URLs allowed and JavaScript rendering on. This shows what is linked.
2. The Page indexing report in Search Console, particularly anything in "Crawled - currently not indexed" and "Duplicate without user-selected canonical". This shows what has been found.
3. A sample of server logs filtered to search engine user agents. This shows what is actually being requested, which is rarely what you expect.
4. The filter, sorting and layered navigation settings in the admin, plus the theme options. This shows what can be produced even if nothing links to it yet.

Record each one in a table: the parameter, an example URL, what generates it (WooCommerce core, the theme, a plugin, an ad platform), whether anything on the site links to it, and its current index status.

### The arithmetic that makes the case

Facets multiply rather than add, which is why an hour spent here is worth it. Take one category with four facets: eight colours, six sizes, five price bands, four sort orders. If each facet is either unset or set to a single value, that one category can produce 9 x 7 x 6 x 5 = 1,890 distinct URLs. Across twelve categories that is 22,680 URLs, of which 22,668 are rearrangements of products already shown on the twelve real category pages.

Allow multi-select on colour and it stops being a rounding error. Any subset of eight colours can be chosen, which is 256 possibilities including none, so one category can produce 256 x 7 x 6 x 5 = 53,760 URLs. Twelve categories reach 645,120. The catalogue underneath might be 400 products.

Run this calculation on your own store before deciding anything. It is the number that decides how aggressive the policy has to be.

## Step 2: Three questions per facet

A facet has to pass all three of these to earn an indexable page of its own.

**Demand.** Does anyone search for this attribute as a phrase, rather than use it as a control? Evidence, not intuition: the Queries report in Search Console, your internal site search log, and what autocomplete offers after the category term. "Oversized band t-shirt" is a phrase people type. "Products between 20 and 30 pounds" is not.

**Difference.** Does the filtered view show a materially different set of products, and could you write copy for it that is not a rewording of the parent category? If the honest answer is that it shows the same twelve products in a different order, there is nothing there to index.

**Durability.** Will this set of products still exist in six months? A colour that three suppliers carry is durable. A filter that currently matches four items, two of them seasonal, is not: you would be publishing a page that empties itself.

The outcomes:

- All three yes: build it as a real page with its own URL, copy and internal links, not as a filter URL. See Step 5.
- Demand yes, difference or durability no: keep the facet out of the crawl and answer the demand on the parent page instead, in the introduction or the choosing guidance.
- No demand: keep it out of the crawl. This is the outcome for most facets on most stores, and it is the normal result rather than a failure.

## Step 3: The default decisions

This is where I start on a WooCommerce store, before adjusting for the catalogue. URL shapes vary by version, theme and filter plugin, so confirm what your own install emits rather than trusting the middle column.

| Facet or URL type | Typical shape | Default | Reasoning |
| --- | --- | --- | --- |
| Category and subcategory | `/product-category/tees/graphic/` | Indexable | Real demand, own copy, stable set |
| Colour or style filter | `?filter_colour=black` | Out of the crawl, with named exceptions | Sometimes has genuine demand, and then it deserves a built page rather than a parameter |
| Size filter | `?filter_size=xl` | Out of the crawl | Sizing is a control, not usually a query, apart from extended sizes |
| Price range | `?min_price=20&max_price=30` | Out of the crawl, always | Nobody searches in price bands, and the sets change with every promotion |
| Sort order | `?orderby=price` | Out of the crawl, always | Identical products in a different sequence |
| In stock toggle | `?stock_status=instock` | Out of the crawl | The content changes daily by definition |
| Layout switch | `?product_view=list` | Out of the crawl | Presentation only |
| Pagination | `/page/3/` or `?product-page=3` | Crawlable, not promoted | It is the discovery path for products, see Step 6 |
| Internal search | `?s=tour+tee&post_type=product` | Noindex, left crawlable | Has to work for users, must never rank |
| Product tags | `/product-tag/tour/` | Consolidate into categories, or noindex | Usually duplicate a category with nothing written behind them |
| Attribute archives | Attribute base plus term | Disable unless deliberately built | WooCommerce can generate these when archives are enabled for an attribute, and themes rarely link them |
| Tracking parameters | `?utm_source=`, `?gclid=`, `?fbclid=` | Canonical to the clean URL, never linked internally | Duplicates created by your own campaigns |

Two rows cause most of the disagreement. Colour is the one facet that genuinely earns exceptions, so name them in the policy instead of leaving it to judgement six months later. Product tags are the rows people defend hardest and use least, so look at their traffic before defending them.

## Step 4: Choose the mechanism, strongest first

These are not interchangeable. They are ordered by how reliably they work, and the first is far stronger than the rest.

1. **Do not generate the link.** A filter that never produces a crawlable URL cannot cause a crawl problem. Most filter plugins can be configured to update the listing without writing a linkable URL. This is the only mechanism that removes the problem instead of managing it.
2. **Disallow the pattern in robots.txt.** Stops crawling. It does not remove URLs that are already indexed, and a blocked URL can still appear in results, because the crawler cannot fetch the page to read anything else. Use it to stop waste, not to clean up.
3. **Noindex.** Removes a URL from the index, but only while the crawler can still fetch it and read the tag. Right for pages that must stay usable, such as internal search.
4. **Canonical tags.** A hint, and ignored when the two pages differ. Correct for tracking parameters and sort variants of the same set. Not a fix for a filter explosion, for the reasons in the technical notes.
5. **Nofollow on facet links.** A hint. Do not build a policy on it.

### The ordering trap

If thousands of facet URLs are already indexed, the sequence matters, and it is easy to get backwards. Blocking in robots.txt first freezes those URLs in the index, because the crawler can no longer fetch them to discover the noindex you add afterwards.

The order that works: add noindex and leave the URLs crawlable; wait until the index reports show them gone, which takes weeks on a large set; then disallow the pattern in robots.txt to stop the crawling; then remove the internal links that generate them, or stop generating them at all. Record the date of each stage. If indexation moves, you need to know which change to look at.

## Step 5: Filters worth promoting

A facet that passes all three questions in Step 2 should stop being a facet. Build it as a page.

- Its own URL under the category path, not a parameter.
- Its own H1, introduction and choosing guidance, using [category-page-content-template.md](../templates/category-page-content-template.md).
- Linked from the parent category in the body copy, not only from the filter widget.
- Included in the sitemap that covers categories.
- Reviewed quarterly against the query that justified it, and removed if the query has gone or the product set has emptied.

Keep the count small: one page per proven query. Twenty of these built on hope is a thin content problem with extra steps.

## Step 6: Pagination, which is not a facet

Pagination gets swept up in facet cleanups and should not be.

- Keep it crawlable. On many stores it is the only path a crawler has to products deeper than page one. If you noindex it, confirm every product is reachable from somewhere else and present in the sitemap.
- Use a self-referencing canonical on page three, not a canonical pointing at page one. Page three is not a duplicate of page one.
- `rel="next"` and `rel="prev"` are no longer used by Google as an indexing signal. There is no harm in leaving whatever your theme outputs, and no gain in adding it.
- Keep one URL shape. A store that produces both `/page/2/` and `?product-page=2` for the same listing has doubled its pagination.
- Avoid a "view all" page on a large category. It is slow, and it competes with the category itself.

## Step 7: The policy table, worked through

This is a composite example with the shape of catalogue this repository is mostly about: 400 products, twelve categories, thirty-eight subcategories, four facets, multi-select enabled on colour. The URL counts are arithmetic from Step 1, not measurements from one store. Do the same exercise with your own numbers.

Generated before any policy: above 600,000 crawlable URLs, against an intended inventory of roughly 450.

| Facet | Decision | Mechanism | Review |
| --- | --- | --- | --- |
| Colour | Out of the crawl, except black, white and tie-dye | Filter rewritten so it produces no URL; three colour pages built under their categories | Quarterly |
| Size | Out of the crawl | No URL generated | Annually |
| Price | Out of the crawl | No URL generated | Annually |
| Sort | Out of the crawl | No URL generated, canonical on any survivors | Annually |
| Pagination | Crawlable, one shape | Self-referencing canonical | Annually |
| Internal search | Noindex, crawlable | Noindex tag | Annually |
| Product tags | Removed | 301 to the nearest category, each one recorded | Once |
| Tracking parameters | Canonical to clean URL | Canonical, and never linked internally | Annually |

What is left crawlable: twelve categories, thirty-eight subcategories, three built colour pages, about thirty pagination URLs, and 400 products. Roughly 480 URLs against an intended 450, which is close enough to explain.

The value is not in the numbers. It is that the table is short, every row has a mechanism and a review interval, and someone who joins the store later can read the decision instead of guessing at it.

## Step 8: Confirm it worked

Do not judge this on indexed URL count alone, which falls for good and bad reasons.

- Week one: crawl the store again with parameters allowed. The facet URLs should be absent, not merely fewer. Test the robots.txt rules against a live URL rather than against the pattern you intended to write.
- Weeks two to six: watch "Crawled - currently not indexed" and "Duplicate without user-selected canonical" in the Page indexing report. On a large clean-up this takes longer than feels reasonable.
- Day thirty to ninety: compare crawl stats, pages crawled per day, and how much of that is products rather than parameters.
- The number that matters: how long a new product takes to be indexed after publishing. That is what the wasted crawling was costing. Measure it the same way each time, using [measurement-setup.md](../resources/measurement-setup.md).

Write the change and its date in your change log. Indexation moves slowly, and in three months somebody will ask what caused it.

## Mistakes to avoid, including ones I have made

- Blocking parameters in robots.txt before de-indexing them, which leaves the URLs stuck in the index with no way for the crawler to see the noindex.
- Trusting canonical tags to absorb a filter explosion. They do not, and the technical notes explain why.
- Building filter landing pages for every colour a supplier offers, then removing most of them as thin pages.
- Noindexing pagination on a large category and losing discovery of everything past page two.
- Writing a careful facet policy and forgetting the sort parameter, which quietly produces several copies of every page in it.

## Verify before implementing

Search engine handling of parameters and faceted navigation changes, and so does the tooling: the URL parameters tool that used to sit in Search Console no longer exists, so there is no dashboard shortcut for any of this. Check current official Google guidance on faceted navigation and on robots.txt before implementing, and confirm the query arguments your own WooCommerce version and filter plugin actually emit rather than the shapes listed above.

## Related files

- [technical-seo-notes.md](technical-seo-notes.md) for the indexation rule and the audit order this sits inside.
- [internal-linking-guide.md](internal-linking-guide.md) for how the surviving pages should be linked.
- [print-on-demand-catalogue-seo.md](print-on-demand-catalogue-seo.md) for the variation and duplication problems specific to print-on-demand catalogues.
- [monthly-seo-maintenance-checklist.md](../checklists/monthly-seo-maintenance-checklist.md) for the monthly check that catches a plugin update reintroducing filter URLs.
