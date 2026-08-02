# Monthly SEO Maintenance Checklist

Stores decay. Products go out of stock, plugins update, someone adds a redirect loop, a category quietly loses its introduction during a theme change. This is the routine that catches those things before they become a quarter of lost traffic.

Budget ninety minutes a month. Do it on the same day each month so the comparisons are clean.

## Part 1: Health, about 20 minutes

- [ ] Run a crawl of the store and compare the URL count with last month. A sudden jump usually means new parameter URLs.
- [ ] List new 404s that are receiving traffic. Redirect the ones with a sensible destination; leave the rest.
- [ ] Check for redirect chains created since last month and flatten them to one hop.
- [ ] Confirm no accidental noindex has appeared on important templates after a plugin or theme update.
- [ ] Check the sitemap still contains only live, indexable URLs.
- [ ] Confirm HTTPS and the canonical domain redirect still behave correctly.

## Part 2: Indexation, about 15 minutes

- [ ] Compare the indexed URL count with last month and with the number you intend to have.
- [ ] Review anything newly excluded and decide whether it matters.
- [ ] Spot-check five products added last month. Are they indexed, and are they linked from a category?
- [ ] Look for indexed URLs you did not intend: filters, internal search, tag archives, staging leaks.

## Part 3: Performance, about 15 minutes

- [ ] Measure the same three URLs you always measure: home, one category, one product. Same tool, same settings.
- [ ] Compare against last month and note anything that moved by more than a small margin.
- [ ] Check the list of active plugins. Anything new since last month? Anything nobody uses?
- [ ] Check the transferred size of one category grid. Image bloat creeps back in with new products.

## Part 4: Content and demand, about 25 minutes

- [ ] Pull the last 28 days of queries and compare with the previous 28 days.
- [ ] List pages with rising impressions but low click-through. These need a better title and meta description, not more content.
- [ ] List pages that lost position. Check whether a competing page of your own appeared.
- [ ] Note any query you are getting that you do not have a good page for. That is your content backlog, built from real demand rather than guesswork.
- [ ] Take that backlog through the four gates in [../docs/search-intent-and-query-mapping.md](../docs/search-intent-and-query-mapping.md) before adding anything to it. Most rows should end as a paragraph on a page that already exists, or as a recorded decision not to build.
- [ ] Pick one commercial query and check how many of your own URLs receive impressions for it. If more than one does, and the position is stuck, follow the diagnosis in the same guide.
- [ ] Review your top ten products: is the copy still accurate on price, stock, sizing and shipping?
- [ ] Check that seasonal categories from last year are either updated or unlinked, not left saying "Christmas 2024".

## Part 5: Links, about 10 minutes

- [ ] Find pages with no internal links pointing to them and give the important ones a link.
- [ ] Add at least one internal link from your best-performing content page to a commercial page.
- [ ] Check out-of-stock products have a route onward for the visitor.

## Part 6: Record it, about 5 minutes

- [ ] Write one line per change: date, what changed, why, and what you expect.
- [ ] Note this month's baseline numbers: indexed URLs, clicks, impressions, the three speed measurements.
- [ ] Write down the one thing you will do next month if this month's changes work.

## Quarterly additions

Every third month, add these:

- [ ] Full crawl comparison against the same crawl three months ago.
- [ ] Review of category structure: has demand shifted enough to justify a new collection or merging two weak ones?
- [ ] Structured data validation across a sample of ten products, including a variable product and an out-of-stock one.
- [ ] A search for duplicate copies of your store on other domains or subdomains.
- [ ] A read-through of your top five product pages as if you were a first-time buyer. Note what you cannot answer from the page.

## Why the recording matters more than the checks

Any competent crawler will tell you what is broken. Nothing will tell you what you changed in April and whether it worked. A store owner with twelve months of one-line change notes can diagnose a traffic drop in an afternoon. Without it, every diagnosis starts from zero and usually ends in guessing.
