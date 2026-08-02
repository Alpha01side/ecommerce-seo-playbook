# Product Lifecycle SEO: Out of Stock, Discontinued and Seasonal Products

[technical-seo-notes.md](technical-seo-notes.md) settles this in two sentences: a product that is genuinely gone with no replacement can return a 404, and a product that will come back should stay published with clear availability. Both are right, and neither is enough to act on, because most products are not at either extreme. This file is the whole decision.

It matters more than most on-page work because the mistakes are hard to undo. A product page that has been live for two years has accumulated rankings, internal links, sometimes external links, and reviews written by customers. A bulk delete or a bulk redirect to the shop page discards all of that in one action, and once the product record has left the database the copy, the slug and the reviews go with it.

## The question that decides everything

Will a buyer be able to purchase this product, or something they would accept in its place, at this URL again?

Everything below is a way of answering that consistently, instead of product by product, in a hurry, at the end of the month.

## Step 1: Put the product into one state

Assign one state per product. If two seem to apply, take the more conservative one and set an earlier review date.

| State | What it means | How you tell |
| --- | --- | --- |
| Temporarily unavailable | Stock has run out and more is coming | A reorder has been placed, or the supplier has confirmed a date |
| Unavailable, no date | Stock has run out and nothing is on order | Nobody has decided yet, which is the most common real situation |
| Discontinued, close replacement | You sell something that does the same job at a similar price | A buyer landing on the old page would be satisfied by the new product without needing it explained |
| Discontinued, nothing comparable | You no longer sell anything that does that job | The nearest thing you stock is a different product for a different need |
| Seasonal | Sold in a predictable window and returns | It sold last year in the same months and you intend to stock it again |
| Should not have been published | Duplicate, test product, bad import, wrong supplier feed | It never had a legitimate reason to exist |

Back-order and pre-order are not lifecycle states. They are purchasable states, and they are handled in Step 5.

## Step 2: The decision table

| State | The URL | Indexable | Availability in structured data | Internal links | Next review |
| --- | --- | --- | --- | --- | --- |
| Temporarily unavailable | Stays live, unchanged | Yes | OutOfStock, or BackOrder if you are taking orders | Keep all of them | When stock returns |
| Unavailable, no date | Stays live for a fixed window, ninety days as a default | Yes | OutOfStock | Keep all of them | End of the window, then reclassify |
| Discontinued, close replacement | 301 to the replacement product | Not applicable | Not applicable | Repoint them to the replacement | Ninety days after the redirect |
| Discontinued, nothing comparable, still earns visits or has external links | Stays live and says plainly that it is no longer available | Yes | Discontinued | Keep the category and alternative links, drop it from related-product carousels | Annually |
| Discontinued, nothing comparable, no visits and no external links | 404, or 410 if you are certain it will never return | Not applicable | Not applicable | Remove them | None |
| Seasonal | Stays live all year at the same URL | Yes | OutOfStock out of season | Keep the category links | Each season |
| Should not have been published | 410 | Not applicable | Not applicable | Remove them | None |

The default is to leave the page alone. Every other option costs something: a redirect gives up the page, a 404 gives up the page and the value of the links pointing at it, and both are more work than doing nothing. Take those options when you can say what you are buying with them.

## Step 3: Redirects, and where they should point

A redirect is a claim that one page is a reasonable substitute for another. If the claim is weak the redirect does not help: a redirect to a page that is not equivalent can be treated as a soft 404, so the old URL drops out anyway and you have also removed the page a visitor could have read. That is the loss without the benefit.

Three rules:

- Redirect to the closest equivalent product, not to the category and never to the home page. If nothing is close enough, keep the page or return a 404 instead.
- One hop. When the replacement is itself retired later, update the original rule rather than chaining onto it.
- Record the old URL, the new URL, the date and the reason in the change log described in [../resources/measurement-setup.md](../resources/measurement-setup.md).

The test for "close enough": would a buyer who came looking for the old product be content to land on the new one without an explanation? If they would need the explanation, keep the old page and put the explanation on it.

## Step 4: What an unavailable page still has to do

A page that stays live has to be honest and useful, or it is a soft 404 with extra steps.

- Say the status in plain words near the top, not only by greying out a button.
- Give the expected return date if you have one. If you do not have one, say so rather than implying a date.
- Remove or disable the add to cart control. A button that fails is worse than no button.
- Offer three to five genuine alternatives from the same category and price range, chosen rather than auto-generated.
- Keep the description, the specifications, the images and the reviews. That content is why the page still ranks.
- Offer a back-in-stock notification if the store supports one.
- Do not replace the page body with "product not found" while still returning a 200. Either the page is useful or it should return a 404.

## Step 5: Availability, back-order and pre-order

Availability is a field to change, not a reason to remove the markup. Keep the Product structured data on the page and update the availability value.

- The values come from schema.org ItemAvailability. InStock, OutOfStock, BackOrder, PreOrder and Discontinued are the ones a store normally needs.
- The value has to match what the page says. If the page says "back in stock on the 14th" and the markup says InStock, the markup is wrong.
- Keep the price if the price is still real. If you no longer know what it will cost, do not show a price on the page either.
- Use BackOrder only if you can genuinely take the order and fulfil it, and put the expected date on the page.
- Use PreOrder with a release date the visitor can see.
- Confirm availability appears in the server response rather than being written in by a script after load. See the rendering section of [technical-seo-notes.md](technical-seo-notes.md).

