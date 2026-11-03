# insights.accomrd.com - master site source (Netlify project legendary-ganache-d60bd8)

This repo is the COMPLETE site. Netlify deploys every commit to `main` automatically (no build command, publish dir = repo root, about 30 seconds). Cloud routines commit through the GitHub connector; no Chrome or zip upload is needed.

Weekly procedure:
1. Add the new article pair: blog/<slug>.html (EN) and blog/es/<slug-es>.html (ES), copying structure from blog/construction-labor-costs-dominican-republic-2026.html.
2. Update blog/index.html (new card + CollectionPage hasPart) and sitemap.xml (EN + ES entries with xhtml:link alternates). tools/regen_index_sitemap.py on the device master folder does this; in cloud runs edit those two files directly.
3. Push all changed files in ONE commit to main (mcp__github__push_files). Add any new image to assets/.
4. Rules: no em/en dashes; no B-45 (no villa-hacienda images); images only from delivered projects; Park View only "in construction"; 16 months as a commitment only.
5. Wait about 60 seconds, verify the new URLs load on insights.accomrd.com, then update content-calendar.md.

Missing articles that were written in earlier runs but never preserved (rewrite as needed): cost per m2 by zone (wk2), construction code (wk3), Puntacana Resort lot deadline (wk4), CONFOTUR self-build (wk5c).

## Deploy status notes (2026-11-03)
- Netlify site id: 5ab32715-5c57-4101-95e8-6424e0111ddf. Continuous deployment from this repo, branch main.
- GitHub connector (Claude Github MCP Connector) is installed on this repo with read/write access.
- Repo made public 2026-11-03 because Netlify's free plan blocks builds of private-repo commits from unrecognized contributors (the connector commits as pierina1991, Netlify is linked to pierinamerinoa). Never put secrets in this repo.
