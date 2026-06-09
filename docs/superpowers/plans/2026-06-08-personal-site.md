# Personal Site Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build a single-page personal website for Michael Nazario at mnazbro.com, hosted on GitHub Pages via `index.html`.

**Architecture:** Pure HTML + CSS in a single `index.html` file. No JavaScript, no build step, no framework. CSS is embedded in a `<style>` block in the `<head>`. Sections are: nav, hero, 3-column grid, footer.

**Tech Stack:** HTML5, CSS3 (custom properties, CSS Grid, Flexbox). No dependencies.

---

## File Map

| File | Action | Responsibility |
|------|--------|----------------|
| `index.html` | Rewrite | Entire site — nav, hero, grid, footer + embedded CSS |

---

### Task 1: Skeleton + CSS variables

**Files:**
- Modify: `index.html`

- [ ] **Step 1: Replace the current placeholder with a full HTML skeleton**

Open `index.html` and replace all content with:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Michael Nazario</title>
  <style>
    /* ── Design tokens ── */
    :root {
      --bg:        #111008;
      --bg-card:   #161409;
      --bg-muted:  #1e1c10;
      --text:      #ffffff;
      --text-muted:#888888;
      --text-dim:  #555555;
      --accent:    #f5a623;
      --border:    #2a2820;
    }

    /* ── Reset ── */
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    body {
      background: var(--bg);
      color: var(--text);
      font-family: 'Helvetica Neue', Arial, sans-serif;
      font-size: 16px;
      line-height: 1.6;
    }

    a {
      color: inherit;
      text-decoration: none;
    }
  </style>
</head>
<body>
  <p style="color: var(--accent); padding: 2rem;">Skeleton OK</p>
</body>
</html>
```

- [ ] **Step 2: Open in browser and verify**

Open `index.html` directly in your browser (drag the file or `open index.html` on macOS).

Expected: Dark warm background (`#111008`), amber text reading "Skeleton OK". No errors in browser console.

- [ ] **Step 3: Commit**

```bash
git add index.html
git commit -m "feat: html skeleton with CSS design tokens"
```

---

### Task 2: Navigation bar

**Files:**
- Modify: `index.html`

- [ ] **Step 1: Add nav CSS inside the `<style>` block** (below the `a` rule)

```css
/* ── Nav ── */
nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1.25rem 2rem;
}

.nav-logo {
  font-size: 1rem;
  font-weight: 800;
  color: var(--accent);
}

.nav-links {
  display: flex;
  gap: 2rem;
  list-style: none;
}

.nav-links a {
  font-size: 0.875rem;
  color: var(--text-muted);
  transition: color 0.2s;
}

.nav-links a:hover {
  color: var(--accent);
}
```

- [ ] **Step 2: Replace the `<body>` content with the nav**

```html
<body>
  <nav>
    <span class="nav-logo">Michael Nazario</span>
    <ul class="nav-links">
      <li><a href="#photos">Photos</a></li>
      <li><a href="#writing">Writing</a></li>
      <li><a href="#code">GitHub</a></li>
    </ul>
  </nav>
</body>
```

- [ ] **Step 3: Verify in browser**

Expected: Dark page, "Michael Nazario" in amber on the left, three muted links on the right. Hover over links — they should turn amber.

- [ ] **Step 4: Commit**

```bash
git add index.html
git commit -m "feat: navigation bar"
```

---

### Task 3: Hero section

**Files:**
- Modify: `index.html`

- [ ] **Step 1: Add hero CSS inside `<style>`** (below nav styles)

```css
/* ── Hero ── */
.hero {
  padding: 4rem 2rem 3rem;
  max-width: 720px;
}

.hero-location {
  font-size: 0.8125rem;
  color: var(--accent);
  margin-bottom: 1rem;
}

.hero-headline {
  font-size: clamp(2rem, 5vw, 3.25rem);
  font-weight: 800;
  letter-spacing: -0.03em;
  line-height: 1.05;
  color: var(--text);
  margin-bottom: 0.75rem;
}

.hero-subtitle {
  font-size: 0.9375rem;
  color: var(--text-dim);
  margin-bottom: 1.5rem;
}

.hero-bio {
  font-size: 0.9375rem;
  color: var(--text-muted);
  max-width: 480px;
  line-height: 1.75;
  margin-bottom: 2rem;
}

.hero-links {
  display: flex;
  gap: 1.5rem;
  flex-wrap: wrap;
}

.hero-links a {
  font-size: 0.875rem;
  color: var(--text-dim);
  border-bottom: 1px solid var(--border);
  padding-bottom: 2px;
  transition: color 0.2s, border-color 0.2s;
}

.hero-links a.primary {
  color: var(--accent);
  border-color: var(--accent);
}

.hero-links a:hover {
  color: var(--accent);
  border-color: var(--accent);
}

.hero-divider {
  height: 1px;
  background: linear-gradient(to right, var(--accent), transparent);
  margin: 0 2rem;
  opacity: 0.4;
}
```

