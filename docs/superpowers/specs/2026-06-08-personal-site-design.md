# Personal Site Design — mnazbro.com

**Date:** 2026-06-08
**Status:** Approved

## Overview

A single-page personal website for Michael Nazario, a Software Engineer and film photographer based in New York City. The site serves as a personal hub: personal branding, photography showcase, and future home for writing and code projects.

Hosted on GitHub Pages at `mnazbro.com`, delivered as a single `index.html` file with inline or co-located CSS.

## Visual Style

- **Background:** Warm dark (`#111008`) — slightly amber-tinted black, not cold
- **Text:** White (`#ffffff`) for headings, muted gray (`#888`) for body/secondary
- **Accent:** Amber/gold (`#f5a623`) — used for logo, active links, hover states, subtle highlights
- **Typography:** System sans-serif (`Helvetica Neue`, Arial fallback). Mixed case throughout — no aggressive ALL-CAPS or wide letter-spacing. Friendly, not institutional.
- **Feel:** Bold and modern but approachable. Dark creative portfolio energy without being stiff.

## Page Structure

Single scrolling page, no JavaScript framework required. Vanilla HTML + CSS only.

### 1. Navigation
- Left: "Michael Nazario" in amber — acts as home anchor
- Right: plain text links — `Photos`, `Writing`, `GitHub`
- Minimal, no border, stays at top (not sticky for now)

### 2. Hero Section
- Location tag: `Based in New York City 📍` in amber
- Headline: **"Building software. Shooting on film."** — large, bold, mixed case
- Subtitle: `Software engineer by day, 35mm photographer by choice.`
- Bio: Short paragraph placeholder — Michael will write this
- Social links: GitHub ↗, Instagram ↗, LinkedIn ↗ (URLs to be filled in)

### 3. Three-Column Grid

Each column is a card. Active cards use amber accents; "coming soon" cards are muted.

| Column | Icon | Title | State | Links to |
|--------|------|-------|-------|----------|
| 1 | 📷 | Film Photography | Active | Google Photos or Instagram gallery |
| 2 | ✍️ | Writing | Coming soon | External blog (platform TBD) |
| 3 | 💻 | Code | Coming soon | GitHub profile/projects |

Photography description: *"35mm and 6×6 — analog in a digital world."*
Writing description: *"Thoughts on software engineering."*
Code description: *"Mobile apps and open source."*

### 4. Footer
- `© 2026 Michael Nazario` on left
- `NYC` on right
- Minimal, 1px top border in dark gray

## Content Placeholders (to be filled by Michael)

- Short bio paragraph in hero
- GitHub URL
- Instagram URL
- LinkedIn URL
- Photography gallery link (Google Photos or Instagram)

## Out of Scope (for now)

- Coast / employer mention — intentionally omitted
- Blog posts — external platform, link added when ready
- GitHub project cards — coming soon state only
- JavaScript, animations, frameworks
- Mobile-specific nav (hamburger menu) — single page is simple enough

## File Structure

```
index.html       — entire site (HTML + embedded or linked CSS)
CNAME            — mnazbro.com (already exists)
```

No build step. No dependencies. Deployable by pushing to `main`.
