# L. Merrick Books — GitHub Pages storefront

Static sales catalog for the finished digital list (author: **L. Merrick**). No build step, no tracker, no stock-photo theft, no testimonials, no fake reviews.

## Live URL

Canonical host is the project Pages site:

`https://basebillionslotto.github.io/lmerrick-books/`

Every page, stylesheet, and cover uses the `/lmerrick-books/` prefix so assets resolve on a project site (not `username.github.io` root). Do not point a custom domain at this repo until you own the name and are ready to add a `CNAME` plus DNS. Custom domain is **optional later**.

There is no `CNAME` file in this folder.

## Deploy to GitHub Pages

1. Put the **contents** of this folder (`index.html`, `books/`, `covers/`, `styles.css`, `.nojekyll`, etc.) at the root of the `basebillionslotto/lmerrick-books` repository — not nested under `site/`.
2. Repo **Settings → Pages**: Source = Deploy from a branch, Branch = `main`, folder = `/ (root)`.
3. Wait for the Pages build. Open `https://basebillionslotto.github.io/lmerrick-books/`.
4. `.nojekyll` is present so GitHub does not process the files through Jekyll.

If the repo already exists, copy/overwrite these files, commit, and push `main`.

## Optional custom domain (later)

Only after you own a domain:

1. Add a `CNAME` file with the hostname (one line).
2. In Pages settings, set Custom domain and complete GitHub’s DNS instructions.
3. Rewrite canonical / Open Graph / `sitemap.xml` / `robots.txt` hosts from `https://basebillionslotto.github.io/lmerrick-books` to `https://your-domain` (and drop the `/lmerrick-books/` prefix on asset links if the site then lives at domain root).

Until then, leave the GitHub Pages URLs as-is.

## Sales rules

- Primary CTA on each card is **Details** (book page). Amazon is labeled **Coming soon on Amazon** and uses `href="#amazon-<slug>"` until a real ASIN exists in that book folder.
- No invented ASINs. No ISBN in JSON-LD unless a file records an assigned one.
- JSON-LD is `Book` / `ItemList` only — no reviews, ratings, or fake stars.

When an ASIN lands: replace `#amazon-<slug>` with `https://www.amazon.com/dp/ASIN` on the catalog card and the book page, change the button text to **Buy on Amazon**, and record the ASIN in that title’s `kdp-metadata.md`.

## Files

- `index.html` — catalog (56 cards)
- `books/<slug>.html` — one page per manuscript
- `about.html`, `contact.html`, `privacy.html`, `404.html`
- `styles.css`
- `covers/<slug>.jpg`
- `sitemap.xml`, `robots.txt`, `.nojekyll`
