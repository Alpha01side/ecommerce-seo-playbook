# Category and Catalogue Architecture

This repository already has a template for writing a category page. Until now it has had nothing about which category pages should exist, which is the wrong way round. On most stores the shape of the catalogue was never designed: it arrived one supplier feed at a time, an import created forty terms nobody reviewed, and two years later there are ninety categories, eleven of them holding a single product and three of them meaning the same thing.

This file is the decision that comes before the copy. How many categories a store needs, how deep they should nest, when something deserves a category rather than a tag or an attribute, what to call it, and how to repair a structure that is already wrong.

Work through it before [faceted-navigation-decision-framework.md](faceted-navigation-decision-framework.md). You cannot sensibly decide which filters deserve indexable pages until you know which categories exist and why.

## What a category is for

Three jobs, and they pull against each other.

**It captures demand no product page can.** "Waterproof walking boots" is a category-shaped query. A single boot cannot answer it honestly.

**It helps someone narrow down.** That argument, and how to write the page, is in [category-page-content-template.md](../templates/category-page-content-template.md) and is not repeated here.

**It distributes authority.** Google's ecommerce documentation states that it works out the relative importance of pages from the links between them rather than from the shape of the URLs, and that it expects to reach products by following links from menus to categories, categories to subcategories, and subcategories to products. Two things follow from that. Nesting a URL more deeply does not by itself demote the page. And a category nothing links to is weak however tidy its URL looks.

## The test: should this category exist?

Four questions, and a category needs all four. The first three are deliberately the same three the faceted navigation framework asks of a facet, because the underlying question is identical: does this set of products deserve a URL of its own?

**Demand.** Do people search for this grouping as a phrase? Evidence rather than intuition: the Queries report in Search Console, your internal site search log, and what autocomplete offers after the parent term.

**Difference.** Does it hold a materially different set of products from its parent and from its siblings?

**Durability.** Will it still hold a sensible number of products in six months, or is it three seasonal lines that empty in March?

**Writability.** Can somebody write an introduction and choosing guidance for it that is not a reworded version of the parent? If nobody can, the page is thin on the day it is published and stays thin.

| Answer | What to do instead |
| --- | --- |
| All four yes | Build it as a category |
| Demand yes, difference no | Answer the demand in the parent category's copy |
| Demand yes, durability no | Leave it as a filter, kept out of the crawl |
| Demand no | It is an internal organising idea. A tag, or nothing |

A grouping with fewer than about eight products rarely survives the difference test. The category template puts it more bluntly: a category with two products in it is a filter.

## How many, and how deep

WooCommerce categories are hierarchical. Each subcategory has exactly one parent, a parent can have many children, and they can be nested several layers deep. WooCommerce's own documentation recommends keeping the structure as simple as possible, which is worth taking literally, because the platform will happily let you build a five-level tree nobody can navigate.

Two rules I hold to. Every product should be reachable from the home page in three clicks or fewer, as in [internal-linking-guide.md](internal-linking-guide.md). And a level only exists because the level above it became too broad to choose from. Depth is a symptom of catalogue size, never a goal.

Starting points by catalogue size. These come from stores I have worked on rather than from any documentation, so argue with them using your own query data.

| Products | Top-level categories | Subcategories | Useful depth |
| --- | --- | --- | --- |
| Under 100 | 3 to 6 | Usually none | 2 |
| 100 to 500 | 5 to 9 | 10 to 30 | 2 to 3 |
| 500 to 2,000 | 6 to 12 | 30 to 80 | 3 |
| Over 2,000 | 8 to 15 | As demand justifies | 3, with a fourth level only where a query proves it |

If your store has more categories than the table suggests and fewer products, that is not a rich taxonomy. Those are filters that were entered as categories.

## Category, subcategory, tag or attribute

WooCommerce gives you three product taxonomies and most stores use them interchangeably, which is where the mess starts. Categories are hierarchical and are the primary grouping. Tags are flat, with no subtags, and are meant for characteristics that cut across categories. Attributes define variations and drive filtering, can be global or defined on a single product, and carry an "Enable archives" setting that produces an archive page for every term.

| What you are grouping by | Where it belongs | Notes |
| --- | --- | --- |
| A kind of product people search for | Category or subcategory | The only one that reliably earns an indexable page |
| A characteristic crossing several categories: material, "eco", "gifts under 20" | Tag, kept out of the index | Useful for internal navigation, rarely worth a page. The faceted framework's default for tag archives is consolidate or noindex |
| An option that defines a variation: size, colour | Attribute | Required for variable products |
| A control the customer uses to narrow a list | Attribute with archives disabled | Archives generate a term page your theme may never link, which is how stores acquire indexable URLs nobody knew existed |
| A brand | Category if people search brand plus product type, otherwise an attribute | Check the query data before deciding, not the supplier's opinion |
| A season or campaign | Category with a permanent URL, refreshed each year | Reasoning is in the category page template |

