# SSI@ICLR2027 — 1st Workshop on Scientific Superintelligence

Static, single-page website for the **1st Workshop on Scientific Superintelligence**, proposed to ICLR 2027.
Its layout follows the [AIMS@ICLR2026](https://alimama-tech.github.io/aims-2026/) workshop site
(Tailwind CSS via CDN, no build step).

## Structure

```
index.html                  # the whole site (all sections)
images/Basic/logo.svg       # logo + favicon (PNG versions: favicon-32.png, apple-touch-icon.png)
images/Basic/og-image.png   # 1200×630 link-preview image
images/Basic/hero.svg       # header background
images/Basic/avatar-placeholder.svg
images/Speakers/            # speaker photos (square, ≥ 300×300 px recommended)
images/Organizers/          # organizer photos
images/Panelists/           # panelist photos
.nojekyll                   # serve files as-is on GitHub Pages
```

## Preview locally

```bash
python3 -m http.server 8027
```

Then open <http://localhost:8027>.

## Common edits (all in `index.html`)

| What | Where |
| --- | --- |
| News items | `<section id="news">`, newest first |
| Key dates / submission link | `<section id="call">` → *Key Dates*, *Submission Site* |
| Speakers | `<section id="speaker">`, one card per person (template in the comment) |
| Panelists | `<section id="panelists">`, one card per person (template in the comment) |
| Organizers | `<section id="organization">`, one card per person (max. 8 for ICLR 2027, advisors and student volunteers included) |
| Schedule | `<section id="program">`: currently a "To Be Announced" placeholder; a full-day table template is kept in an HTML comment right below it |
| Accepted papers / PC | `<section id="accepted-papers">`, `<section id="program-committee">` |
| Contact email | search for `ssi.iclr2027@example.com` |

Photos: put the file in `images/Speakers/`, `images/Panelists/` or `images/Organizers/` and point the card's `<img src>` to it.
GitHub Pages paths are case-sensitive, so prefer lowercase file names such as `jane-doe.jpg`.

## Deploy on GitHub Pages

The site is hosted from [`AI4SSI/ssi-2027`](https://github.com/AI4SSI/ssi-2027) at
<https://ai4ssi.github.io/ssi-2027/> (**Settings → Pages**: *Deploy from a branch*, `main`, `/ (root)`).
Every push to `main` is live within a minute or two.

If the repository is renamed or moved, update the absolute URLs in `index.html`
(`og:url`, `og:image`, `canonical`). The URL path is case-sensitive and must match the repository name.