- [ ] **Step 2: Add the hero HTML inside `<body>`, after `</nav>`**

```html
  <section class="hero">
    <p class="hero-location">Based in New York City 📍</p>
    <h1 class="hero-headline">Building software.<br>Shooting on film.</h1>
    <p class="hero-subtitle">Software engineer by day, 35mm photographer by choice.</p>
    <p class="hero-bio">
      <!-- Michael: replace this placeholder with your bio -->
      Short bio goes here. A few sentences about who you are, what you care about,
      and what you're building.
    </p>
    <div class="hero-links">
      <a href="https://github.com/mnazbro" class="primary" target="_blank" rel="noopener">GitHub ↗</a>
      <a href="#" target="_blank" rel="noopener">Instagram ↗</a>
      <a href="#" target="_blank" rel="noopener">LinkedIn ↗</a>
    </div>
  </section>
  <div class="hero-divider"></div>
```

- [ ] **Step 3: Verify in browser**

Expected:
- "Based in New York City 📍" in amber
- Large bold headline "Building software. Shooting on film."
- Muted subtitle and bio text
- GitHub link in amber, others in dim gray — all turn amber on hover
- Thin amber-to-transparent gradient divider below hero

- [ ] **Step 4: Commit**

```bash
git add index.html
git commit -m "feat: hero section with bio placeholder and social links"
```

---

### Task 4: Three-column grid

**Files:**
- Modify: `index.html`

- [ ] **Step 1: Add grid CSS inside `<style>`** (below hero styles)

```css
/* ── Grid ── */
.grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1px;
  background: var(--bg-muted);
  margin-top: 1px;
}

.card {
  background: var(--bg-card);
  padding: 2rem 1.75rem;
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.card-icon {
  font-size: 1.5rem;
  margin-bottom: 0.25rem;
}

.card-title {
  font-size: 1rem;
  font-weight: 700;
  color: var(--text);
}

.card-desc {
  font-size: 0.8125rem;
  color: var(--text-dim);
  line-height: 1.6;
  flex: 1;
}

.card-link {
  font-size: 0.8125rem;
  color: var(--accent);
  margin-top: 0.75rem;
  transition: opacity 0.2s;
}

.card-link:hover {
  opacity: 0.75;
}

.card-link.muted {
  color: var(--text-dim);
  cursor: default;
}
```

- [ ] **Step 2: Add grid HTML inside `<body>`, after the hero divider**

```html
  <main id="content">
    <div class="grid">

      <article class="card" id="photos">
        <div class="card-icon">📷</div>
        <h2 class="card-title">Film Photography</h2>
        <p class="card-desc">35mm and 6×6 — analog in a digital world. Street, portrait, landscape.</p>
        <!-- Michael: replace href with your Google Photos or Instagram gallery URL -->
        <a class="card-link" href="#" target="_blank" rel="noopener">See gallery →</a>
      </article>

      <article class="card" id="writing">
        <div class="card-icon">✍️</div>
        <h2 class="card-title">Writing</h2>
        <p class="card-desc">Thoughts on software engineering, craft, and the industry.</p>
        <span class="card-link muted">Coming soon</span>
      </article>

      <article class="card" id="code">
        <div class="card-icon">💻</div>
        <h2 class="card-title">Code</h2>
        <p class="card-desc">Mobile apps and open source projects.</p>
        <span class="card-link muted">Coming soon</span>
      </article>

    </div>
  </main>
```

- [ ] **Step 3: Verify in browser**

Expected:
- Three equal-width cards separated by 1px dark gaps
- Each card has emoji icon, bold title, muted description
- Photography card: "See gallery →" in amber
- Writing + Code cards: "Coming soon" in dim gray (not clickable)

- [ ] **Step 4: Commit**

```bash
git add index.html
git commit -m "feat: three-column grid with photography, writing, code cards"
```

---

### Task 5: Footer

**Files:**
- Modify: `index.html`

