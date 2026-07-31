# WooCommerce Performance Guide

Speed work on a WooCommerce store fails for the same reason most SEO work fails: people change many things at once and then cannot tell what helped. This guide is the order I follow, written for store owners and marketers rather than developers.

## Measure before you touch anything

Pick three URLs and treat them as your fixed test set:

1. The home page.
2. One category page with a realistic number of products and filters enabled.
3. One product page, ideally a variable product, because that is usually the heaviest template.

Test each one on a mobile profile and write down the result with the date. A category page behaves nothing like a home page, so a single home page score tells you very little about the store your customers actually browse.

## Understand what is actually slow

Most WooCommerce slowness comes from a small number of causes, and they are rarely the ones people blame:

**Too many plugins doing work on every request.** The count matters less than what each one loads. A single page builder or slider plugin can outweigh twenty small utility plugins.

**Uncached dynamic pages.** Cart, checkout and My Account cannot be cached the way a blog post can. If your cache plugin is also excluding categories or products, you are serving everything dynamically.

**Images at the wrong size.** A 3000 pixel product photo displayed in a 600 pixel frame costs the visitor bandwidth for nothing. On print-on-demand catalogues this is usually the single biggest win.

**Render-blocking scripts and fonts.** Chat widgets, review apps, tracking pixels and multiple font weights delay the moment the page becomes usable.

**Hosting that cannot handle PHP work.** Shared hosting often looks fine on a static page and collapses on cart and checkout, which are exactly the pages that decide revenue.

## Fix in this order

Work top to bottom, and re-measure after each step so you know what each change was worth.

1. **Hosting and PHP version.** Use a current supported PHP version and hosting sized for WooCommerce. No plugin compensates for an overloaded server.
2. **Caching.** Page caching for catalogue pages, object caching if your host supports it, and correct exclusions for cart, checkout and account pages.
3. **Images.** Resize before upload, compress, serve modern formats, and lazy load everything except the main image in the viewport.
4. **Plugin audit.** List every active plugin, write next to each what it does for the business, and deactivate anything you cannot justify. Test on a staging copy first.
5. **Scripts and styles.** Stop loading cart fragments, block styles or slider libraries on pages that do not use them.
6. **Fonts.** Two weights of one family is usually enough. Self-host or preload the one used above the fold.
7. **Theme and template weight.** Only after the steps above, because theme changes are the most disruptive and the hardest to reverse.

## What to record

Keep a simple change log in this format, one line per change:

date | page tested | change made | metric before | metric after | notes

This is unglamorous and it is the single most useful habit in performance work. Six weeks later it is the only way to answer the question "when did the product pages get slow again".

## Common mistakes I have made

- Chasing a perfect score on the home page while the category template stayed slow.
- Enabling every option in an optimization plugin at once, breaking the add-to-cart button, and not knowing which setting did it.
- Deleting a plugin without checking whether its shortcodes were still used in old product descriptions.
- Testing only over office wifi on a fast laptop.
- Treating speed as an SEO task. It is a conversion task first; search visibility is a side effect.

## How this connects to SEO

Speed will not rescue a page that does not answer a buying question, and it will not create demand that was never there. What it does is remove friction on pages that already earn impressions. Fix the page quality issues in the product page checklist first, then make those pages fast, and keep a record of both.

Verify anything here against current official WordPress, WooCommerce and Google documentation before relying on it. If something in this guide is out of date, please open an issue.
