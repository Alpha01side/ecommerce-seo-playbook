# Roadmap

What is planned for this repository, in order, and why. Dates are deliberately absent: files are added when the material has been used on a real store, not to keep to a schedule.

Last reviewed: 2 August 2026.

## Where the library stands today

Nine guides in docs/, three checklists, three templates, two worked examples and two reference files. Coverage is strongest on product pages, technical indexation, filter URLs, catalogue structure, the product lifecycle and print-on-demand duplication. The gap named at the last review, how many category pages should exist and how deep they should nest, is closed by the architecture guide below. Two things are still missing: the procedural half of the filter work, and a method for deciding which page answers which query now that the structure is settled.

## Delivered since the last review

- [docs/category-and-catalogue-architecture.md](docs/category-and-catalogue-architecture.md) — the four questions a category has to pass before it earns a URL, sizing and depth by catalogue size, the split between categories, tags and attributes on WooCommerce, naming and slugs, empty and thin categories, pagination as part of the structure rather than part of the filter clean-up, and the order of operations for restructuring a catalogue that is already wrong. Verified against Google Search Central, WooCommerce, WordPress.org and schema.org documentation, all listed in the file. Planned here as "category and collection architecture" and renamed, because the file turned out to be about the whole catalogue rather than collections alone.
- [docs/product-lifecycle-seo.md](docs/product-lifecycle-seo.md) — out of stock, discontinued and seasonal products, as a decision table with the reasoning for each row, plus availability values, what happens to reviews and inbound links, the WooCommerce and WordPress behaviour that trips people up, a decision log and a quarterly pass. It replaces a two-sentence summary in [docs/technical-seo-notes.md](docs/technical-seo-notes.md), which now links to it.

## Next checklist: filter and parameter audit

Why. The framework added on 1 August explains how to decide. It does not turn that into a repeatable job, and it should not, because a framework that becomes a procedure stops being readable.

Planned scope: collecting the URL inventory from the four sources; running the multiplication to get the real number; filling in the policy table; implementing in the order that avoids trapping URLs in the index; and the verification steps at week one, week six and day ninety. Roughly ninety minutes on a store of a few hundred products.

## Next guide: mapping queries to pages

Why. The architecture guide decides which pages exist. It does not decide which query each page is meant to answer, and the failure it leaves behind is two of your own pages competing for the same term: a category and its best-selling product, or a category and the guide written about it. That is now the most likely way a well-structured catalogue still underperforms.

Planned scope: building the map from Search Console queries, internal site search and the category tree; the test for deciding which page should own a query; what to do when the wrong page owns it, which is usually an internal linking and copy problem rather than a redirect; and a quarterly re-check. It depends on the architecture guide, which is why it was not written first.

## Queued, lower priority

- A troubleshooting guide for a product page that is not indexed, written as a diagnostic sequence rather than a list of possible causes.
- A worked example of a category page rewrite, to sit alongside the existing product page example. Moved up: with the template and the architecture guide both in place, the example is the missing third piece.

## Deliberately not planned

- Link building tactics.
- Plugin and theme recommendations or comparisons.
- Anything that requires writing code in order to use it.
- Rewrites of existing files for the sake of activity. Files change when a platform or a search engine changes behaviour, or when something in them turns out to be wrong.

## How this roadmap is used

It is reviewed whenever a file is added, and reordered when a real store problem makes something more urgent than the plan. An item that has sat here for months without becoming useful is removed rather than carried indefinitely.
