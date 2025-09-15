# Akash Gupta — Data Analytics Portfolio (Hugo + Bookshop)

This is my personal portfolio built with Hugo (extended) and CloudCannon Bookshop components. It showcases projects, blog posts, and a short About section.

Live site: https://itsaakashgupta.github.io/

## Highlights

- Projects grid with manual ordering using `weight` (higher appears first)
- About section on the homepage renders rich HTML from the About page
- Excel workbook embedded via Microsoft Office Online Viewer (public URL)
- GitHub Pages deployment via a workflow (`.github/workflows/hugo.yml`)
- Goldmark configured to allow raw HTML in Markdown

## Getting started

Prerequisites:
- Hugo extended (v0.148+ recommended)
- Node 18+ only if you want to use the optional Bookshop component browser

Local development:

```bash
# serve with drafts
hugo server -D
```

Build for production:

```bash
hugo --minify
```

## Deployment (GitHub Pages)

Deployment is automated via `.github/workflows/hugo.yml`. Pushing to `main` builds the site and publishes the `public/` output to the `gh-pages` branch.

## Project ordering (featured first)

Projects are now sorted by `weight` (descending). Add a `weight` field to a project’s front matter to pin it near the top:


## Rich About section on the homepage

The homepage “About me” section pulls HTML from the About page’s `content_blocks.content.content_html` and renders it safely, keeping headings and links.

## Notable configuration

- Allow raw HTML in Markdown (required for iframes):

```toml path=null start=null
ignoreLogs = ['warning-goldmark-raw-html']

[markup]
  [markup.goldmark]
    [markup.goldmark.renderer]
      unsafe = true
```

File: `config.toml`

## Repository layout (short)

- `content/` — pages, posts, and projects
- `component-library/` — Bookshop components (HTML, SCSS, metadata)
- `layouts/` — Hugo templates/partials
- `assets/` — JS/CSS assets processed by Hugo Pipes
- `static/` — files served as-is (e.g., `/uploads/...`)
- `data/` — site settings (navigation, general settings)
- `resources/` — generated assets from Hugo (safe to regenerate)
- `.github/workflows/hugo.yml` — GitHub Pages deployment workflow

## Changes made in this repository

- Enabled HTML rendering in Markdown via Goldmark in `config.toml
- Homepage About preview renders HTML (`safeHTML`) instead of plain text
- Manual project ordering added (sort by `Weight` desc); SmartDash has `weight: 100`


## License

MIT (see `LICENSE`).
