# Search Intent and Query-to-Page Mapping

The rest of this repository decides which pages exist, how they are structured, and whether a search engine can reach them. This guide decides what each page is **for**: what the person searching is trying to accomplish, which type of page should answer them, and what to do when two of your own pages answer the same search.

Two existing files depend on this and do not explain it. [category-and-catalogue-architecture.md](category-and-catalogue-architecture.md) makes demand the first gate a category has to pass. [faceted-navigation-decision-framework.md](faceted-navigation-decision-framework.md) makes it the first of three questions a filter has to pass before it earns a page of its own. Both tell you to use evidence rather than intuition. Neither tells you how to gather it. This is that half.

This is not keyword research. There is no tool to buy, no volume column to sort by, and nothing here about placing terms in copy. Estimated volumes describe a market; they do not tell you which of your pages should answer a search, which is the only question that changes what you build. Everything below runs on demand you can observe on your own store.

## Step 1: Decide what the person is trying to accomplish

Intent belongs to the search, not to the searcher. The same customer will move through all four of the following in a week, and will expect a different kind of page each time.

**Get one specific item.** They already know what they want and are looking for the page that sells it. A model name, a code, a brand and a variant together.

**Choose within a type.** They know the category and not the item. Plural nouns, qualifiers, constraints: a use, a size, a material, a person to buy for. This is the largest group on most stores and the one most often answered badly, because a single product page cannot honestly answer it.

**Understand something before committing.** They are not ready to choose. They want to know how a thing is measured, what the difference between two materials is, or whether they need one at all.

**Resolve a doubt that is blocking the purchase.** Sizing, delivery, returns, care, compatibility. Narrow, specific, and often typed by someone who is already on your site.

Three tests to place a search, in order. First, finish the sentence "I want to..." in the searcher's words and see which of the four it lands in. Second, look at what is already ranking for it: if the results are all category listings, the search is a choosing search whatever you think of it, and a product page will not win it. Third, look at what the person did next on your own site, which the internal search log will often tell you.

Intent moves. A term that was a choosing search two years ago becomes a specific-item search once one product dominates the market. Date the judgement so you can see when it aged.

## Step 2: Read the demand you already have

Four sources. These are the same sources the architecture guide and the filter framework both point at, described properly for once.

