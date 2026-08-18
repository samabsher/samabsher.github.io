# samabsher.com

Personal academic website, built with [Quarto](https://quarto.org).

## How it works

- Pages are `.qmd` files (Markdown + raw HTML). Edit them in any text editor.
- `_quarto.yml` controls the navbar, theme, and output location.
- `quarto render` builds the site into `docs/`, which GitHub Pages serves.
- `quarto preview` opens a live local preview that rebuilds on save.

## Everyday workflow

```
cd D:\repos\samabsher.com
quarto preview          # look at changes locally
quarto render           # build docs/ for publishing
git add -A
git commit -m "Describe the change"
git push                # publishes the site
```

## Layout

| Path | What it is |
|---|---|
| `index.qmd` | Home page |
| `research.qmd` | All papers and reports |
| `research/fences-and-fortunes/index.qmd` | Paper companion page (template for future ones) |
| `data.qmd` | Data & replication |
| `cv.qmd` | CV page (`files/absher_cv.pdf` is the download) |
| `styles/theme.scss` | Site-wide look (colors, fonts) |
| `styles/paper.css` | Companion-page components (hero, stats, charts, dropdowns) |

## Adding a new paper page

Copy `research/fences-and-fortunes/` to `research/<new-slug>/`, edit the
`index.qmd`, and add a card linking to it in `research.qmd`. The CSS components
(`pp-hero`, `pp-stats`, `pp-section`, `pp-details`, …) are reusable.

## TODOs before/after launch

- Replace `#` placeholder links (SSRN, replication repos, journal DOIs,
  Google Scholar, GitHub username) — search the repo for `TODO`.
- Add a headshot to `index.qmd` if desired.
- See `DEPLOY.md` for GitHub Pages + custom domain steps.
