# Structured Data Examples

Worked examples to sit alongside the schema implementation notes in `docs/`. Every value below is invented. Replace them with what your page actually renders, and validate before you rely on any of it.

The rule that governs all of these: the markup must match what a visitor sees on the page.

## 1. Simple product, in stock

The minimum that is genuinely useful. Nothing invented, no ratings.

```json
{
  "@context": "https://schema.org",
  "@type": "Product",
  "name": "Allotment Gardener Mug",
  "sku": "MUG-ALLOT-11",
  "description": "An 11oz ceramic mug printed with a hand-drawn allotment plan, printed on both sides.",
  "image": [
    "https://example.com/images/allotment-gardener-mug-front.jpg",
    "https://example.com/images/allotment-gardener-mug-bench.jpg"
  ],
  "offers": {
    "@type": "Offer",
    "url": "https://example.com/shop/allotment-gardener-mug/",
    "price": "14.00",
    "priceCurrency": "GBP",
    "availability": "https://schema.org/InStock",
    "itemCondition": "https://schema.org/NewCondition"
  }
}
```

## 2. Out of stock, and back-ordered

Two different situations that people often mark up identically.

Out of stock, no date known:

```json
"offers": {
  "@type": "Offer",
  "url": "https://example.com/shop/allotment-gardener-mug/",
  "price": "14.00",
  "priceCurrency": "GBP",
  "availability": "https://schema.org/OutOfStock"
}
```

Available to order, shipping later:

```json
"offers": {
  "@type": "Offer",
  "url": "https://example.com/shop/allotment-gardener-mug/",
  "price": "14.00",
  "priceCurrency": "GBP",
  "availability": "https://schema.org/BackOrder"
}
```

If the page says "back in stock next week", the markup should not say InStock. That mismatch is the most common cause of a listing showing a price and availability that annoy the customer before they arrive.

## 3. Variable product with a price range

For a parent page that covers several sizes at different prices. Use this when the page itself shows a range rather than defaulting to one variant.

```json
{
  "@context": "https://schema.org",
  "@type": "Product",
  "name": "Allotment Gardener T-Shirt",
  "sku": "TEE-ALLOT",
  "description": "Hand-drawn allotment plan printed on a mid-weight cotton t-shirt, sizes S to 3XL.",
  "image": "https://example.com/images/allotment-tee-front.jpg",
  "offers": {
    "@type": "AggregateOffer",
    "url": "https://example.com/shop/allotment-gardener-t-shirt/",
    "priceCurrency": "GBP",
    "lowPrice": "22.00",
    "highPrice": "28.00",
    "offerCount": "6",
    "availability": "https://schema.org/InStock"
  }
}
```

The trap here is marking up `lowPrice` as the single price while the page defaults to the middle size. Either show the range on the page or mark up the default variant, and keep the two consistent.

## 4. Breadcrumbs

Low effort, useful, and it must match the trail shown on the page.

```json
{
  "@context": "https://schema.org",
  "@type": "BreadcrumbList",
  "itemListElement": [
    {
      "@type": "ListItem",
      "position": 1,
      "name": "Home",
      "item": "https://example.com/"
    },
    {
      "@type": "ListItem",
      "position": 2,
      "name": "Gifts for gardeners",
      "item": "https://example.com/shop/gifts-for-gardeners/"
    },
    {
      "@type": "ListItem",
      "position": 3,
      "name": "Allotment Gardener Mug"
    }
  ]
}
```

The final item has no `item` URL because it is the current page.

## 5. Reviews, only when they exist

Include this **only** if the reviews are visible on the page and generated from real customer submissions.

```json
"aggregateRating": {
  "@type": "AggregateRating",
  "ratingValue": "4.6",
  "reviewCount": "38"
}
```

If you have three reviews, say three. Rounding up, importing ratings from another platform that are not shown on the page, or carrying a store-wide rating onto every product are all misrepresentations, and they are the kind that get rich results removed.

## 6. Organisation, once, on the home page

```json
{
  "@context": "https://schema.org",
  "@type": "Organization",
  "name": "Example Allotment Prints",
  "url": "https://example.com/",
  "logo": "https://example.com/images/logo.png",
  "contactPoint": {
    "@type": "ContactPoint",
    "contactType": "customer service",
    "email": "hello@example.com"
  }
}
```

## Checking your work

1. Validate the URL in a structured data testing tool and read the errors rather than skimming them.
2. View the rendered page and confirm the price, availability and name in the markup match what is displayed.
3. Confirm there is only one Product block on the page. Two competing blocks, one from the platform and one from a plugin, is extremely common.
4. Re-test after any plugin or theme update, because markup is frequently regenerated.

Specifications and search engine requirements change. Check current official documentation before implementing, and open an issue here if you find something in this file that is out of date.
