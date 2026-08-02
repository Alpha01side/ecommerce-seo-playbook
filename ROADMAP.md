# Roadmap

What is planned for this repository, in order, and why. Dates are deliberately absent: files are added when the material has been used on a real store, not to keep to a schedule.

Last reviewed: 2 August 2026.

## Where the library stands today

Ten guides in docs/, three checklists, three templates, two worked examples and two reference files. Coverage is strongest on product pages, technical indexation, filter URLs, catalogue structure, the product lifecycle, print-on-demand duplication and, since this review, what each page is for. Both gaps named at the last review are now closed: which categories should exist, and which query each page is meant to answer. What the library is short of now is demonstration rather than further explanation.

## Delivered since the last review

- [docs/search-intent-and-query-mapping.md](docs/search-intent-and-query-mapping.md) — what each page is for. Reading what a searcher is trying to accomplish, the four gates a query has to pass before anything is built for it, which of six page types should own it, how to decide ownership when two could, how to diagnose and fix two of your own pages competing, and when the honest answer is that no page should exist. It supplies the demand test that the architecture guide and the filter framework both invoke without explaining. Verified against Google Search Central, WooCommerce and schema.org documentation, all linked in the file. Planned here as "mapping queries to pages" and broadened, because the mapping is worthless without the intent reading that comes before it.
- [docs/category-and-catalogue-architecture.md](docs/category-and-catalogue-architecture.md) — the four questions a category has to pass before it earns a URL, sizing and depth by catalogue size, the split between categories, tags and attributes on WooCommerce, naming and slugs, empty and thin categories, pagination as part of the structure rather than part of the filter clean-up, and the order of operations for restructuring a catalogue that is already wrong. Verified against Google Search Central, WooCommerce, WordPress.org and schema.org documentation, all listed in the file. Planned here as "category and collection architecture" and renamed, because the file turned out to be about the whole catalogue rather than collections alone.
- [docs/product-lifecycle-seo.md](docs/product-lifecycle-seo.md) — out of stock, discontinued and seasonal products, as a decision table with the reasoning for each row, plus availability values, what happens to reviews and inbound links, the WooCommerce and WordPress behaviour that trips people up, a decision log and a quarterly pass. It replaces a two-sentence summary in [docs/technical-seo-notes.md](docs/technical-seo-notes.md), which now links to it.

## Dropped from the plan: filter and parameter audit checklist

Planned at the last two reviews and now removed. Checking it against [docs/faceted-navigation-decision-framework.md](docs/faceted-navigation-decision-framework.md) showed that the whole of the intended scope already exists there: the inventory from four sources and the arithmetic in Step 1, the default decisions in Step 3, the implementation order in Step 4, the worked policy table in Step 7, and the week one, week six and day ninety verification in Step 8. Writing it would have restaged an existing file as tick boxes and added a file without adding anything to know. If the framework turns out to be hard to follow on a real store, the answer is to fix the framework, not to duplicate it.

## Next: a worked example of a category page rewrite

Why. The template says how to write a category page, the architecture guide says which categories should exist, and the intent guide says which query one should own. Nothing in the repository shows that work actually being done. The product copy example is the most useful file here for people who are not sure where to start, which suggests the demonstration is worth more now than another explanation.

Planned scope: a before and after on one category page, the query it was written to own and why that one, the internal links that were retargeted away from a competing product page, what was deliberately left alone, and what happened afterwards measured the way the measurement file describes. Composite, and labelled as such.

## Then: a diagnostic for a product page that is not indexed

Why. It is the most common single question a store owner asks, and the existing material answers it in pieces spread across the technical notes, the filter framework and the product page checklist. Written as an ordered sequence of checks that ends in a decision, not as a list of possible causes.

## Queued, lower priority

- A query map template for templates/, if the map described in the intent guide turns out to need a fixed shape rather than a spreadsheet with five columns. Not written yet because a template nobody has used twice is a guess.
- A note on internal site search as a demand source, if the intent guide proves too brief on it in practice.

## Deliberately not planned

- Link building tactics.
- Plugin and theme recommendations or comparisons.
- Anything that requires writing code in order to use it.
- Rewrites of existing files for the sake of activity. Files change when a platform or a search engine changes behaviour, or when something in them turns out to be wrong.

## How this roadmap is used

It is reviewed whenever a file is added, and reordered when a real store problem makes something more urgent than the plan. An item that has sat here for months without becoming useful is removed rather than carried indefinitely.
