# L. Merrick / Groundwood catalog site

Static promo site for the finished digital catalog. No build step. No tracker. No stock photos or testimonials.

## Files

- `index.html` — catalog
- `about.html` — author / method
- `contact.html` — mailto placeholder (`author@example.com`)
- `styles.css`
- `covers/` — copies of finished covers from `/workspace/books/_covers/final/`

Titles without a final cover (Iran–Israel–US timeline, Kanye West, Fifty Years of U.S. Immigration Policy) use a typographic placeholder block, not a downloaded image.

Amazon buttons point at `#amazon-TITLE` until ASINs exist. Kobo, Apple Books, and Google Play are labeled Coming soon.

List prices on the site: **$3.99** for *Trump: The Public Record, 2015–2026* and *Fifty Years of U.S. Immigration Policy*; **$2.99** for the other eight titles.

## Host on GitHub Pages (free)

1. Create a GitHub repository (for example `groundwood-catalog` or `username.github.io`).
2. Put the contents of this `site/` folder at the **root** of the default branch (`index.html` must be at `/`, not nested).
   ```bash
   cd site
   git init
   git add .
   git commit -m "Add Groundwood catalog site"
   git branch -M main
   git remote add origin https://github.com/USER/REPO.git
   git push -u origin main
   ```
3. On GitHub: **Settings → Pages → Build and deployment**.
   - Source: **Deploy from a branch**
   - Branch: `main` / `/ (root)`
4. After a minute, the site is at `https://USER.github.io/REPO/` (or `https://USER.github.io/` if the repo is named `USER.github.io`).
5. Custom domain (optional): add a `CNAME` file containing your domain, then set DNS as GitHub instructs.

Project-site URLs need relative links (already used: `styles.css`, `covers/…`, `about.html`). Do not use a leading `/` if the site is not at the domain root.

## Host on Netlify (free)

1. Drag this `site/` folder onto [https://app.netlify.com/drop](https://app.netlify.com/drop), **or**
2. Connect the GitHub repo in Netlify:
   - Build command: *(leave empty)*
   - Publish directory: `.` if the repo is only this folder, or `site` if this folder lives inside a larger repo.
3. Netlify assigns `https://something.netlify.app`. Custom domains are free on the starter plan.

No environment variables or serverless functions are required.

## After ASINs land

Replace each `href="#amazon-…"` on `index.html` with the live Amazon product URL. Then add Kobo / Apple / Google URLs and change those spans from “Coming soon” to real links.
