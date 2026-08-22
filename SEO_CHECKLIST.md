# SEO and Social Sharing Checklist

This checklist is tailored to the current one-page site at `https://saasappnamegenerator.com/`. It covers search metadata, social previews, crawl files, and launch verification without adding packages, services, or unnecessary scripts.

## Current baseline

- [x] Declare the document as English with `<html lang="en">`.
- [x] Include UTF-8 character encoding.
- [x] Include the responsive viewport tag.
- [x] Set a browser theme color.
- [x] Use one clear, descriptive page title: `SaaS App Name Generator | Startup Name Ideas`.
- [x] Include one page-specific meta description.
- [x] Include one absolute, self-referencing canonical URL: `https://saasappnamegenerator.com/`.
- [x] Use one visible H1 that agrees with the page title: `SaaS App Name Generator`.

## Priority 1: create the missing visual assets

- [ ] Create `og-image.png` at 1200 x 630 pixels.
  - Make it a useful preview of this specific tool, not only a logo.
  - Keep important text away from the outer edges so social sites can crop it safely.
  - Use a stable public URL: `https://saasappnamegenerator.com/og-image.png`.
  - Write the image alt text before adding the tags. Suggested starting point: `SaaS App Name Generator interface showing generated startup name ideas`.
- [ ] Create a simple, recognizable square favicon based on this site's visual identity.
  - Create `favicon.svg` as the primary scalable icon.
  - Create a square PNG at least 48 x 48 pixels, preferably a multiple of 48 such as `favicon-96x96.png`.
  - Create `apple-touch-icon.png` at 180 x 180 pixels for saved iOS shortcuts.
  - Optional: create `favicon.ico` for older browsers.
  - Keep favicon URLs stable after launch.

## Priority 2: add social-sharing metadata to `index.html`

- [ ] Add the core Open Graph fields.
- [ ] Use absolute HTTPS URLs for `og:url` and `og:image`.
- [ ] Keep the Open Graph title and description aligned with the real page title and description.
- [ ] Include image dimensions, type, and meaningful alt text.
- [ ] Add an X/Twitter large-image card. The explicit duplicated fields below are intentional: they make the preview easy to inspect and maintain even though some consumers can fall back to Open Graph values.
- [ ] Do not add `twitter:site` unless the project has a real, maintained X account.

Suggested markup:

```html
<meta property="og:type" content="website">
<meta property="og:site_name" content="SaaS App Name Generator">
<meta property="og:title" content="SaaS App Name Generator | Startup Name Ideas">
<meta property="og:description" content="Generate 21 startup and SaaS app name variations from one word, then copy the list into any bulk domain search tool.">
<meta property="og:url" content="https://saasappnamegenerator.com/">
<meta property="og:image" content="https://saasappnamegenerator.com/og-image.png">
<meta property="og:image:type" content="image/png">
<meta property="og:image:width" content="1200">
<meta property="og:image:height" content="630">
<meta property="og:image:alt" content="SaaS App Name Generator interface showing generated startup name ideas">

<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="SaaS App Name Generator | Startup Name Ideas">
<meta name="twitter:description" content="Generate 21 startup and SaaS app name variations from one word, then copy the list into any bulk domain search tool.">
<meta name="twitter:image" content="https://saasappnamegenerator.com/og-image.png">
<meta name="twitter:image:alt" content="SaaS App Name Generator interface showing generated startup name ideas">
```

## Priority 3: add favicon links to `index.html`

- [ ] Add the icon links only after their files exist at the stated paths.
- [ ] Check the icon at small sizes; fine text and thin details will disappear.

Suggested markup:

```html
<link rel="icon" href="/favicon.svg" type="image/svg+xml">
<link rel="icon" href="/favicon-96x96.png" type="image/png" sizes="96x96">
<link rel="apple-touch-icon" href="/apple-touch-icon.png" sizes="180x180">
```

## Priority 4: add site-name structured data

- [x] Confirm that `SaaS App Name Generator` is the final public site name and use it consistently in the visible page, Open Graph tags, and structured data.
- [x] Add one `WebSite` JSON-LD block to the home page.
- [x] Keep all JSON-LD claims accurate and reflected by visible page content.
- [ ] Do not expect structured data to guarantee a special search result or improve ranking by itself.

Suggested markup:

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "WebSite",
  "@id": "https://saasappnamegenerator.com/#website",
  "url": "https://saasappnamegenerator.com/",
  "name": "SaaS App Name Generator",
  "description": "Generate 21 startup and SaaS app name variations from one word, then copy the list into any bulk domain search tool.",
  "inLanguage": "en"
}
</script>
```

`WebApplication` is a valid Schema.org type, but it is not needed for this first pass. Add it later only if its properties accurately describe the deployed tool; do not invent ratings, reviews, pricing, or other claims to qualify for a rich result.

## Priority 5: add crawl-discovery files

- [x] Create `sitemap.xml` in the site root with only the canonical home-page URL.
- [ ] Do not add `<priority>` or `<changefreq>`; Google ignores them.
- [ ] Add `<lastmod>` only if the date can be kept accurate when the page changes significantly.

Suggested `sitemap.xml`:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <url>
    <loc>https://saasappnamegenerator.com/</loc>
  </url>
</urlset>
```