One WooCommerce detail to know before planning anything: every product must belong to a category, and an unassigned product is placed in the default category, which starts life as "Uncategorized". The default cannot be deleted while it is the default, but it can be renamed, and a different category can be made the default instead. Find out what yours is called and whether it is indexable. It is one of the most common accidental URLs on a WooCommerce store.

## Naming

Name the category the way a customer would say it, not the way the admin is organised. The heading advice in the category template applies to the taxonomy name too, and the taxonomy name is the harder one to change later.

Four rules prevent most of the damage.

- One concept per category. "Accessories and other" is two concepts, or none.
- Siblings must be mutually exclusive. The test: take ten products and ask whether any of them could sit in two sibling categories with equal confidence. If so, the names are wrong, not the products.
- No supplier codes and no internal jargon, ever.
- Use the words that appear in your own query data, singular or plural as people actually type them, then keep that convention across every sibling.

Slugs follow the name. Google's ecommerce URL guidance recommends descriptive words in URL paths rather than identifiers, so the slug should read like the category. Keep it short, decide it once, and remember that everything below a category inherits a change made to it.

## URL shape, and how much it matters

Less than people expect, because Google infers site structure from links rather than URLs. Most of the usual arguments are therefore aesthetic.

**Keeping or removing the product category base.** WordPress exposes optional custom bases for category and tag URLs on the permalinks screen, and WooCommerce adds its own product permalink options to that same screen. Removing the base is cosmetic and carries a real risk of collisions with page slugs. It is not a reason to migrate on its own.

**Nesting parents inside child URLs.** A preference. Pick one, apply it to every category, and stop discussing it.

**Consistency, which does matter.** Use the same URL in internal links, in the sitemap and in the canonical tag. Google's URL guidance is explicit that alternative URLs returning the same content are one of the main ways ecommerce sites create duplicates for themselves.

## One product, several paths

A product that legitimately belongs to three categories is normal. A store that generates that product at three URLs is not. Confirm your install produces one product URL, and be careful with any plugin offering to include the category path in product permalinks.

For breadcrumbs, Google's structured data documentation recommends a trail that represents the route a user typically takes rather than a copy of the URL path, permits a page to declare more than one trail, and requires at least two items in the list. So choose the primary path for the customer, not for the folder structure. The markup itself belongs in [schema-implementation-notes.md](schema-implementation-notes.md); schema.org also defines CollectionPage for listing pages, which carries the breadcrumb property, and it is not a rich result on its own.

## Empty and thin categories

Google's ecommerce URL documentation is unusually direct here. Avoid linking to, or at least indexing, pages without useful content; apply a noindex robots meta tag to a category with no items; and if the store automatically removes an empty category from browse and site search, consider returning a 404 for it.

The policy I use on WooCommerce stores:

| State | Action |
| --- | --- |
| Empty, refilling within weeks | Keep published, noindex until it has products, keep it linked from the parent |
| Empty, permanently | 301 to the nearest surviving category, recorded with the date and reason |
| One to three products, duplicates a sibling | Merge into the sibling, 301, and fold the distinction into the sibling's copy |
| One to three products, genuinely distinct | Demote to a filter or an attribute and leave the products in the parent |
| Has products, but copy repeats a sibling almost word for word | Not yet an architecture problem. Rewrite it. If it cannot be written distinctly, merge it |

Run the count monthly. It takes two minutes from a category export, and it is the check that catches a supplier feed quietly emptying a range.

## Pagination belongs to the architecture, not to the filters

Pagination decides whether products below page one are discoverable at all, so it is settled when the structure is settled rather than during a filter clean-up. Verified against Google's pagination guidance:

- Give every page in a sequence its own URL and its own self-referencing canonical. Do not canonicalise page three to page one.
- Link pages sequentially with real anchor tags, and consider linking every page in the sequence back to the first page.
- Pages in a sequence may share a title and meta description. It is one of the few places duplication is explicitly acceptable.
- rel next and rel prev are no longer used by Google, although other engines may still read them.
- Never put the page number in a fragment. Google ignores fragments.
- Load more buttons and infinite scroll are JavaScript, and crawlers do not click buttons. If that is your pattern, the products still need crawlable links, a sitemap, or a product feed.

How many products per page is as much a performance decision as an SEO one: see [woocommerce-performance-guide.md](woocommerce-performance-guide.md) and [image-optimization-guide.md](image-optimization-guide.md). A grid of 24 to 48 with correctly sized images is usually the balance point.

## Changing a structure that is already wrong

This is the second most dangerous change in this repository, after removing products, because it moves the URLs everything else depends on. Do it in this order, and change one thing per week.

