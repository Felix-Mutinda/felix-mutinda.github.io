# Felix Isaiah - Portfolio & Architecture Showcase

GitHub Pages site hosting public case studies, Architecture Decision Records (ADRs), and systems-level narratives. Serves as the deep-dive anchor between LinkedIn hooks and GitHub proof-of-work.

Built for readability, long-term maintainability, and explicit constraint → decision → outcome storytelling.

---

## 🎨 Brand & Positioning Principles

| Dimension | Specification |
|-----------|---------------|
| **Core Identity** | ML Platform Architect \| DevSecMLOps |
| **Visual System** | Primary: `#1A3A52` (Navy/Charcoal) \| Accent: `#2C5AA0` (Professional Blue) \| Background: `#F5F5F5` (Cream/Off-White) |
| **Design Ethos** | Minimalist, geometric, high-contrast. Zero gradients, shadows, or decorative elements. Negative space as a functional element. |
| **Tone & Voice** | Precise, evidence-based, constraint-focused. Zero hype. Systems-thinking over tool-chasing. Professional restraint with subtle authenticity. |
| **Content Philosophy** | Every piece answers: What bottleneck was removed? What trade-offs were accepted? What organizational impact followed? |
| **Cross-Platform Pipeline** | LinkedIn (150–300 word hook) → Portfolio (constraint → decision → outcome narrative) → GitHub (reference implementation / ADR / sanitized configs) |
| **Accessibility** | WCAG AAA contrast ratios. No color-only meaning. Legible at 40px–400px. Grayscale-friendly. |

---

## 🏗️ Technical Architecture

| Component | Implementation |
|-----------|----------------|
| **Engine** | Jekyll (GitHub Pages native, zero CI required) |
| **Rendering** | Markdown-first (`kramdown`), minimal custom CSS, semantic HTML5 |
| **SEO / Metadata** | `jekyll-seo-tag`, `jekyll-feed`, `jekyll-sitemap` |
| **Layouts** | `default.html` (base shell), `showcase.html` (deep-dive template with automatic cross-linking) |
| **Styling** | Single CSS file (`assets/css/style.css`), CSS variables, mobile-responsive (`@media` breakpoints) |
| **Hosting** | GitHub Pages (`main` branch auto-deploys on push) |
| **Performance** | Zero external JS, <50KB CSS, static HTML output, WCAG AA+ contrast, fast LCP/CLS scores |

---

## 📁 Directory Structure

```text
.
├── _config.yml              # Site metadata, plugins, path defaults, build config
├── index.md                 # Homepage: positioning + showcase index + featured work
├── _layouts/
│   ├── default.html         # Base shell (nav, container, footer, SEO head)
│   └── showcase.html        # Deep-dive template with LinkedIn/GitHub cross-link injection
├── _includes/
│   ├── header.html          # Navigation bar + site title
│   └── footer.html          # Contact links + brand philosophy quote
├── assets/
│   ├── css/style.css        # Brand-aligned, minimal, responsive, CSS-variable driven
│   └── img/                 # Architecture diagrams, icons, sanitized screenshots
├── showcase/                # Case studies (Problem → Decision → Outcome → Lessons)
├── adr/                     # Architecture Decision Records (Context → Decision → Consequences)
└── README.md                # This file: repo overview, brand specs, agent guidelines
```

---

## 🔄 Content Pipeline & Frontmatter Schema

Every new deep-dive follows this exact frontmatter convention. Coding agents should parse these fields to auto-generate cross-links, sitemaps, and index pages.

```yaml
---
layout: showcase
title: "Descriptive Title (Action + Domain)"
date: YYYY-MM-DD
tags: [kebab-case, topic1, topic2]
linkedin_post: "https://linkedin.com/posts/..."
github_repo: "https://github.com/felix-mutinda/repo-name"
---
```

**Pipeline Workflow:**
1. **LinkedIn Hook:** 150–300 word narrative post using Template 3 (`06_MESSAGING_TEMPLATES.md`)
2. **Portfolio Deep Dive:** Markdown file in `showcase/` or `adr/` using `showcase.html` layout
3. **GitHub Proof:** Reference implementation, sanitized configs, or ADR registry
4. **Cross-Link Sync:** Frontmatter fields automatically render navigation links in the layout

---

## ⚙️ Local Development & Build

```bash
# 1. Install dependencies
bundle install

# 2. Run local server (auto-reloads on file change)
bundle exec jekyll serve

# 3. Build static site (production)
JEKYLL_ENV=production bundle exec jekyll build
```

GitHub Actions auto-deploys on push to `main`. No custom CI required.

---

## 🤖 Guidelines for AI / Agent Contributors

When generating or updating content, enforce these constraints:

| Rule | Implementation |
|------|----------------|
| **No proprietary data** | Sanitize all metrics to %, ranges, percentiles, or relative improvements |
| **Enforce schema** | Every markdown file in `showcase/` or `adr/` must include required frontmatter fields |
| **Keep CSS lean** | Do not add inline styles. Extend `style.css` via CSS variables only |
| **Semantic HTML** | Use `<article>`, `<section>`, `<nav>`, `<footer>` in layouts |
| **Link validation** | All `linkedin_post` and `github_repo` URLs must resolve to `200 OK` before merge |
| **Tone check** | Remove hype words (`excited`, `revolutionary`, `cutting-edge`). Replace with constraint/outcome framing |
| **File naming** | `YYYY-MM-DD-kebab-case.md` for chronological sorting and predictable routing |
| **Brand alignment** | Use navy (`#1A3A52`) for headings, blue (`#2C5AA0`) for links, cream (`#F5F5F5`) for backgrounds |

---

## 📜 Maintenance Checklist

- [ ] Run `bundle exec jekyll build` locally before merging PRs
- [ ] Validate all cross-links quarterly
- [ ] Archive deprecated case studies to `_archive/` instead of deleting
- [ ] Keep `_config.yml` title/description synced with LinkedIn headline
- [ ] Audit `tags` in frontmatter for consistency (lowercase, hyphenated)
- [ ] Verify directory structure matches this README after major refactors

---

> *"The best platform architecture solves constraints, not just technical problems."*