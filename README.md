# insights.accomrd.com - master site source (Netlify project legendary-ganache-d60bd8)

This folder is the COMPLETE site. Netlify Drop replaces the whole site on every deploy, so every weekly run must:
1. Start from THIS folder (never from an old zip).
2. Add the new article pair: blog/<slug>.html (EN) and blog/es/<slug-es>.html (ES), copying structure from blog/construction-labor-costs-dominican-republic-2026.html (tools/build_article_2026-10-29_labor.py shows how it was generated).
3. Run: python3 tools/regen_index_sitemap.py   (rebuilds blog index cards, CollectionPage schema, sitemap with hreflang)
4. Rules: no em/en dashes; no B-45 (no villa-hacienda images); images only from delivered projects; Park View only "in construction"; 16 months as a commitment only.
5. Zip the folder (exclude tools/ and README.md is harmless): cd insights-site && zip -qr ../accom-insights-site-YYYY-MM-DD.zip . -x "tools/*" && deploy to https://app.netlify.com/projects/legendary-ganache-d60bd8/deploys
6. Verify the new URLs load on insights.accomrd.com, then update content-calendar.md.

Missing articles that were written in earlier runs but never preserved (rewrite as needed): cost per m2 by zone (wk2), construction code (wk3), Puntacana Resort lot deadline (wk4), CONFOTUR self-build (wk5c).

## Deploy status notes (2026-11-03)
- Working path: Claude in Chrome drives Netlify Drop. Needs Chrome open with the extension, signed in to Netlify, desktop app online. Stage the zip with device_stage_files, then file_upload from /mnt/user-data/uploads/.
- Blocked: Netlify MCP deploy-site (needs npx to reach netlify-mcp.netlify.app, 403 from cloud and no route from the device VM); GitHub (no linked account; gh token invalid). Netlify site id: 5ab32715-5c57-4101-95e8-6424e0111ddf.
- Fix for fully hands-off weekly deploys: connect GitHub at claude.ai/customize/connectors, create a repo for this folder, link it in Netlify (Project configuration > Build & deploy > Link repository).