1. Export the current tree: every category, its parent, its product count, its clicks and impressions over twelve months, and any inbound links.
2. Design the target tree on paper and run the four questions over every proposed category. Expect to finish with fewer categories than you started with.
3. Write the mapping before touching anything: old URL, new URL, reason. That document is both the redirect map and the record of why.
4. Create the new categories and reassign products. Delete nothing yet.
5. Update internal links, menus and category copy to point at the new URLs. Redirects are a safety net, not a substitute for fixing links.
6. Then apply the redirects, one hop each, and remove the old categories.
7. Regenerate and resubmit the category sitemap.
8. Measure at day 30 and day 90 using [measurement-setup.md](../resources/measurement-setup.md). Expect a dip before a recovery, and make no second structural change inside that window, or you will never know which change did what.

Products being removed rather than remapped are a different decision, and it is made in [product-lifecycle-seo.md](product-lifecycle-seo.md) before this work starts, not during it.

## A composite example

The same store shape used in the faceted navigation framework: roughly 400 products, print-on-demand, grown out of supplier imports. The figures are composite and illustrative, not one store's measurements.

Before: 71 product categories across four levels; 22 of them holding fewer than three products; three pairs meaning the same thing under different names; 140 tags operating as a second, parallel category system; colour and size attributes with archives enabled and nothing in the theme linking to them.

After: nine top-level categories and 29 subcategories, three levels at most; 18 merges, each with a recorded 301; four categories left published and noindexed while their ranges restock; tags cut to six genuinely cross-cutting descriptors, all kept out of the index; attribute archives disabled; the default category renamed and checked.

What to watch afterwards, in this order: whether every product is still reachable in three clicks, whether the category sitemap count matches the intended tree, whether impressions on the surviving categories recover by day 90, and how long a newly published product takes to be indexed. The last of those is the number that tells you the structure is doing its job.

## Keep the record

One short table, kept wherever the store's decisions live, with a row per category: the category, the query or reason that justifies it, its product count, the date it was last reviewed. Review it quarterly and at every catalogue expansion. A category nobody can justify in one sentence is a merge waiting to happen.

## Mistakes to avoid, including ones I have made

- Building the tree from the supplier's catalogue instead of from query data. The supplier organised it for warehousing.
- Adding a subcategory level for one large category and then applying it to all twelve for consistency, leaving eleven levels holding three products each.
- Using tags as a second category system and later discovering they are indexed and thin.
- Renaming a category and letting the slug follow it silently, which moves the URL without a redirect.
- Redirecting merged categories to the home page instead of the nearest equivalent.
- Deleting an empty seasonal category rather than leaving it published and noindexed until it refills.
- Restructuring the catalogue and cleaning up filter URLs in the same fortnight, then being unable to explain the indexation change to anybody, including yourself.

## Verify before implementing

Taxonomy behaviour, permalink options and attribute archive settings vary by WooCommerce version, theme and filter plugin, and search engine guidance changes. Confirm what your own install does before planning around it, and where this file disagrees with current documentation, the documentation is right. The sources checked while writing this file:

- [Help Google understand your ecommerce website structure](https://developers.google.com/search/docs/specialty/ecommerce/help-google-understand-your-ecommerce-site-structure)
- [Designing a URL structure for ecommerce websites](https://developers.google.com/search/docs/specialty/ecommerce/designing-a-url-structure-for-ecommerce-sites)
- [Pagination, incremental page loading, and their impact on Google Search](https://developers.google.com/search/docs/specialty/ecommerce/pagination-and-incremental-page-loading)
- [Breadcrumb (BreadcrumbList) structured data](https://developers.google.com/search/docs/appearance/structured-data/breadcrumb)
- [Managing product categories, tags and attributes](https://woocommerce.com/document/managing-product-taxonomies/)
- [Settings Permalinks screen](https://wordpress.org/documentation/article/settings-permalinks-screen/)
- [schema.org CollectionPage](https://schema.org/CollectionPage)

## Related files

- [faceted-navigation-decision-framework.md](faceted-navigation-decision-framework.md) — the decision that comes immediately after this one, and depends on it.
- [technical-seo-notes.md](technical-seo-notes.md) — the indexation rule and the audit order this sits inside.
- [internal-linking-guide.md](internal-linking-guide.md) — how the surviving categories should be linked once they exist.
- [product-lifecycle-seo.md](product-lifecycle-seo.md) — what happens to products, as opposed to categories, when they stop selling.
- [category-page-content-template.md](../templates/category-page-content-template.md) — what to write once you know the category should exist.
- [print-on-demand-catalogue-seo.md](print-on-demand-catalogue-seo.md) — the duplication problems that make catalogue structure harder at scale.
- [store-launch-seo-checklist.md](../checklists/store-launch-seo-checklist.md) — where the URL structure decision appears during a launch.
