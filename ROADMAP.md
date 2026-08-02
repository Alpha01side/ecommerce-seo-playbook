# Roadmap

What is planned for this repository, in order, and why. Dates are deliberately absent: files are added when the material has been used on a real store, not to keep to a schedule.

Last reviewed: 2 August 2026.

## Where the library stands today

Eight guides in docs/, three checklists, three templates, two worked examples and two reference files. Coverage is strongest on product pages, technical indexation, filter URLs, the product lifecycle and print-on-demand duplication. The weakest area left is catalogue structure: how many category pages should exist, how deep they should nest, and how they should be named. The next two items address that, in that order.

## Delivered since the last review

- [docs/product-lifecycle-seo.md](docs/product-lifecycle-seo.md) — out of stock, discontinued and seasonal products, as a decision table with the reasoning for each row, plus availability values, what happens to reviews and inbound links, the WooCommerce and WordPress behaviour that trips people up, a decision log and a quarterly pass. It replaces a two-sentence summary in [docs/technical-seo-notes.md](docs/technical-seo-notes.md), which now links to it.

## Next checklist: filter and parameter audit

Why. The framework added on 1 August explains how to decide. It does not turn that into a repeatable job, and it should not, because a framework that becomes a procedure stops being readable.

Planned scope: collecting the URL inventory from the four sources; running the multiplication to get the real number; filling in the policy table; implementing in the order that avoids trapping URLs in the index; and the verification steps at week one, week six and day ninety. Roughly ninety minutes on a store of a few hundred products.

## Next guide: category and collection architecture

Why. There is a template for writing a category page and no guidance on how many category pages should exist, how deep they should nest, when a collection earns a page of its own, or how to name them so they match demand. On most stores this has been decided by accident, one supplier feed at a time.

It belongs before the category template rather than after it, and the faceted navigation framework depends on it: you cannot sensibly decide which filters deserve their own pages without first knowing which categories exist and why.

## Queued, lower priority

- A troubleshooting guide for a product page that is not indexed, written as a diagnostic sequence rather than a list of possible causes.
- A method for mapping queries to pages across a catalogue, including how to stop two pages competing for the same query.
- A worked example of a category page rewrite, to sit alongside the existing product page example.

## Deliberately not planned

- Link building tactics.
- Plugin and theme recommendations or comparisons.
- Anything that requires writing code in order to use it.
- Rewrites of existing files for the sake of activity. Files change when a platform or a search engine changes behaviour, or when something in them turns out to be wrong.

## How this roadmap is used

It is reviewed whenever a file is added, and reordered when a real store problem makes something more urgent than the plan. An item that has sat here for months without becoming useful is removed rather than carried indefinitely.
