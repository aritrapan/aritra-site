# aritra.ai — Quarto site

## Before first build
1. Delete the placeholder files in `img/` and copy your real `img/` folder from cPanel
   (`AP.png`, `favicon.png`, `Project 1.png`, `Project 2.png`, the nine workshop photos).
   File names must match exactly.
2. Edit `teaching.qmd` → "Earlier courses" once you have the courses table export.
3. Blog: `posts/2026-09-welcome/` is a draft (not published). Copy the folder, rename,
   set `draft: false`, write. One folder per post.

## Local preview (optional)
Install Quarto (https://quarto.org/docs/get-started/), then in this folder: `quarto preview`.

## Deploy to GitHub Pages
1. Create a new GitHub repository (public), e.g. `aritra-ai`. Push this folder to branch `main`.
2. Repository → Settings → Pages → Source: **GitHub Actions**. The workflow in
   `.github/workflows/publish.yml` renders and deploys on every push.
3. Settings → Pages → Custom domain: `aritra.ai` → Save. (The `CNAME` file is already in the project.)
4. GoDaddy → DNS for aritra.ai:
   - Delete the existing `A` record for `@` (currently pointing at GoDaddy hosting).
   - Add four `A` records, name `@`:
     185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153
   - Add a `CNAME` record, name `www`, value `<your-github-username>.github.io`.
5. Wait 15–60 min, then in GitHub Pages settings tick **Enforce HTTPS**.
6. Google Search Console → add property `aritra.ai` → submit `https://aritra.ai/sitemap.xml`.

## Editing
Everything is Markdown. Publications: `research.qmd` (visible list) and `publications.bib` (download).
Latest updates: table in `index.qmd`. Push to `main` and the site rebuilds in ~2 minutes.