Worked markup for in stock, out of stock and back-ordered products is in [../examples/schema-examples.md](../examples/schema-examples.md).

## Step 6: Reviews and links you have already earned

Reviews stay with the product they were written about. Do not move review markup or star ratings onto a different product because the original was retired: the markup has to describe the item on the page. If the retired product had reviews worth keeping, that is an argument for keeping the page, not for relocating them.

Before deleting or redirecting anything, check whether the URL has external links. External links are the one thing on a product page you cannot recreate by writing better copy. A page with real external links should be kept, or redirected to a genuine equivalent, rather than removed.

## Step 7: Seasonal products and collections

Seasonal ranges are where deleting and rebuilding costs the most, because the work repeats every year.

- Use one permanent URL per recurring season. A dated URL forces an annual redirect and each year's page starts from nothing.
- Keep the collection page indexable all year. A page that is unpublished for nine months has to be found and reassessed again every time it returns.
- Out of season, keep the page and change the content: say when the range comes back, and link to what is available now. Remove the promotional copy, keep the descriptive copy.
- Set the products out of stock rather than deleting them.
- Diary the reactivation as a job: availability, copy, internal links from the home page and the relevant categories, and a check that the page is still in the sitemap.

## Step 8: WooCommerce and WordPress behaviour to know before you act

Confirm these on your own installation, since themes and plugins change them.

- Setting a product to Out of stock does not unpublish it and does not change the URL. The page stays live, which is what the table above wants for most states.
- "Hide out of stock items from the catalog", in the product inventory settings, removes the product from category listings and internal search while the product page itself stays published and stays in the sitemap. That combination creates orphan pages. If you switch it on, do it knowingly, and read the orphan section of [internal-linking-guide.md](internal-linking-guide.md).
- Deleting a product moves it to the trash and the URL starts returning a 404 immediately. Emptying the trash is permanent. Put the redirect in place first, and export the product data before removing anything.
- Moving a product to Draft or Private also makes the URL return a 404 for visitors and crawlers. Unpublishing is not a neutral holding action.
- On a variable product, an unavailable variation does not make the parent unavailable. Retire the variation rather than the product, then check that the displayed price range and the default selection still make sense. [print-on-demand-catalogue-seo.md](print-on-demand-catalogue-seo.md) covers variations in more detail.
- Do not reuse a retired slug for a different product. The old URL will start showing something the visitor did not ask for, and any redirect written for it will conflict.

## Step 9: Record the decision so someone else can reverse it

One row per decision, in the same change log you use for everything else:

| Date | SKU | URL | State assigned | Action taken | Where it was implemented | Decided by | Review date |

Keep the product export for anything deleted. The point of the row is not tidiness. It is that in six months somebody will ask why a URL returns a 404, and the alternative to a written answer is guessing.

## Step 10: The quarterly pass

On a store of a few hundred products this takes about an hour.

1. Export every product with the stock status Out of stock, with the date it last sold.
2. Pull organic entrances and impressions for those URLs for the last quarter.
3. Add external link data if you have a source for it.
4. Assign each product a state from Step 1.
5. Apply the table in Step 2 in one batch, rather than product by product across the quarter.
6. Write the rows into the change log and diary the review dates.

Run it alongside the quarterly additions in [../checklists/monthly-seo-maintenance-checklist.md](../checklists/monthly-seo-maintenance-checklist.md).

## Mistakes to avoid

- Bulk redirecting every retired product to the home page or to its category.
- Deleting products to tidy the catalogue before checking traffic and links.
- Noindexing pages that are out of stock but still being searched for.
- Removing Product markup instead of changing the availability value.
- Using a dated URL for a collection that comes back every year.
- Redirecting to a "replacement" that a buyer would not accept as one.
- Hiding out of stock items from the catalogue and forgetting the pages are still published and still in the sitemap.
- Leaving an add to cart button on a page that cannot take an order.

## Verify before implementing

Platform behaviour and search engine handling both change. Check the sources below before a bulk action, test the change on one product and confirm the response code and the rendered markup, then record the date you checked. Where this file disagrees with current official documentation, the documentation is right.

## Sources

- Google Search Central, "Redirects and Google Search": https://developers.google.com/search/docs/crawling-indexing/301-redirects
- Google Search Central, "HTTP status codes, network and DNS errors, and how they affect Google Search": https://developers.google.com/search/docs/crawling-indexing/http-network-errors
- Google Search Central, "Product structured data": https://developers.google.com/search/docs/appearance/structured-data/product
- schema.org, ItemAvailability: https://schema.org/ItemAvailability
- WooCommerce documentation, "Managing Products": https://woocommerce.com/document/managing-products/

## Related files

- [technical-seo-notes.md](technical-seo-notes.md) — redirects, canonicals, sitemaps and rendering.
- [faceted-navigation-decision-framework.md](faceted-navigation-decision-framework.md) — the same policy-then-implement approach applied to filter URLs.
- [schema-implementation-notes.md](schema-implementation-notes.md) and [../examples/schema-examples.md](../examples/schema-examples.md) — availability markup.
- [internal-linking-guide.md](internal-linking-guide.md) — orphan pages and related products.
- [print-on-demand-catalogue-seo.md](print-on-demand-catalogue-seo.md) — variations and large catalogues.
- [../resources/measurement-setup.md](../resources/measurement-setup.md) — the change log.
- [../checklists/monthly-seo-maintenance-checklist.md](../checklists/monthly-seo-maintenance-checklist.md) — where the quarterly pass belongs.
