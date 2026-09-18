# Health Decisions — website

**This folder is the GitHub repository.** Upload everything in it, and nothing from outside it.
The WordPress files live one level up in `../wordpress/`.

Static site for the Health Decisions Lab at Towson University.
Published with GitHub Pages at **https://farzinahmadi.github.io/healthdecisions/** and linked
from **https://wp.towson.edu/healthdecisions/**.

No build step. Plain HTML and one CSS file. Edit a file, commit, and it is live in about a minute.

## Files

| File | What it is |
|---|---|
| `index.html` | Home page — what the lab does, and cards for the two live resources |
| `gbr-tracker.html` | Maryland GBR Tracker, embedded in an iframe with a full-screen link |
| `measles.html` | U.S. Measles Tracker — description and links out to the Johns Hopkins page |
| `404.html` | Not-found page |
| `styles.css` | All styling |
| `.nojekyll` | Tells GitHub Pages to serve files as-is rather than running Jekyll |
| `WORDPRESS-SETUP.md` | Step-by-step guide for the wp.towson.edu side (not published; reference only) |

## One-time setup

1. On GitHub, create a **new public repository named `healthdecisions`**.
   The name matters — it becomes the URL path.
2. Upload every file in this folder to the repository root, **including the hidden `.nojekyll`**.
   Drag-and-drop in the browser skips dotfiles, so if you use the web uploader, create
   `.nojekyll` afterwards with *Add file → Create new file*, name it `.nojekyll`, leave it empty,
   and commit.
3. Go to **Settings → Pages**.
4. Under *Build and deployment*, set **Source: Deploy from a branch**, **Branch: `main`**,
   **Folder: `/ (root)`**. Save.
5. Wait about a minute, then open **https://farzinahmadi.github.io/healthdecisions/**.

## Linking it from WordPress

Full instructions are in **`WORDPRESS-SETUP.md`**. In short: keep the page at
`wp.towson.edu/healthdecisions/` short — a paragraph on what the lab does and
a clear link out. The WordPress page is the Towson-badged front door; this site is where the
interactive work lives. Duplicating content between them is the main way this gets stale.

## Updating

- **Text changes** — edit the relevant `.html` file directly on GitHub and commit.
- **The GBR tracker** — nothing to do here. It lives in the `maryland-gbr-tracker` repository and
  this site embeds it, so it updates on its own.
- **Adding a page** — copy an existing HTML file, change the content, and add a `<li>` to the
  `<nav>` block in *every* page so the navigation stays consistent.

## Project thumbnails

The two cards on `index.html` show `img/gbr-card.jpg` and `img/measles-card.jpg`. Both are in
place (1600x900, padded to 16:9 on white so no part of either map is cropped).

**To replace one:** save a new screenshot over the same filename, at 1600x900. If the new capture
is not 16:9, pad it rather than cropping, or the edges of the map will be cut off. The card crops
from the top, so keep anything important in the upper portion.

Sources if you want to recapture:
- GBR: https://farzinahmadi.github.io/maryland-gbr-tracker/
- Measles: https://publichealth.jhu.edu/ivac/resources/us-measles-tracker

**The measles image** is Panel A of Figure 2 from the 2025 *JAMA* research letter — your own
published figure, extracted from the source PowerPoint, rather than a screenshot of the JHU
dashboard. It is described on `measles.html`. Worth a quick check of JAMA'''s author-reuse terms
before the site goes public; reuse of your own figure on an institutional page with citation is
normally permitted, but the journal holds the published version.

## Adding your photo

The **Who runs this** block on `index.html` works without a photo. To add one:

1. Save a square headshot as `farzin.jpg` in this folder (at least 400×400; it renders at 112px).
2. In `index.html`, find the commented `<img class="lead-photo" …>` line and uncomment it.

## Notes

- The iframe on `gbr-tracker.html` points at `https://farzinahmadi.github.io/maryland-gbr-tracker/`.
  If that repository is ever renamed or moved to a custom domain, update the three links in that
  file and the one on `index.html`.
- `404.html` uses absolute paths (`/healthdecisions/…`) because GitHub serves it from any depth.
  If the repository is renamed, those four paths need to change.
- Everything is plain HTML — no dependencies, nothing to install, nothing that can break on a
  version bump.
