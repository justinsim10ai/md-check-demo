# CLAUDE.md

## What this repo is

`md-check-demo` is the **public-facing marketing / SEO surface** for **md-check**, a
technical SEO & AEO (AI answer-engine optimization) auditor. It is intentionally tiny:
a single landing page plus crawler-facing metadata. **It is not the application** — the
md-check app lives in the private `justinsim10ai/md-check` repo and runs on Fly.io
(`md-check-wgp` → https://md.weregoingplaces.xyz).

## Files

- `index.html` — the landing page. Contains a `SoftwareApplication` JSON-LD block
  (`<script type="application/ld+json">`) with the product name, description, and
  `featureList`.
- `llms.txt` — page map for AI crawlers, following the llms.txt convention md-check
  itself promotes. Lists Product / Docs / About URLs under https://md.weregoingplaces.xyz.
- `README.md` — short repo readme.

## Conventions

- **Keep the three sources of product copy in sync.** The product name, one-line
  description, and feature list appear in `index.html` (both the JSON-LD and the
  visible `<h1>`/`<p>`) and in `llms.txt`. If you change one, update the others so a
  crawler and a human see a consistent story.
- This repo dogfoods md-check's own advice (ships an `llms.txt` and rich structured
  data) — preserve that when editing.
- Validate any JSON-LD change (it must stay valid JSON inside the `<script>` tag).

## Deploying

There is currently **no automated deploy** wired to this repo (no GitHub Pages,
no Vercel/Netlify integration). The live app referenced in metadata
(https://md.weregoingplaces.xyz — the Fly app `md-check-wgp`) is hosted separately
from this repo. Don't assume a push here goes live.

## Related

- App repo: `justinsim10ai/md-check` (the actual auditor; Node + Fly.io). See its
  `DEPLOY.md` for product deployment.
- The `md-check/feat-*` PRs into this repo are opened by the md-check GitHub App.
