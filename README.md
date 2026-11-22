# Lazy Intercom - info site

Static site for https://intercom.kalmarium.com/ (GitHub Pages, repo `gaborkalmar83/lazy-intercom-info`). No build step, no scripts, no external fonts. Each HTML page has its CSS inline.

## Files

| File | Purpose |
|------|---------|
| `index.html` | SEO landing page. One H1, FAQ section that matches the FAQPage JSON-LD, MobileApplication JSON-LD, OG/Twitter tags, canonical |
| `privacy-policy.html` | Privacy policy (use this URL in Play Console, "Privacy policy") |
| `404.html` | Not-found page (noindex, absolute links) |
| `robots.txt`, `sitemap.xml` | Crawling. Add every new page to the sitemap |
| `CNAME` | `intercom.kalmarium.com` for GitHub Pages |
| `app-ads.txt` | AdMob seller line. Must be served at `https://intercom.kalmarium.com/app-ads.txt` |

## Images still to add (exact names under `img/`)

| Path | Size | Notes |
|------|------|-------|
| `img/icon-512.png` | 512x512 | From `lazy-intercom/art/images/icon.png`. Also used as favicon and apple-touch-icon |
| `img/hero.webp` | 1536x1024 | From `hero.png`. Keep under ~150 KB (LCP image) |
| `img/og-image.jpg` | 1200x630 | Social card. Needs a crop/compose, the hero is 3:2 |
| `img/shot-1.png` ... `shot-8.png` | 1080x1920 | Phone screenshots in the order of `store/listing-en-GB.md` |
| `img/speakers.webp` | 1024x1024 | From `speakers.png` |
| `img/pairing.webp` | 1024x1024 | From `pairing.png` |

Width and height attributes in the HTML already match these sizes, so layout will not jump once the images arrive. Shots are displayed at 210 px wide, so consider also shipping smaller copies if page weight matters.

Until the images exist, pages still render but show broken-image icons. Do not publish before they are added.

## Before going live

1. Create the repo, push, enable Pages from the `main` branch root.
2. DNS: add a CNAME record `intercom` -> `gaborkalmar83.github.io` (same pattern as the other Kalmarium app subdomains), then tick "Enforce HTTPS" in the Pages settings.
3. Check `https://intercom.kalmarium.com/app-ads.txt` returns the single line as plain text.
4. The "Get it on Google Play" button is a CSS badge-style button, not Google's artwork. Google's brand rules prefer the official badge: generate it at the Google Play badge generator and swap it in if you want the official look. Note the credit line in the footer.
5. Validate: Rich Results Test (FAQPage; the MobileApplication block has no rating on purpose, do not add ratings until real ones exist), PageSpeed Insights (mobile), a mobile viewport check.
6. Search Console: add the domain property, submit `sitemap.xml`, request indexing of `/`.
7. After the Play listing is live, check the store URL in the badge, JSON-LD `downloadUrl` and `installUrl` all resolve.

## Editing notes

- Keep FAQ text in `index.html` and in the JSON-LD identical. Google requires FAQ markup to match visible content.
- Palette: coral #E8553A, deep teal #0F5257, mustard #F2B134, cream #FFF6E9, charcoal #23302F. No purple anywhere.
- The privacy policy must stay true to the app. Update it and the "Last updated" date whenever the app adds an SDK, a permission or a data flow.
- Illustrations are AI-generated (Azure gpt-image). The footer and privacy policy say so. Keep that.
