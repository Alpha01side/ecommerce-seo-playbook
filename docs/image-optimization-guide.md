# Image Optimization Guide for Product Catalogues

Images are the heaviest thing on almost every product page and the part store owners are most reluctant to touch, because photography feels sacred. It is not a choice between quality and speed. Most stores are shipping images four times larger than the screen will ever display, which helps nobody.

This guide is aimed at people managing dozens to thousands of product images, including print-on-demand catalogues where the same mockup template repeats across a whole range.

## Decide your display sizes first

You cannot optimise an image without knowing how big it will be shown. Open your product template on a phone and on a desktop, and note the actual rendered width of the main image, the gallery thumbnails, and the category grid tile. Most themes land somewhere near a 600 to 900 pixel main image on mobile and 800 to 1200 on desktop, with thumbnails under 200.

Everything else follows from those numbers. If your main image renders at 900 pixels wide on the largest screen you support, uploading a 4000 pixel file achieves nothing except a slower page and a larger backup.

## The upload rules I follow

**Resize before upload, not after.** Server-side resizing plugins are useful, but the original still sits in your uploads folder forever, inflating backups and migration times. Export at roughly twice your largest display width to allow for high density screens, and no more.

**Compress deliberately.** Test your own images at a few quality settings and look at them at display size, not zoomed in. For most product photography the point where quality visibly suffers is lower than people expect, and the file size difference between "fine" and "perfect" is often half the weight.

**Use a modern format with a fallback.** Modern formats typically save a meaningful share of the file size at equivalent quality. Serve them where supported and keep an older format as a fallback.

**Name the file before you upload it.** A descriptive, hyphenated file name costs nothing at upload time and is painful to fix later across a thousand products.

## Alt text, written properly

Alt text exists for people who cannot see the image. That is the whole standard, and following it happens to produce good SEO too.

Describe what the image shows, in the same words a customer would use, in a normal sentence fragment. For a product photo, that usually means the product, its distinguishing attribute, and its context if the image has one. Do not start with "image of" or "photo of", do not stuff a keyword list, and do not repeat the same alt text on every image in a gallery. If an image is purely decorative, leave the alt attribute empty so screen readers skip it rather than reading a filename aloud.

For print-on-demand catalogues where the same mockup repeats, write alt text that reflects the design and the product type together, so the fiftieth mug does not have identical alt text to the first.

## Loading behaviour

The main product image is the one thing the visitor came to see. It should load early and should not be lazy loaded. Everything below the fold, including the rest of the gallery, review avatars and cross-sell thumbnails, should be lazy loaded.

Always set explicit width and height attributes, or an aspect ratio, so the browser reserves the space before the image arrives. Without that, the page jumps as images load, the customer taps the wrong thing, and your layout stability score suffers for a reason that takes ten minutes to fix.

## Category and listing pages

Category grids are where image weight quietly destroys performance, because you are loading twenty to forty images at once. Serve genuinely small files to grid tiles rather than the full product image scaled down in the browser. Check the actual transferred size of one grid tile in your browser's network panel; if it is over a couple of hundred kilobytes, the grid is the problem, not the product page.

## Print-on-demand specifics

Three problems repeat in POD catalogues.

The same mockup, thousands of times. Identical images across hundreds of products give a search engine very little to work with, and give the customer nothing either. Add at least one image per product that shows the actual design in a real context, even if the rest of the gallery is templated.

Enormous source files from the design tool. Print files are made for printing. They should never be what the storefront serves. Keep the print file in your design storage, not in your media library.

Automated bulk uploads with machine file names and no alt text. If your integration pushes products automatically, fix the naming at the source. Fixing it later means editing every product.

## A quick audit you can run today

1. Open your most important product page on a phone-sized viewport with the network panel recording.
2. Sort by transferred size and note the three largest images.
3. Compare each transferred size against the rendered display size.
4. Check whether the main image is lazy loaded. If it is, that is your first fix.
5. Check three images for descriptive alt text and file names.
6. Repeat on one category page, because it will be worse.

Write down the total page weight before and after. Image work is one of the few areas of SEO where you can prove the improvement the same afternoon.

## What not to bother with

Do not chase a perfect score by removing images that help people buy. A product page with five clear photographs and a size reference converts better than a fast page with one thumbnail. The goal is to remove waste, not to remove evidence that the product is worth buying.
