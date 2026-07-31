# Product Structured Data Notes (WooCommerce)

Structured data does not improve rankings by itself. What it does is let a search engine read your product details with less guessing, which is how you become eligible for rich results such as price, availability and review stars. This file is my working note on getting it right on WooCommerce stores without overreaching.

## The rule that matters most

Markup must describe what a visitor can actually see on the page. If the price in your markup is 19.99 and the page shows 24.99, or the markup claims an aggregate rating when the page has no reviews, you are not being clever. That is the kind of mismatch that gets rich results removed and, in bad cases, gets a manual action.

## What WooCommerce usually handles for you

Modern WooCommerce outputs product structured data by default, and most SEO plugins extend or replace it. Before adding anything yourself, check what is already on the page. Two competing sets of product markup on one URL is a more common problem than missing markup.

To check: open the product page, view the rendered source, and search for the product type declaration. Then run the URL through a structured data validator and read what it reports rather than what you assume.

## Fields worth getting right

- **name** — the product name as a customer would say it, matching the H1.
- **image** — the main product image at a usable resolution, not a thumbnail.
- **description** — a real description, not the whole page dumped in.
- **sku** — your own identifier; keep it stable over time.
- **brand** — only if you have a genuine brand for the product.
- **offers.price and priceCurrency** — must match the displayed price, including tax presentation.
- **offers.availability** — must follow real stock status, including back orders.
- **offers.url** — the canonical product URL.

## A minimal, honest example

This is a stripped-down shape for a simple product. Values are placeholders; replace them with the real ones your page renders.

```json
{
  "@context": "https://schema.org",
  "@type": "Product",
  "name": "Heavyweight Cotton Crew T-Shirt",
  "sku": "TSH-CRW-BLK",
  "description": "Mid-weight combed cotton crew neck with a set-in collar, printed to order.",
  "image": "https://example.com/wp-content/uploads/tsh-crw-blk-front.jpg",
  "offers": {
    "@type": "Offer",
    "url": "https://example.com/product/heavyweight-cotton-crew-t-shirt/",
    "price": "24.00",
    "priceCurrency": "USD",
    "availability": "https://schema.org/InStock"
  }
}
```

Note what is absent: no rating, no review count, no invented availability. Add those only when the page really has them and they are generated from live data rather than typed in once and forgotten.

## Variable products

For a variable product you have two defensible options. Either describe the parent product with a price range, or output the specific variation when a variation is selected and reflected in the URL. What you should not do is mark up the cheapest variation price while the page defaults to a more expensive one. That mismatch is exactly what customers complain about when a listing price does not match the page.

## Breadcrumbs

Breadcrumb markup is low effort and genuinely useful, because it lets search results show a readable path instead of a raw URL. Make sure the marked-up trail is the same one shown on the page, and that it reflects the category the product actually sits in.

## Things I check before calling it done

- The validator reports no errors and the warnings are ones I understand and accept.
- Only one set of product markup exists on the page.
- Price, availability and currency match the rendered page on a hard refresh.
- No review or rating markup without visible reviews.
- The canonical URL and the offer URL agree.
- Spot-check a variable product, a back-ordered product and an out-of-stock product, not just a simple in-stock one.

Structured data specifications and search engine requirements change. Validate against current official documentation before relying on anything here, and please open an issue if you find something out of date.
