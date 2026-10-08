# SSI@ICLR2027 — Scientific Super Intelligence Workshop Website

Static, single-page website for the **Scientific Super Intelligence** workshop proposed to ICLR 2027.
Its layout follows the [AIMS@ICLR2026](https://alimama-tech.github.io/aims-2026/) workshop site
(Tailwind CSS via CDN, no build step).

## Structure

```
index.html                  # the whole site (all sections)
images/Basic/logo.svg       # logo + favicon
images/Basic/hero.svg       # header background
images/Basic/avatar-placeholder.svg
images/Speakers/            # speaker photos (square, ≥ 300×300 px recommended)
images/Organizers/          # organizer photos
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
| Organizers | `<section id="organization">`, one card per person (max. 8 for ICLR 2027) |
| Schedule | `<section id="program">`: currently a "To Be Announced" placeholder; a full-day table template is kept in an HTML comment right below it |
| Accepted papers / PC | `<section id="accepted-papers">`, `<section id="program-committee">` |
| Contact email | search for `ssi.iclr2027@example.com` |

Photos: put the file in `images/Speakers/` or `images/Organizers/` and point the card's `<img src>` to it.

## Deploy on GitHub Pages

1. Push this folder to a GitHub repository (e.g. `ssi-2027`).
2. Repository **Settings → Pages → Build and deployment**: *Deploy from a branch*, branch `main`, folder `/ (root)`.
3. The site will be available at `https://<github-user>.github.io/<repo>/` within a minute or two.
