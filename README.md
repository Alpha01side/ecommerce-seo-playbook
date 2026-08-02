# E-commerce SEO Playbook

Practical, original documentation for people who run, build or optimise online stores. Written for WooCommerce and WordPress in particular, and useful to anyone selling products online, including print-on-demand sellers.

Everything here is documentation, not software. It is written from an SEO, content and store-operations point of view rather than a developer one, and every word of it is original. Where an idea comes from official Google, WordPress or WooCommerce documentation, this repository links to the source instead of reproducing it.

## Why it exists

Store SEO advice is scattered across blog posts, support threads and half-remembered fixes, and most of it is written for a site that sells nothing. The same problems come back on every store: filter URLs multiplying, thin product pages, supplier descriptions repeated across a thousand shops, images four times larger than they need to be, and nobody able to say what changed in March.

Writing the process down once makes it repeatable, reviewable, and possible to hand to somebody else.

## Start here

If you have never audited this store before, work in this order:

1. Read [docs/technical-seo-notes.md](docs/technical-seo-notes.md) and count your URLs. If the store generates thousands of URLs you did not intend, fix that before anything else. Then use [docs/faceted-navigation-decision-framework.md](docs/faceted-navigation-decision-framework.md) to decide what happens to each of them.
2. Run [checklists/product-page-seo-checklist.md](checklists/product-page-seo-checklist.md) on your three best-selling products.
3. Set up measurement properly using [resources/measurement-setup.md](resources/measurement-setup.md), so the rest of your work can be judged.
4. Then pick whichever guide matches your biggest problem.

If you are launching or replatforming, go straight to [checklists/store-launch-seo-checklist.md](checklists/store-launch-seo-checklist.md).

Before you delete or bulk-redirect anything that has stopped selling, read [docs/product-lifecycle-seo.md](docs/product-lifecycle-seo.md). It is the decision most stores get wrong once and cannot easily undo.

## What is in here

### docs/ — the reasoning

- [technical-seo-notes.md](docs/technical-seo-notes.md) — crawling, indexation, canonicals, redirects, rendering, and the audit order I follow.
- [faceted-navigation-decision-framework.md](docs/faceted-navigation-decision-framework.md) — deciding which filter, sort and parameter URLs should be indexable, and which mechanism to use for each.
- [product-lifecycle-seo.md](docs/product-lifecycle-seo.md) — what to do with a product when it goes out of stock, is discontinued or only sells for part of the year: keep, redirect or remove.
- [woocommerce-performance-guide.md](docs/woocommerce-performance-guide.md) — what is actually slow on a WooCommerce store, and the order to fix it in.
- [internal-linking-guide.md](docs/internal-linking-guide.md) — structure, anchor text, orphan pages, and a monthly routine.
- [image-optimization-guide.md](docs/image-optimization-guide.md) — sizing, compression, alt text and loading behaviour for large catalogues.
- [schema-implementation-notes.md](docs/schema-implementation-notes.md) — product structured data without overreaching.
- [print-on-demand-catalogue-seo.md](docs/print-on-demand-catalogue-seo.md) — duplication, page structure and copy at scale for POD stores.

### checklists/ — the doing

- [product-page-seo-checklist.md](checklists/product-page-seo-checklist.md) — ten stages, from baseline measurement to post-publish review.
- [store-launch-seo-checklist.md](checklists/store-launch-seo-checklist.md) — two weeks before launch through to the first month after.
- [monthly-seo-maintenance-checklist.md](checklists/monthly-seo-maintenance-checklist.md) — a ninety minute routine that catches decay early.

### templates/ — the writing

- [product-copy-brief.md](templates/product-copy-brief.md) — fill this in before writing a product page.
- [product-page-content-template.md](templates/product-page-content-template.md) — the structure of a page that answers buying questions in order.
- [category-page-content-template.md](templates/category-page-content-template.md) — how to make a category page help someone choose.

### examples/ — worked, with reasoning

- [product-copy-worked-example.md](examples/product-copy-worked-example.md) — a full before and after rewrite, and why each change was made.
- [schema-examples.md](examples/schema-examples.md) — structured data for simple products, variable products, stock states and breadcrumbs.

### resources/ — reference

- [glossary.md](resources/glossary.md) — plain definitions, including how each term is commonly misused.
- [measurement-setup.md](resources/measurement-setup.md) — the four numbers to track, and how to run a change so the result means something.

## Who this is for

Store owners fixing their own SEO. Freelancers and marketers auditing WooCommerce or WordPress sites. Print-on-demand sellers with large catalogues and thin product pages. Anyone who would rather follow a written process than guess.

You do not need to write code to use any of it.

## Scope and honest limitations

- This is written by someone who works in SEO, WordPress, WooCommerce, print-on-demand and e-commerce content. It is not engineering advice and does not pretend to be.
- Nothing here guarantees rankings. Search engines change, platforms change, and your competitors are working too.
- Every recommendation is something to verify on your own store. Where this repository disagrees with current official documentation, the documentation is right and I would like to know so I can fix the file.
- All wording is original. Nothing is copied from blogs, forums or vendor documentation.

## How this repository is maintained

Files are added when there is something tested and worth writing down, not on a schedule. What is planned next, and why, is in [ROADMAP.md](ROADMAP.md). Existing files are corrected when a platform or a search engine changes behaviour. The commit history is the changelog.

## Contributing

Corrections are genuinely welcome, especially counter-examples from your own store. See [CONTRIBUTING.md](CONTRIBUTING.md).

## Licence

Released under the MIT Licence. You may reuse and adapt this documentation as long as the copyright and licence notice stays with it. See [LICENSE](LICENSE).

## Contact

Open an issue on this repository. It is the fastest way to reach me about anything published here.