**The Search Console performance report.** It breaks what you receive from Google down by query and by page, with impressions, clicks and average position for each. See [Get started with Search Console](https://developers.google.com/search/docs/monitor-debug/search-console-start). Two views matter here: queries where you have impressions and almost no clicks, which usually means the wrong page is answering, and queries where the same phrase is spread across several of your URLs, which is Step 6.

**Your internal site search.** The most honest source you have, because it is your own customers typing in their own words with no interface prompting them. It has to be recorded to be useful; check that your analytics is capturing site search and that your theme's search actually passes through it before you trust an empty report.

**Autocomplete and related searches.** Type your category names into Google and read what is offered. Useful for the shape of phrases rather than their popularity. Treat it as a vocabulary source.

**Your own catalogue.** Every category name, tag and product title is a claim about a search you intend to answer. Listing them alongside the three sources above shows the mismatch quickly: the phrases customers use that you have no page for, and the pages you built for phrases nobody types.

Record one row per query: the query, where you saw it, which of the four intents it is, which page currently receives impressions for it, and which page should own it. That table is the map, and it is the deliverable of this guide.

## Step 3: Decide whether any page should exist

Most queries do not deserve a page. Deciding this before choosing a page type stops the map from turning into a publishing backlog. Four gates, deliberately the same shape as the four questions in the architecture guide.

**Demand.** Do people actually search for this phrasing, in your two observed sources, rather than in your imagination?

**Difference.** Could you write this page without rewording a page you already have? If the honest answer is no, the demand belongs inside the existing page.

**Durability.** Will this still be searched, and will you still stock the answer, in six months?

**Deliverability.** Can you answer it well? A choosing search you can only meet with three products in stock is a page that disappoints, and disappointment is measurable.

| Gates passed | What it means | Action |
| --- | --- | --- |
| All four | A real gap | Build the page type chosen in Step 4 |
| Demand, no difference | You already answer it | Give it a section and an internal link on the existing page |
| Demand, no durability | A spike, not a pattern | Answer it inside a page that already exists |
| Demand, no deliverability | You cannot serve it yet | Note it against the buying plan, not the content plan |
| No demand | Your own internal vocabulary | Nothing. A tag at most |

## Step 4: Assign the query to a page type

| What they are trying to do | Typical shape | Page that should own it | Why that one |
| --- | --- | --- | --- |
| Get one specific item | Brand plus model, a code, an exact name | Product page | It is the only page that can complete the task |
| Choose within a type | Plural noun with a qualifier, a use, a constraint | Category page | It shows the choice; a product page hides it |
| Choose within a narrow, durable attribute | A qualifier people say as a phrase | A promoted filter page, built as a real page | Covered in Step 5 of the filter framework |
| Buy within a brand | Brand alone, brand plus category | Brand archive, written | The brand is the deciding factor, not the product type |
| Understand before choosing | How, what, which, whether | Buying guide | It answers without selling, and can link to everything relevant |
| Decide between two named things you sell | One thing against another, alternatives to | Comparison page | Only worth building where both are genuinely stocked and comparable |
| Resolve a specific doubt | Does it, can I, how long, what if | A section on the commercial page, or an FAQ page if there are many | Usually a paragraph, not a page |

Four of these need qualification.

**Brand pages.** Brands are now part of WooCommerce itself rather than a separate extension, and behave like categories: hierarchical, with a name, description, image and their own archive page, and assigning one adds brand information to the product's structured data. See the [product brands documentation](https://woocommerce.com/document/managing-product-taxonomies/product-brands/). What the platform gives you is an archive; what it does not give you is a reason for that archive to rank. An unwritten brand archive is a template listing with no copy, and it should pass the same four gates in Step 3 as any category before you index it. Brand pages earn their place when customers shop by brand. On a store where the brand is invisible to the buyer, they are pages nobody searches for.

**Buying guides.** Their value is not only the search they answer. They are the page type that can legitimately link to categories and products with commercial anchor text, which matters because Google works out the relative importance of your pages from the links between them rather than from the shape of your URLs, as set out in [Help Google understand your ecommerce website structure](https://developers.google.com/search/docs/specialty/ecommerce/help-google-understand-your-ecommerce-site-structure). A guide with no links to the pages it discusses is a missed opportunity twice over. See [internal-linking-guide.md](internal-linking-guide.md).

**Comparison pages.** Only for two named things you actually sell, where a real customer really does hesitate between them. Generating a comparison for every possible pair is how a catalogue of forty products becomes eight hundred thin pages.

**FAQ pages.** Build these for customers, not for markup. Google removed its FAQ rich result documentation in June 2026 because the feature is no longer shown in search results, as recorded in the [Search Central documentation updates](https://developers.google.com/search/updates). The [FAQPage](https://schema.org/FAQPage) type still exists in the schema.org vocabulary, so the markup is not invalid; it simply no longer buys you anything in Google's results. That removes the only reason many stores had for splitting answers onto a separate page. Most of the time the answer belongs on the product or category page, where the doubt actually occurs.

## Step 5: When two page types could answer, decide who owns it

A query has exactly one owner. The owner targets it in the title, the first heading and the internal anchor text pointing at it. Every other page may discuss the subject and link to the owner using that phrase. Without a written owner you get the failure the glossary already names: two of your pages competing, both ranking poorly, swapping positions.

Four questions, in order. The first one that gives a clear answer decides it.

1. **Which page completes the task?** If the search implies a choice, only a page showing several options can complete it.
2. **Which page would annoy the person who landed on it?** Arriving at a single product after searching for a category is annoying. Arriving at a listing of forty after searching for one model is worse.
3. **Which page can be written about this without repeating the other?** If both can, one of them is thin.
4. **Which page do you already point at with that phrase?** Existing internal anchors are a vote you have already cast; changing the owner means changing them.

### Category against its best-selling product

The most common collision, and the one the roadmap flagged. A category exists for a type of product; one product in it outsells everything else and its page slowly acquires all the copy, all the reviews and most of the internal links, until it starts appearing for the category phrase.

The category owns the plural, choosing phrase. The product owns its own name and its distinguishing attributes. The fix is almost never a redirect: it is retargeting the internal anchors so that the category receives the commercial phrase, and rewriting the product page to be about that product rather than about the type.

### Category against the guide written about it

A guide about choosing within a type and the category listing that type will compete unless you separate them deliberately. The guide owns the question phrasing. The category owns the buying phrasing. The guide links to the category using the buying phrase; the category links to the guide for people who are not ready. If you cannot tell them apart when you read them side by side, you do not have two pages, you have one page and a duplicate.

### Category against a promoted filter page

Already decided in [faceted-navigation-decision-framework.md](faceted-navigation-decision-framework.md): a facet that passes all three of its questions stops being a facet and becomes a page. The parent category then owns the broad phrase and the promoted page owns the qualified one. If the promoted page shows nearly the same products as its parent, it was never a page.

### Brand page against category

The brand archive owns brand plus product type. The category owns the type alone. If several brands compete inside one category, the category owns everything unqualified and the brand pages own only their own names.

## Step 6: Diagnosing cannibalisation

The glossary defines it. Here is how to see it rather than suspect it.

In the performance report, filter to the single query, then look at which of your pages received impressions for it. More than one URL appearing for a commercial phrase over a long enough window is the signal. Compare two consecutive periods of the same length: the signature is the URLs alternating between periods while the average position sits stubbornly outside the top results, with impressions that are healthy and clicks that are not.

Then check what Google itself considers the canonical version, using the URL inspection tool. Google may choose a different canonical from the one you declared, and [Google's canonicalisation troubleshooting guidance](https://developers.google.com/search/docs/crawling-indexing/canonicalization-troubleshooting) is explicit that fixing this comes down to making the clustered pages sufficiently different from each other. If your two competing pages have been clustered, that is your answer: they are not different enough, and no amount of retitling will fix content that says the same thing.

Rule out the boring explanations before you rebuild anything. A drop can be seasonal, algorithmic, or technical, and Google's guide to [debugging search traffic drops](https://developers.google.com/search/docs/monitor-debug/debugging-search-traffic-drops) is worth working through first. Positions move on their own; a page that fell from second to fourth has not been cannibalised, it has had a normal week.

The false positive worth naming: two of your pages both ranking and both being clicked for the same phrase is not a problem. It is two results instead of one. Leave it alone.

## Step 7: Fixing it

In this order. Stop as soon as it is fixed.

**Differentiate the content.** Decide what each page is about and rewrite until a reader could tell you the difference in one sentence. This is the only fix that addresses the cause. Expect it to take time: Google may keep pages in a duplicate cluster for up to a fortnight after the content changes, and they separate faster when the difference is clear and substantial rather than cosmetic. You can ask for re-evaluation through the URL inspection tool, but that request is subject to quotas, so save it for pages that matter.

**Retarget the internal links.** Find every internal link using the contested phrase and point them all at the owner. On most stores this is the actual cause, not a secondary step, because the store has spent two years linking to the wrong page with the right words. See [internal-linking-guide.md](internal-linking-guide.md).

**Adjust titles and headings.** Only after the first two. Retitling pages that still say the same thing moves the problem rather than solving it.

**Merge, and redirect the loser.** Only when the two pages genuinely serve one purpose and always did. Redirect to the page that answers the search, not to the home page or to a parent category, for the reasons set out in [product-lifecycle-seo.md](product-lifecycle-seo.md).

**Do nothing.** Both pages performing is not a defect.

Two things not to do. Do not add a canonical tag between two pages that are not duplicates in order to pick a winner; canonicals are a consolidation signal for genuinely equivalent pages and are treated as a hint, which [technical-seo-notes.md](technical-seo-notes.md) covers. And do not noindex one of two commercially valuable pages as a first move, which loses the traffic instead of fixing the confusion.

## Step 8: Deciding that no page should exist

Written down so it counts as a decision rather than an omission. The honest answer is no page when: the demand exists but you would be rewording an existing page; the demand is a seasonal spike you can meet with a paragraph; the query is a filter behaviour rather than a phrase, which Step 2 of the filter framework already tests for; you cannot stock a satisfying answer; or the query belongs to a doubt that should be resolved where it occurs, on the product page, rather than in a separate FAQ.

Record the decision and the date. A no now is not a no forever, and the reason is what tells you when to revisit.

## A composite example

Composite, not a real client: a 400-product outdoor clothing store, the same shape used elsewhere in this repository.

Five queries taken from one month of Search Console and internal search, and what the map said.

*Waterproof walking trousers* — choosing, all four gates passed, owner is the existing category. Currently a product page was receiving the impressions and converting badly, because eleven internal links used the phrase to point at the best seller. Retargeted the anchors, rewrote the product page around its own name and features. Both pages recovered, the category faster.

*How to wash a waterproof jacket* — understanding, no commercial page can answer it honestly, owner is a new buying guide that links to two categories with the buying phrasings.

*Brand plus base layers* — buying within a brand, the brand archive existed but had no description at all. Written rather than created.

*Trousers in a specific colour* — a filter behaviour, not a phrase. No page. Recorded as a no with the reason.

*Do your trousers come in a short leg* — a doubt. Two lines added to the category copy and to the sizing section of the affected products. No page, and site search for it fell the following month, which was the point.

## Keep the map

One file, one row per query, with the query, its intent, the owning page, the date of the decision, and a note if it was contested. Re-read it quarterly against a fresh performance report. Three things change: a query gets a new owner because you built something better, an owner starts losing to another of your own pages, or a query stops being searched. All three are visible in ten minutes if the map exists and invisible if it does not. Measure the outcomes the way [measurement-setup.md](../resources/measurement-setup.md) describes, so that a change and its result can be connected.

## Mistakes to avoid, including ones I have made

**Assigning a choosing query to a product page because that product sells well.** The page cannot complete the task. I did this for a season and it looked fine in the rankings and terrible in the conversion data.

**Treating every duplicated appearance as cannibalisation.** Sometimes two of your pages ranking is simply two of your pages ranking.

**Building an FAQ page because of the markup.** That reason no longer exists in Google's results, and it was always the weakest reason to split an answer away from the page where the question is asked.

**Creating brand archives for every brand in the catalogue.** Most were empty template listings competing with the categories that already worked.

**Rewriting titles first.** It is the fastest thing to change and the least likely to help, which is exactly why it is tempting.

**Letting the map become a content plan.** Its main output is the decisions not to build, and a map with no rejected rows on it has not been used honestly.

## Verify before implementing

Search Console report names, filters and data retention change, so confirm the current behaviour of the performance report before building a routine around a particular view. Google's search features change too: the FAQ rich result was retired in 2026, and anything you build around a feature should be checked against the current [Search Central documentation](https://developers.google.com/search/docs/appearance/structured-data/search-gallery) rather than against a blog post or against this file. Confirm how your own WooCommerce version and theme handle brand archives, including whether the archive template outputs your description at all. And check the current canonicalisation and traffic-drop guidance linked above before you conclude that two of your pages are competing.

## Related files

- [category-and-catalogue-architecture.md](category-and-catalogue-architecture.md) — which pages should exist. This guide decides what they are for.
- [faceted-navigation-decision-framework.md](faceted-navigation-decision-framework.md) — the demand test applied to filters, and when a facet becomes a page.
- [internal-linking-guide.md](internal-linking-guide.md) — how to move anchor text onto the owning page once ownership is decided.
- [technical-seo-notes.md](technical-seo-notes.md) — canonicals, indexation and what they can and cannot resolve.
- [product-lifecycle-seo.md](product-lifecycle-seo.md) — where a redirect should point when a merge is the right answer.
- [../templates/product-copy-brief.md](../templates/product-copy-brief.md) — the brief that asks which query a page should answer and whether another page competes for it.
- [../checklists/monthly-seo-maintenance-checklist.md](../checklists/monthly-seo-maintenance-checklist.md) — the monthly pass that feeds new queries into the map.
- [../resources/glossary.md](../resources/glossary.md) — definitions, including cannibalisation.