- [x] Create `robots.txt` in the site root.
- [x] Allow normal crawling and point crawlers to the sitemap.
- [ ] Do not use `robots.txt` to keep a page out of search results; use `noindex` or access control for that job.

Suggested `robots.txt`:

```text
User-agent: *
Disallow:

Sitemap: https://saasappnamegenerator.com/sitemap.xml
```

These files are simple discovery aids, not ranking boosts. A sitemap is low-cost here but not essential for a one-page site that is already linked and crawlable.

## Priority 6: make the indexing and URL policy explicit

- [ ] Confirm the production home page returns `200 OK` at `https://saasappnamegenerator.com/`.
- [ ] Redirect HTTP and any unwanted `www`/non-`www` version to the exact canonical URL.
- [ ] Confirm the canonical URL, `og:url`, sitemap URL, and structured-data URL use the same hostname and trailing-slash form.
- [ ] Confirm the deployed page has no `noindex` directive and is not blocked by authentication or `robots.txt`.
- [ ] After `og-image.png` exists, optionally add this useful preview directive:

```html
<meta name="robots" content="max-image-preview:large">
```

Do not copy `index,follow` merely because it appears in the reference site. Indexing and following links are already the default; adding those words does not make the page more indexable.

## Priority 7: strengthen the visible on-page signal

Metadata cannot replace useful visible content.

- [x] Correct `twentyone` in the subtitle to `twenty-one`.
- [ ] Confirm the first screen plainly states what the tool does and who it is for.
- [ ] Consider adding a short, static “How it works” section if the page remains very light on crawlable explanatory copy.
- [ ] Keep the H1 unique and descriptive.
- [ ] Avoid stuffing repeated phrases such as “SaaS name generator” into headings or hidden text.
- [ ] If an FAQ is added later, write genuinely useful, visible answers first. Add FAQ structured data only when it accurately represents that visible content and current search-engine eligibility rules support the intended use.

## Priority 8: deploy and verify

- [ ] Check that these URLs return `200 OK` with the expected content types:
  - `https://saasappnamegenerator.com/`
  - `https://saasappnamegenerator.com/og-image.png`
  - `https://saasappnamegenerator.com/favicon.svg`
  - `https://saasappnamegenerator.com/favicon-96x96.png`
  - `https://saasappnamegenerator.com/apple-touch-icon.png`
  - `https://saasappnamegenerator.com/robots.txt`
  - `https://saasappnamegenerator.com/sitemap.xml`
- [ ] View the deployed page source and confirm there is exactly one title, meta description, canonical tag, and `WebSite` JSON-LD node.
- [ ] Validate the JSON-LD with the Schema.org validator and Google's Rich Results Test.
- [ ] Test the public URL in social-sharing preview/debugging tools after deployment.
- [ ] Add the domain to Google Search Console using domain-level verification if practical.
- [ ] Submit `https://saasappnamegenerator.com/sitemap.xml` in Search Console.
- [ ] Inspect the canonical home-page URL in Search Console and request indexing after the launch metadata is live.
- [ ] Recheck after Google recrawls the page; title links, descriptions, site names, and favicons are suggestions and may not appear exactly as supplied.

## Items from the reference that should not be copied automatically

- [ ] Do not add a web app manifest unless the site is intentionally being made installable as a PWA. A manifest is not general SEO metadata.
- [ ] Do not preload fonts unless the site actually self-hosts and uses those exact font files above the fold. This project currently uses system font stacks.
- [ ] Do not add analytics scripts for SEO. Analytics can help measure traffic, but it does not create search metadata and adds privacy, performance, and maintenance considerations.
- [ ] Do not copy the reference site's theme script, sponsor-selection script, avatar favicon, or analytics IDs; they are specific to that site.
- [ ] Do not add a meta-keywords tag; modern Google Search does not use it for ranking.
- [ ] Do not paste Markdown-formatted URLs such as `[https://example.com/](https://example.com/)` into HTML attributes. The attribute value must be the plain URL.

## Reference documentation

- [Google: title links](https://developers.google.com/search/docs/appearance/title-link)
- [Google: meta descriptions and snippets](https://developers.google.com/search/docs/appearance/snippet)
- [Google: canonical URLs](https://developers.google.com/search/docs/crawling-indexing/consolidate-duplicate-urls)
- [Google: favicons](https://developers.google.com/search/docs/appearance/favicon-in-search)
- [Google: site names and `WebSite` structured data](https://developers.google.com/search/docs/appearance/site-names)
- [Google: robots meta directives](https://developers.google.com/search/docs/crawling-indexing/robots-meta-tag)
- [Google: robots.txt](https://developers.google.com/search/docs/crawling-indexing/robots/intro)
- [Google: build and submit a sitemap](https://developers.google.com/search/docs/crawling-indexing/sitemaps/build-sitemap)
- [Open Graph protocol](https://ogp.me/)
- [Schema.org: `WebSite`](https://schema.org/WebSite)
- [Schema.org validator](https://validator.schema.org/)
- [Google Rich Results Test](https://search.google.com/test/rich-results)
