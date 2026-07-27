# SEO Setup — joshuadriver.com

This file covers the browser-only steps that can't be automated from the repo.
Everything else (JSON-LD, sitemap, llms.txt, OG image, icons, header rules) is
already in the codebase and deploys automatically via Netlify.

Do this part in a browser (Josh + Cowork Claude).

## Status

- ✅ **GA4 tag** — `G-JVGDFEN30R` installed in `<head>` and live.
- ✅ **GSC verification token** — `5AXtG8329Bk-FFurucDGdIftJ3rOCvsAVW8Vo6W3zi0`
  installed as a live `<meta name="google-site-verification">` tag.
- ⏳ **Remaining (browser):** click Verify in GSC, submit the sitemap, import to Bing.

---

## Google Search Console — verify + submit sitemap

The property token is already live in the deployed HTML, so steps 1–3 are done.
Finish in the browser:

1. ✅ Property added: `https://joshuadriver.com/` (URL prefix).
2. ✅ HTML-tag verification token pasted + deployed
   (`content="5AXtG8329Bk-FFurucDGdIftJ3rOCvsAVW8Vo6W3zi0"`).
3. ✅ Deployed live (confirm any time via `view-source:https://joshuadriver.com/`).
4. **Click Verify** in Search Console — should confirm within a minute.
5. **Submit the sitemap.** GSC → *Sitemaps* → enter `sitemap.xml` → *Submit*.
   Confirm it reports "Success" (may take a few minutes to a day to process).

## Bing Webmaster Tools — via GSC import (fastest)

6. Go to https://www.bing.com/webmasters → sign in → *Import* → **Import from
   Google Search Console** → authorize → select `joshuadriver.com`. This copies
   verification and the sitemap automatically — no separate meta tag needed.
   (If import fails, use Bing's own HTML-tag method with the same placeholder
   line in `index.html`, then re-submit `sitemap.xml`.)

---

## Post-verification quick checks

- **Rich Results Test:** https://search.google.com/test/rich-results — paste
  `https://joshuadriver.com/` → confirm **Person** and **ProfessionalService**
  parse with no errors.
- **Schema validator:** https://validator.schema.org/ — same URL, confirm the
  `@graph` (Person + ProfessionalService) is valid.
- **Social preview:** https://www.opengraph.xyz/ — paste the URL → confirm the
  1200×630 OG image renders.
- **URL Inspection** in GSC → *Request indexing* for the homepage to speed up
  first crawl.

---

## Backlink checklist (verify only — no outreach this session)

These are the "owed" links that point authority back to joshuadriver.com.
Check each is live and uses `https://joshuadriver.com/`:

- [x] **LinkedIn profile** — contact-info website link added **Jul 27 ✅**.
      Verify it points to `https://joshuadriver.com/` (not a redirect).
- [ ] **Workplace-giving directory** — confirm Josh's profile / Selflessly
      listing links back to joshuadriver.com.
- [ ] **TechPoint** — founder interview publishing in **August**; confirm the
      published piece links to joshuadriver.com once live.
- [ ] **Selflessly team/about page** — confirm the founder bio on selflessly.io
      links to joshuadriver.com (reciprocal of the `sameAs` link).
- [ ] **IBJ article** — already cited in our `sameAs`; no backlink owed, but
      worth confirming the article is still reachable.

---

## What's already done in the repo (no action needed)

- JSON-LD `@graph`: **Person** (Joshua Driver, Founder & CEO of Selflessly,
  `sameAs` → LinkedIn, selflessly.io, IBJ) + **ProfessionalService** (advisory +
  three speaking topics as `makesOffer`).
- `sitemap.xml`: homepage + section anchors, `lastmod` set, referenced by
  `robots.txt`.
- `netlify.toml`: pins `sitemap.xml` → `application/xml`, `llms.txt` /
  `robots.txt` → `text/plain`, long cache on assets.
- `llms.txt`: plain-text summary for AI answer engines (who Josh is, what
  Selflessly is, the three talks, contact = site form).
- OG image `assets/og-image.jpg` (1200×630) + `assets/apple-touch-icon.png`
  (180×180); SVG favicon inline.

### Bio guardrails (keep consistent everywhere)
- Always "**founder and CEO**" of Selflessly. **Never** "solo founder."
- Selflessly **launched in 2020**.
