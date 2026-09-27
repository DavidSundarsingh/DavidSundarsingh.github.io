# davidsundarsingh.github.io

Personal academic website of David Smith Sundarsingh (Ph.D. student, Washington University in St. Louis).

Live at **https://davidsundarsingh.github.io/**

The site is plain static HTML — no build step, no framework, no dependencies beyond a Google Fonts stylesheet.

```
.
├── index.html          # the whole site: landing animation + homepage
├── 404.html            # shown by GitHub Pages for unknown URLs
├── assets/
│   ├── profile.jpg     # portrait (440×440)
│   └── favicon.svg     # browser-tab icon
├── robots.txt
├── sitemap.xml
└── .nojekyll           # tells GitHub Pages to serve files as-is
```

## Deploying on GitHub Pages

1. **Create the repository.** On GitHub, click **New repository** and name it exactly
   `DavidSundarsingh.github.io` (it must match your username). Make it **Public**. Don't add a README.

2. **Upload the files.** Either:

   - **Web upload:** open the empty repo → *uploading an existing file* → drag in *everything inside*
     this folder, including the `assets` folder → **Commit changes**.
     (`.nojekyll` is hidden on macOS — press `Cmd + Shift + .` in Finder to show it. The site works
     without it, but it's recommended.)
   - **Command line:**
     ```bash
     cd DavidSundarsingh.github.io
     git init
     git add .
     git commit -m "Initial site"
     git branch -M main
     git remote add origin https://github.com/DavidSundarsingh/DavidSundarsingh.github.io.git
     git push -u origin main
     ```

3. **Turn on Pages.** In the repo: **Settings → Pages → Build and deployment** → Source:
   *Deploy from a branch* → Branch: `main`, folder: `/ (root)` → **Save**.

4. Wait a minute or two, then visit **https://davidsundarsingh.github.io/**.
   The deployment status appears under the repo's **Actions** tab.

## Updating the site

Edit `index.html`, then commit and push (or use the pencil icon on GitHub to edit in the browser).
Changes go live within about a minute; hard-refresh (`Cmd + Shift + R`) if you still see the old version.

Common edits, all in `index.html`:

| What | Where to look |
| --- | --- |
| Bio | the `<h2>About</h2>` section |
| Contact links | `<nav class="links">` |
| Project entries, descriptions, links | `<ol class="bib">` — one `<li>` per project |
| Links for the ongoing project | inside `<li id="proj-3">`, copy a `bib-links` block from project 1 |
| Tasks in the animation | the `<select id="task">` options **and** the matching `TASKS` object in the script |
| Portrait | replace `assets/profile.jpg` (square image, ~440 px) |

## Optional: custom domain

To serve the site from your own domain, add it under **Settings → Pages → Custom domain**, then create
the DNS records GitHub shows you. Update the `canonical`, `og:url` and `og:image` URLs in `index.html`,
and the URLs in `sitemap.xml` and `robots.txt`, to the new domain.

## Optional: Google Search

To speed up indexing, add the site in [Google Search Console](https://search.google.com/search-console)
and submit `https://davidsundarsingh.github.io/sitemap.xml`.
