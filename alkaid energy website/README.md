# Phalanx ARC — One-Page Site

Static site for Phalanx ARC™ (Alkaid Energy Technologies, LLC) — no build step, no dependencies.

## Files
- `index.html` — the page (~1.2MB)
- `phalanx-arc-overview.mp4` — the narrated product overview video (2:36, ~4.4MB), loaded only when a visitor clicks "Watch the Video"
- `favicon.png`, `apple-touch-icon.png` — site icons
- `og-image.jpg` — the image shown when the page is shared on social media / iMessage / Slack
- `robots.txt`, `sitemap.xml` — SEO crawl files

**Keep all of these files together in the same folder when you deploy** — index.html references the others by relative path (not inline), which is what keeps the page itself small and fast to load.

## Deploy

Any static host works. Two easy options:

**Netlify (connected to this repo, auto-deploys on push)**
1. Push this repo to GitHub.
2. In Netlify: "Add new site" → "Import an existing project" → pick this repo.
3. Build command: leave blank. Publish directory: `/` (root).
4. Deploy. Then Site settings → Domain management → add your custom domain (alkaidenergy.com) and follow the DNS instructions.

**Any other static host** (Vercel, Cloudflare Pages, GitHub Pages)
Point it at this repo's root — there's nothing to build, it just serves the files as-is.

## Before this goes live — two things only you can finish

1. **Google Analytics 4** — `index.html` has a GA4 tag already wired in near the top of `<head>`, but it's pointed at a placeholder ID (`G-XXXXXXXXXX`) in two places. Create a GA4 property at analytics.google.com, grab your real Measurement ID, and replace both instances of `G-XXXXXXXXXX` with it.
2. **Business address** — if you want a `LocalBusiness` listing (for Google Business Profile / local map pack), the structured data in `<head>` can include a mailing address once you give me one — right now it only declares the company as an `Organization` (no address).

## Notes
- The "Request Technical Data" popup form only saves submissions to a database when this page is hosted as a Claude Artifact. On a normal static host (Netlify, GitHub Pages, etc.) it automatically falls back to opening a pre-filled email to Roy instead — this still works fine, it just won't keep a saved list of leads.
- The "Watch the Video" button opens the narrated Phalanx ARC overview video inline.
