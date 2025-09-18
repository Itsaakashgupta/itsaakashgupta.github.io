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

## 🔄 Comparison with Original Template

Here’s what I changed compared to the original **Vonge theme**:

### 1. 🖼️ Homepage Layout
- **Original:** Showcases creative works/photography grid.  
- **My Version:** Replaced with a **Project Showcase** highlighting data analytics dashboards and AI projects.  

### 2. 📊 Project Section
- **Original:** Static gallery-style showcase with images.  
- **My Version:**  
  - Added **live project previews** (SmartDash, Excel Dashboards, etc.).  
  - Introduced **tech-stack badges** (Python, Pandas, Streamlit, Excel, Pivot Tables).  
  - Added **interactive buttons**: links to **Demo, GitHub, Hugging Face**.  
  - Each project has a **short description + screenshot** for clarity.  

### 3. 📝 Content Customization
- Updated all **text content** to reflect:
  - My **data analytics & AI focus**.  
  - Professional tone suitable for portfolio showcase.  
  - Replaced placeholder content with **real project details**.  

### 4. 🎨 Visual Design Tweaks
- Customized **color accents** and **buttons** (red/blue/black) to highlight actions.  
- Reorganized sections to keep **projects at the forefront**.  
- Adjusted **image dimensions** for a clean 16:9 look (LinkedIn friendly).  

### 5. 🔗 Navigation & Links
- Added external links to:  
  - **Streamlit apps**  
  - **Hugging Face Spaces**  
  - **GitHub repositories**  

### 6. 🚀 Deployment
- Hosted via **GitHub Pages** for easy sharing.


## License

MIT (see `LICENSE`).
