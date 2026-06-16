# Ishan Roy Portfolio — Claude Code Context

## Site Overview
Jekyll static site portfolio for Ishan Roy, a Cornell MAE student.
- **Live URL:** https://cornell-mae-ug.github.io/fa25-portfolio-ishanr254/
- **Repo baseurl:** `/Ishan-Roy-Portfolio` (used in all asset paths)
- **Host:** GitHub Pages (via `github-pages` gem, Jekyll 3.10.0)
- **Markdown:** kramdown with GFM input

---

## Directory Structure

```
.
├── CLAUDE.md                    # This file
├── _config.yml                  # Site config, collections, plugins
├── Gemfile / Gemfile.lock       # Ruby dependencies
│
├── _layouts/
│   ├── default.html             # Base layout: sidebar + main content area
│   ├── page.html                # Standard content page
│   ├── project.html             # Individual project page
│   └── report.html              # Individual report page (renders PDF/slides iframe)
│
├── _includes/
│   ├── navigation.html          # Sidebar nav with active-state logic
│   ├── header.html              # (legacy, not used in default.html)
│   └── footer.html              # Footer with copyright
│
├── _sass/
│   └── custom.scss              # ALL custom styles — single source of truth
│
├── _projects/                   # Collection: one .md per project
├── _reports/                    # Collection: one .md per report
│
├── assets/
│   ├── images/                  # Photos, renders, headshots
│   ├── icons/                   # Small icons used in report/project cards
│   ├── files/                   # PDFs and downloadable files
│   └── css/style.css            # Compiled output (do not edit directly)
│
├── aboutme.md                   # Homepage (permalink: /)
├── projects.md                  # Projects gallery page (permalink: /projects/)
├── reports.md                   # Reports gallery page (permalink: /reports/)
├── cv.md                        # CV/Resume page (permalink: /cv/)
├── coursework.md                # Coursework listing (permalink: /coursework/)
└── index.md                     # Redirects to aboutme; permalink: /welcome/
```

---

## Collections

### Projects (`_projects/`)
Each file generates a page at `/projects/:name/`.

**Required front matter:**
```yaml
---
layout: project
title: "Project Title"
date: YYYY-MM-DD        # Used for sort order on projects.md gallery (newest first)
image: assets/images/filename.jpg  # Thumbnail shown on gallery + top of project page
tags: [tag1, tag2]      # Optional
---
```

**Optional front matter:**
```yaml
subtitle: "Short subtitle shown under title"
project_link: "https://..."   # Renders a "View Project/Demo" link
repo_link: "https://..."      # Renders a "View Code Repository" link
```

**Content notes:**
- Write in Markdown; HTML blocks are fine for complex layouts
- Images: use `{{ site.baseurl }}/assets/images/filename.jpg` for src
- Use `.inline-image`, `.inline-image-l`, `.inline-image-r` classes for floated inline images (max-width 350px)
- Use `style="width:100%"` on images inside `.image-block-full` divs for full-width figures
- Embedded PDFs: use `<object>` tag with `data="{{ site.baseurl }}/assets/files/file.pdf#view=FitH"`
- Embedded YouTube: use the responsive iframe wrapper pattern (padding-bottom: 56.25%)

### Reports (`_reports/`)
Each file generates a page at `/reports/:name/`.

**Required front matter:**
```yaml
---
layout: report
title: "Report Title"
date: YYYY-MM-DD        # Used for sort order on reports.md gallery (newest first)
icon: /assets/icons/filename.png   # Card thumbnail on reports gallery
file: /assets/files/filename.pdf   # File to embed
type: pdf                          # "pdf" or "slides"
---
```
The `report.html` layout auto-embeds the file in an iframe (800px tall). No body content needed unless you want intro text above the embed.

---

## Navigation
Defined in `_includes/navigation.html`. Current pages in order:
1. About Me → `/`
2. Projects → `/projects/`
3. Reports → `/reports/`
4. CV → `/cv/`
5. Coursework → `/coursework/`

To add a new top-level page, add a `<li>` entry here with appropriate active-state logic.

---

## Styling (`_sass/custom.scss`)

