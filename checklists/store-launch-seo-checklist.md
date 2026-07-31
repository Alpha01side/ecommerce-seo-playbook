# Store Launch SEO Checklist

For new stores, replatforming, or a redesign going live. Work through it in order. The items near the top are the ones that cause months of damage if they are wrong, and minutes of work if they are right.

Print it, tick it, and keep the finished copy with the launch date on it.

## Two weeks before launch

- [ ] Decide the single canonical domain: with or without www, http or https. Write it down.
- [ ] Confirm the staging site is behind authentication, not just robots.txt.
- [ ] Export a full list of current URLs if a site already exists. This is the only chance to get it cleanly.
- [ ] Map every old URL to its closest new equivalent. Anything with traffic, links or sales in the last year must have a destination that is not the home page.
- [ ] Agree the URL structure for products and categories, and check it against how people search rather than how the admin is organised.
- [ ] Decide which filter, sort and search URLs will be kept out of the crawl.
- [ ] Confirm someone owns analytics and Search Console access, and that it is not an agency's personal account.

## One week before

- [ ] Write titles and meta descriptions for the home page, top ten categories and top twenty products. Not all of them, the ones that matter.
- [ ] Write real introductory copy for the top categories.
- [ ] Check every product has at least one original paragraph of description.
- [ ] Confirm images are resized, compressed and named before upload.
- [ ] Set up the redirect rules in staging and test a sample of fifty, including edge cases with parameters and trailing slashes.
- [ ] Check the 404 page is helpful: search box, links to main categories, no dead end.
- [ ] Confirm shipping, returns, contact and about pages exist and say something real. These matter for buyer trust and for how the store is assessed.

## Launch day, before the switch

- [ ] Remove any site-wide noindex from staging. This is the single most common launch mistake and it is worth checking twice.
- [ ] Confirm robots.txt on the live site allows crawling of what should be crawled.
- [ ] Check HTTPS works on every URL pattern and that mixed content warnings are gone.
- [ ] Verify the canonical domain redirects: non-www to www or the reverse, http to https, in one hop.
- [ ] Load the home page, a category and a product in a private window and check nothing requires login.

## Launch day, after the switch

- [ ] Crawl the live site immediately. Look for unexpected 404s, redirect chains and noindex tags.
- [ ] Submit sitemaps in Search Console, split by products, categories and content.
- [ ] Check analytics is recording, including add-to-cart and purchase events.
- [ ] Test checkout end to end on a phone.
- [ ] Confirm structured data validates on one product, one category and the home page.
- [ ] Record baseline speed measurements for home, one category and one product page.

## First week after launch

- [ ] Check the indexation report daily for the first few days, then weekly.
- [ ] Watch for old URLs still being requested, and add redirects for anything you missed.
- [ ] Search for a distinctive phrase from your product copy in quotation marks to find duplicate copies of the store.
- [ ] Check server logs or the crawl stats report to see what is being crawled most. If it is filter URLs, fix that now rather than later.
- [ ] Fix any 404s that are receiving real traffic.
- [ ] Do not change titles or URLs again this week. Let things settle so you can tell what is happening.

## First month

- [ ] Compare indexed URL count against the number you intended. Investigate any large gap in either direction.
- [ ] Review the first search queries arriving. They often reveal how customers describe your products differently from how you do.
- [ ] Add internal links from your best content to your most important categories.
- [ ] Write or improve copy on the five categories with impressions but poor click-through.
- [ ] Record what changed and when, in one place. This becomes your reference for every later diagnosis.

## Migration-specific extras

If you are replatforming rather than launching new:

- [ ] Keep the old site accessible privately for a month so you can compare content.
- [ ] Preserve page titles and copy where they were already performing. Redesign is not a reason to rewrite what works.
- [ ] Expect a temporary dip. Judge the migration at six to eight weeks, not at six days.
- [ ] Keep the redirect map forever. Deleting it is the reason old migrations become unfixable.

## What not to do on launch week

Do not run a large price test, a new plugin rollout and a redesign at once, because you will never know what caused what. Do not remove old content because it looks dated; check its traffic and links first. Do not chase perfect speed scores while checkout is untested. Sales and stability come first, and the search visibility follows.