- [ ] **Step 1: Add footer CSS inside `<style>`** (below grid styles)

```css
/* ── Footer ── */
footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1.25rem 2rem;
  border-top: 1px solid var(--border);
  margin-top: 1px;
}

.footer-copy {
  font-size: 0.75rem;
  color: var(--text-dim);
}

.footer-location {
  font-size: 0.75rem;
  color: var(--text-dim);
  letter-spacing: 0.1em;
}
```

- [ ] **Step 2: Add footer HTML inside `<body>`, after `</main>`**

```html
  <footer>
    <span class="footer-copy">© 2026 Michael Nazario</span>
    <span class="footer-location">NYC</span>
  </footer>
```

- [ ] **Step 3: Verify in browser**

Expected: Dim "© 2026 Michael Nazario" on the left, "NYC" on the right, separated by a subtle dark border line at the top.

- [ ] **Step 4: Commit**

```bash
git add index.html
git commit -m "feat: footer with copyright and location"
```

---

### Task 6: Responsive layout

**Files:**
- Modify: `index.html`

- [ ] **Step 1: Add responsive CSS at the bottom of `<style>`** (last rules, after footer styles)

```css
/* ── Responsive ── */
@media (max-width: 640px) {
  nav {
    padding: 1rem 1.25rem;
  }

  .nav-links {
    gap: 1.25rem;
  }

  .hero {
    padding: 2.5rem 1.25rem 2rem;
  }

  .hero-divider {
    margin: 0 1.25rem;
  }

  .grid {
    grid-template-columns: 1fr;
  }

  footer {
    padding: 1rem 1.25rem;
  }
}
```

- [ ] **Step 2: Verify on mobile width**

In your browser DevTools, toggle the device toolbar (Cmd+Shift+M on Chrome macOS) and set width to 375px.

Expected:
- Nav links still visible and comfortable
- Hero text scales down gracefully via `clamp()`
- Grid stacks to a single column
- No horizontal scrollbar

- [ ] **Step 3: Commit**

```bash
git add index.html
git commit -m "feat: responsive layout for mobile"
```

---

### Task 7: Meta tags and page polish

**Files:**
- Modify: `index.html`

- [ ] **Step 1: Add meta tags inside `<head>`**, after the `<title>` tag

```html
  <meta name="description" content="Michael Nazario — Software engineer and film photographer based in New York City.">
  <meta property="og:title" content="Michael Nazario">
  <meta property="og:description" content="Software engineer and film photographer based in New York City.">
  <meta property="og:type" content="website">
  <meta property="og:url" content="https://mnazbro.com">
  <link rel="canonical" href="https://mnazbro.com">
```

- [ ] **Step 2: Add favicon fallback inside `<head>`**, after meta tags

```html
  <link rel="icon" href="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'><text y='.9em' font-size='90'>📷</text></svg>">
```

- [ ] **Step 3: Verify**

Reload the page. Expected:
- Browser tab shows camera emoji as favicon
- Page title reads "Michael Nazario"
- Right-click → View Page Source — confirm meta description and OG tags are present

- [ ] **Step 4: Commit**

```bash
git add index.html
git commit -m "feat: meta tags, OG tags, and emoji favicon"
```

---

### Task 8: Deploy to GitHub Pages

**Files:**
- No file changes — push existing branch

- [ ] **Step 1: Verify CNAME is correct**

```bash
cat CNAME
```

Expected output: `mnazbro.com`

- [ ] **Step 2: Push to main**

```bash
git push origin main
```

- [ ] **Step 3: Confirm GitHub Pages deployment**

Go to `https://github.com/mnazbro/mnazbro.github.io/settings/pages` and confirm:
- Source is set to deploy from `main` branch, `/ (root)`
- Custom domain shows `mnazbro.com`

- [ ] **Step 4: Visit the live site**

Open `https://mnazbro.com` in your browser (DNS may take a few minutes if first deploy).

Expected: Same result as local — dark warm page, amber accents, all sections present.

---

## Content Checklist (for Michael to fill in after deploy)

- [ ] Write bio paragraph in `.hero-bio`
- [ ] Add GitHub URL: `https://github.com/mnazbro` (already set)
- [ ] Add Instagram URL in hero links
- [ ] Add LinkedIn URL in hero links
- [ ] Add photography gallery URL in the Photos card (`href="#"`)
- [ ] Update Writing card link when blog platform is chosen
- [ ] Update Code card link to GitHub profile/projects when ready