### Theme / Color Scheme
Supports `light` (default), `dark`, `aqua`, and `desert` via `$color_scheme` variable.

Default (light) palette:
- `$primary-color: #3a3f58` — header, footer, sidebar background
- `$background-color: #f7f8fa` — page background
- `$text-color: #333`

### Key CSS Classes

| Class | Use |
|---|---|
| `.profile-image` | Float-left portrait image, 150px wide, rounded + shadow |
| `.project-image` | Float-left image, max 200px wide |
| `.inline-image` | Centered inline image, max 350px |
| `.inline-image-l` | Float-left variant of `.inline-image` |
| `.inline-image-r` | Float-right variant of `.inline-image` |
| `.image-block-full` | Full-width figure block |
| `.project-gallery` | CSS grid for project/report cards (auto-fit, minmax 150px) |
| `.gallery-item` | Individual card in a gallery grid |
| `.back-arrow` | Styled back-navigation link |
| `.resume-download` | Container for download button |
| `.download-button` | Styled download/CTA button |
| `.report-gallery` | Gallery grid for reports page |
| `.report-card` | Individual report card |

### Typography
- Headings: `Merriweather` serif, weight 700
- Body: `Open Sans` / `Montserrat` / `Helvetica Neue`, line-height 1.6

---

## Asset Path Rules
- **Always** use `{{ site.baseurl }}/assets/...` or `{{ '/assets/...' | relative_url }}` — never bare `/assets/...` paths, as the baseurl prefix is required for GitHub Pages
- Files in `assets/files/` and `assets/covers/` are explicitly included in `_config.yml`

---

## CV / Resume Notes
- CV page is written directly in `cv.md` as HTML+Markdown hybrid
- Uses `.item`, `.item-header`, `.left`, `.date`, `.role` CSS classes for layout
- Downloadable PDF at `assets/files/Ishan_Roy.pdf`
- Transcript PDF at `assets/files/Roy_Ishan_Transcript Fall 2025.pdf`

---

## Owner / Personal Context
- **Name:** Ishan Roy
- **School:** Cornell University, Sibley School of Mechanical and Aerospace Engineering
- **Degree:** BS Mechanical Engineering, Minor Aerospace Engineering, Expected May 2027
- **Email:** irr4@cornell.edu
- **Key projects:** Magnus Effect Ultralight drone (Team Lead), CU Design Build Fly (Full Team Co-Lead), MATLAB DBF design optimization
- **Skills:** SOLIDWORKS, ANSYS, MATLAB, Python, composite fabrication, 3D printing

---

## Common Tasks & Patterns

### Add a new project
1. Create `_projects/your-project-name.md` with required front matter
2. Add image to `assets/images/`
3. Write content in Markdown below the `---`

### Add a new report
1. Add PDF to `assets/files/`
2. Add icon image to `assets/icons/`
3. Create `_reports/your-report-name.md` with required front matter

### Add a new nav page
1. Create `yourpage.md` with `layout: page` and a `permalink:`
2. Add `<li>` to `_includes/navigation.html`

### Responsive iframes (YouTube)
```html
<div style="position:relative;padding-bottom:56.25%;height:0;overflow:hidden;margin:1rem 0 2rem;">
  <iframe src="https://www.youtube.com/embed/VIDEO_ID"
    title="YouTube video" loading="lazy"
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
    allowfullscreen
    style="position:absolute;top:0;left:0;width:100%;height:100%;border:0;">
  </iframe>
</div>
```

### Embedded PDF (in project pages)
```html
<div style="width:100%; margin:1rem 0 2rem; clear:both;">
  <object data="{{ site.baseurl }}/assets/files/FILENAME.pdf#view=FitH"
          type="application/pdf" width="100%" height="390vh">
    <p>PDF preview not supported. <a href="{{ site.baseurl }}/assets/files/FILENAME.pdf" target="_blank">Open PDF</a></p>
  </object>
</div>
```

### Project timeline block
Use the inline-styled `.timeline` div pattern (see `_projects/magnus_drone.md` for full example). Each `.tl-item` has a red dot (`#b31b1b`), a `.tl-time` label, and `.tl-content` with an `<h4>` and `<p>`.
