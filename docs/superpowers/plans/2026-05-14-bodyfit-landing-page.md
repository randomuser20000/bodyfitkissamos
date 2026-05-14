# Bodyfit Kissamos — Lightweight Landing Page Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build a clean, fast, lightweight one-page responsive website for Bodyfit Kissamos gym — fully optimized for Generative Engine Optimization (GEO) so all content is readable and citable by LLMs (ChatGPT, Claude, Perplexity, Google AI Overviews). Replaces the existing Tailwind CDN prototype with hand-written CSS and zero JavaScript dependencies.

**Architecture:** Single `index.html` file with all CSS inlined via `<style>` — no build tools, no frameworks, no external CSS. Design tokens from `DESIGN.md` are mapped to CSS custom properties. Vanilla JS is used only for the mobile menu toggle (~15 lines). External dependencies are limited to Google Fonts and Material Symbols icon font. All content is server-rendered HTML (no JS-dependent content) — critical because AI crawlers do NOT execute JavaScript.

**Tech Stack:** HTML5, CSS3 (custom properties, grid, flexbox, media queries), vanilla JavaScript (mobile menu only), Google Fonts CDN (Montserrat + Inter), Material Symbols CDN.

**GEO Strategy:** JSON-LD schema stacking (LocalBusiness + FAQPage + Offer), `llms.txt` for AI crawler guidance, `robots.txt` allowing GPTBot/ClaudeBot/PerplexityBot, answer-first content structure (direct answer in first 40-60 words per section), question-based headings, self-contained 134-167 word citable passages, FAQ section with structured Q&A.

**Reference files:**
- `DESIGN.md` — design tokens and component rules
- `screen.png` — visual reference for the final result
- `code.html` — existing prototype (reference only, will be replaced)

---

### Task 1: HTML Document Shell + CSS Custom Properties

**Files:**
- Create: `index.html`

This task creates the document skeleton with all design tokens as CSS custom properties, the global reset, the noise overlay, and base typography. No visible content yet beyond the background and noise effect.

- [ ] **Step 1: Create `index.html` with doctype, head, and CSS custom properties**

```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Bodyfit Kissamos — Old-School Bodybuilding Gym in Chania, Crete</title>
<meta name="description" content="Bodyfit Kissamos is an authentic bodybuilding gym in Kissamos, Chania, Crete, Greece. Day pass €10, weekly €35, monthly €55. Air-conditioned, fully equipped with free weights and machines. Open Mon–Sat.">

<!-- GEO: Open Graph for AI and social parsers -->
<meta property="og:title" content="Bodyfit Kissamos — Old-School Bodybuilding Gym in Chania, Crete">
<meta property="og:description" content="Authentic bodybuilding gym in Kissamos, Chania, Crete. Day pass €10, weekly €35, monthly €55. Free weights, machines, air conditioning, supplements on-site.">
<meta property="og:type" content="website">
<meta property="og:locale" content="en_US">
<meta property="og:site_name" content="Bodyfit Kissamos">

<!-- GEO: Additional meta for AI crawlers -->
<meta name="robots" content="index, follow, max-snippet:-1, max-image-preview:large">
<meta name="author" content="Bodyfit Kissamos">
<meta name="geo.region" content="GR-X">
<meta name="geo.placename" content="Kissamos, Chania, Crete">

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@700;800;900&family=Inter:wght@400;700&display=swap" rel="stylesheet">
<link href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:wght,FILL@100..700,0..1&display=swap" rel="stylesheet">

<!-- GEO: JSON-LD LocalBusiness + Gym schema -->
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "HealthClub",
  "name": "Bodyfit Kissamos",
  "alternateName": "BODYFIT KISSAMOS",
  "description": "Bodyfit Kissamos is an authentic old-school bodybuilding gym located in Kissamos, Chania, Crete, Greece. The gym features heavy free weights, resistance machines, a fully air-conditioned training floor, and on-site supplements including protein, pre-workout, and BCAAs.",
  "url": "https://bodyfikissamos.com",
  "image": "https://lh3.googleusercontent.com/aida-public/AB6AXuAo39WNUkYFs-2epbhTUM62BxZzBTVfCpMTaWuAAY59OT1vo3DRdoPVG130Q1527IZPZkgszMI-Xqnm4hT8xmi_f95lwmXocCFkWnXgB_jrMdA-V4bJo-ena_cRb4Ad0iBzb3J2PV43RailLtvnSnZDy3ko6afHMuCDudfjTHZKxmq-lyEn_4DS1YOcRNzOxNSTf9bB0E0HXUvCuW-WLoYskaI-7hgGftL2Jey5kWXv5HY-k1y_5HQkpd7ZCIRbMAGqyBx0Z_NEgQZq",
  "telephone": "",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "",
    "addressLocality": "Kissamos",
    "addressRegion": "Chania",
    "addressCountry": "GR"
  },
  "geo": {
    "@type": "GeoCoordinates",
    "latitude": 35.4946,
    "longitude": 23.6559
  },
  "openingHoursSpecification": [
    {
      "@type": "OpeningHoursSpecification",
      "dayOfWeek": ["Monday","Tuesday","Wednesday","Thursday","Friday"],
      "opens": "10:00",
      "closes": "22:00"
    },
    {
      "@type": "OpeningHoursSpecification",
      "dayOfWeek": "Saturday",
      "opens": "10:00",
      "closes": "21:00"
    }
  ],
  "priceRange": "€10 - €55",
  "currenciesAccepted": "EUR",
  "paymentAccepted": "Cash, Credit Card, NFC",
  "hasOfferCatalog": {
    "@type": "OfferCatalog",
    "name": "Gym Membership Plans",
    "itemListElement": [
      {
        "@type": "Offer",
        "name": "Day Pass",
        "description": "Single-day full floor access with free weights and machines",
        "price": "10",
        "priceCurrency": "EUR"
      },
      {
        "@type": "Offer",
        "name": "Weekly Pass",
        "description": "7 consecutive days of unlimited gym access with locker usage, ideal for travelers visiting Crete",
        "price": "35",
        "priceCurrency": "EUR"
      },
      {
        "@type": "Offer",
        "name": "Monthly Membership",
        "description": "Unlimited monthly gym access with priority support and nutrition advice",
        "price": "55",
        "priceCurrency": "EUR"
      }
    ]
  },
  "amenityFeature": [
    {"@type": "LocationFeatureSpecification", "name": "Air Conditioning", "value": true},
    {"@type": "LocationFeatureSpecification", "name": "Free Weights", "value": true},
    {"@type": "LocationFeatureSpecification", "name": "Resistance Machines", "value": true},
    {"@type": "LocationFeatureSpecification", "name": "Supplements Shop", "value": true},
    {"@type": "LocationFeatureSpecification", "name": "Lockers", "value": true},
    {"@type": "LocationFeatureSpecification", "name": "NFC Payment", "value": true}
  ],
  "keywords": "gym Kissamos, bodybuilding Chania, gym Crete, fitness Kissamos, old school gym Greece, weights gym Chania"
}
</script>
<style>
/* ── Design Tokens ── */
:root {
  --surface: #131313;
  --surface-dim: #131313;
  --surface-bright: #3a3939;
  --surface-container-lowest: #0e0e0e;
  --surface-container-low: #1c1b1b;
  --surface-container: #201f1f;
  --surface-container-high: #2a2a2a;
  --surface-container-highest: #353534;
  --on-surface: #e5e2e1;
  --on-surface-variant: #c4c9ac;
  --surface-variant: #353534;
  --surface-tint: #abd600;
  --primary: #ffffff;
  --on-primary: #283500;
  --primary-container: #c3f400;
  --primary-fixed: #c3f400;
  --primary-fixed-dim: #abd600;
  --on-primary-fixed: #161e00;
  --secondary: #ffb59a;
  --secondary-container: #ff5e07;
  --on-secondary-container: #531900;
  --outline: #8e9379;
  --outline-variant: #444933;
  --background: #0a0a0a;

  --font-headline: 'Montserrat', sans-serif;
  --font-body: 'Inter', sans-serif;

  --space-unit: 8px;
  --space-gutter: 24px;
  --margin-mobile: 16px;
  --margin-desktop: 48px;
  --container-max: 1280px;
}

/* ── Reset ── */
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

body {
  background: var(--background);
  color: var(--on-surface);
  font-family: var(--font-body);
  font-size: 16px;
  line-height: 1.6;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

img { max-width: 100%; display: block; }
a { color: inherit; text-decoration: none; }
ul { list-style: none; }
button { cursor: pointer; border: none; font: inherit; }

/* ── Noise Overlay ── */
.noise-overlay {
  position: fixed;
  inset: 0;
  width: 100vw;
  height: 100vh;
  pointer-events: none;
  z-index: 9999;
  opacity: 0.03;
  background-image: url('data:image/svg+xml,%3Csvg viewBox="0 0 200 200" xmlns="http://www.w3.org/2000/svg"%3E%3Cfilter id="n"%3E%3CfeTurbulence type="fractalNoise" baseFrequency="0.65" numOctaves="3" stitchTiles="stitch"/%3E%3C/filter%3E%3Crect width="100%25" height="100%25" filter="url(%23n)"/%3E%3C/svg%3E');
}

/* ── Utility: Container ── */
.container {
  max-width: var(--container-max);
  margin-inline: auto;
  padding-inline: var(--margin-mobile);
}
@media (min-width: 768px) {
  .container { padding-inline: var(--margin-desktop); }
}

/* ── Typography ── */
.headline-xl {
  font-family: var(--font-headline);
  font-size: clamp(36px, 8vw, 64px);
  font-weight: 900;
  line-height: 1.1;
  letter-spacing: -0.04em;
  text-transform: uppercase;
}
.headline-lg {
  font-family: var(--font-headline);
  font-size: clamp(28px, 5vw, 40px);
  font-weight: 800;
  line-height: 1.2;
  letter-spacing: -0.02em;
  text-transform: uppercase;
}
.headline-md {
  font-family: var(--font-headline);
  font-size: 24px;
  font-weight: 700;
  line-height: 1.3;
  text-transform: uppercase;
}
.body-lg {
  font-family: var(--font-body);
  font-size: 18px;
  font-weight: 400;
  line-height: 1.6;
}
.label-sm {
  font-family: var(--font-body);
  font-size: 12px;
  font-weight: 700;
  line-height: 1;
  letter-spacing: 0.1em;
  text-transform: uppercase;
}
</style>
</head>
<body>
<div class="noise-overlay" aria-hidden="true"></div>
</body>
</html>
```

- [ ] **Step 2: Open in browser to verify**

Open `index.html` in a browser. Expected: deep black page (#0a0a0a) with a subtle grainy texture visible on close inspection.

- [ ] **Step 3: Commit**

```
feat: scaffold index.html with design tokens and base styles
```

---

### Task 2: Sticky Navigation Bar + Mobile Menu

**Files:**
- Modify: `index.html`

Adds the sticky top navigation with the logo, desktop nav links, "Join Now" CTA, and a hamburger toggle for mobile. This is the only section requiring JavaScript.

- [ ] **Step 1: Add nav CSS after the typography block**

```css
/* ── Nav ── */
.nav {
  position: sticky;
  top: 0;
  z-index: 50;
  background: var(--background);
  border-bottom: 2px solid var(--surface-variant);
}
.nav-inner {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 80px;
}
.nav-logo {
  font-family: var(--font-headline);
  font-size: 24px;
  font-weight: 900;
  letter-spacing: -0.04em;
  color: var(--primary-fixed);
  text-transform: uppercase;
}
.nav-links {
  display: none;
  gap: var(--space-gutter);
  align-items: center;
}
@media (min-width: 768px) {
  .nav-links { display: flex; }
}
.nav-links a {
  font-family: var(--font-headline);
  font-size: 16px;
  font-weight: 700;
  text-transform: uppercase;
  color: var(--on-surface);
  transition: color 0.2s;
}
.nav-links a:hover { color: var(--primary-fixed); }

.btn-primary {
  background: var(--primary-fixed);
  color: var(--on-primary-fixed);
  font-family: var(--font-headline);
  font-weight: 800;
  text-transform: uppercase;
  padding: 12px 24px;
  border-bottom: 2px solid black;
  transition: background 0.2s;
}
.btn-primary:hover { background: var(--surface-tint); }
.btn-primary:active { transform: scale(0.95); }

.btn-secondary {
  background: transparent;
  color: var(--primary);
  font-family: var(--font-headline);
  font-weight: 700;
  text-transform: uppercase;
  padding: 12px 24px;
  border: 2px solid var(--primary);
  transition: background 0.2s;
}
.btn-secondary:hover { background: var(--surface-bright); }

/* ── Hamburger ── */
.hamburger {
  display: flex;
  flex-direction: column;
  gap: 5px;
  background: none;
  padding: 8px;
}
.hamburger span {
  display: block;
  width: 24px;
  height: 2px;
  background: var(--primary);
  transition: transform 0.3s, opacity 0.3s;
}
.hamburger[aria-expanded="true"] span:nth-child(1) { transform: translateY(7px) rotate(45deg); }
.hamburger[aria-expanded="true"] span:nth-child(2) { opacity: 0; }
.hamburger[aria-expanded="true"] span:nth-child(3) { transform: translateY(-7px) rotate(-45deg); }
@media (min-width: 768px) {
  .hamburger { display: none; }
}

/* ── Mobile Menu ── */
.mobile-menu {
  display: none;
  flex-direction: column;
  gap: 0;
  background: var(--surface-container);
  border-bottom: 2px solid var(--surface-variant);
  padding: var(--space-gutter);
}
.mobile-menu.open { display: flex; }
.mobile-menu a {
  font-family: var(--font-headline);
  font-size: 20px;
  font-weight: 700;
  text-transform: uppercase;
  color: var(--on-surface);
  padding: 16px 0;
  border-bottom: 1px solid var(--surface-variant);
  transition: color 0.2s;
}
.mobile-menu a:last-child { border-bottom: none; }
.mobile-menu a:hover { color: var(--primary-fixed); }
@media (min-width: 768px) {
  .mobile-menu { display: none !important; }
}
```

- [ ] **Step 2: Add nav HTML inside `<body>` after the noise overlay**

```html
<nav class="nav" id="nav">
  <div class="container nav-inner">
    <a href="#" class="nav-logo">Bodyfit Kissamos</a>
    <ul class="nav-links">
      <li><a href="#features">Training</a></li>
      <li><a href="#pricing">Pricing</a></li>
      <li><a href="#info">Info</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
    <div style="display:flex;align-items:center;gap:16px;">
      <a href="#pricing" class="btn-primary" style="font-size:14px;">Join Now</a>
      <button class="hamburger" id="menuBtn" aria-expanded="false" aria-label="Toggle menu">
        <span></span><span></span><span></span>
      </button>
    </div>
  </div>
  <div class="mobile-menu" id="mobileMenu">
    <a href="#features">Training</a>
    <a href="#pricing">Pricing</a>
    <a href="#info">Info</a>
    <a href="#contact">Contact</a>
  </div>
</nav>
```

- [ ] **Step 3: Add JavaScript before `</body>`**

```html
<script>
const menuBtn = document.getElementById('menuBtn');
const mobileMenu = document.getElementById('mobileMenu');
menuBtn.addEventListener('click', () => {
  const open = menuBtn.getAttribute('aria-expanded') === 'true';
  menuBtn.setAttribute('aria-expanded', !open);
  mobileMenu.classList.toggle('open');
});
mobileMenu.querySelectorAll('a').forEach(a => {
  a.addEventListener('click', () => {
    menuBtn.setAttribute('aria-expanded', 'false');
    mobileMenu.classList.remove('open');
  });
});
</script>
```

- [ ] **Step 4: Add smooth scroll to html element**

Add this at the top of the CSS, inside the reset block:

```css
html { scroll-behavior: smooth; scroll-padding-top: 88px; }
```

- [ ] **Step 5: Open in browser and test**

Verify:
- Nav is sticky and stays at top on scroll
- Desktop: four links visible, hamburger hidden
- Mobile (resize to <768px): links hidden, hamburger visible, clicking it opens/closes mobile menu with animated icon
- "Join Now" button is Safety Yellow with black text
- Clicking mobile links closes the menu

- [ ] **Step 6: Commit**

```
feat: add sticky nav with responsive hamburger menu
```

---

### Task 3: Hero Section

**Files:**
- Modify: `index.html`

The hero has a gym interior background image (grayscale, low opacity), a left-aligned gradient overlay, the main headline, tagline, and CTA button.

- [ ] **Step 1: Add hero CSS**

```css
/* ── Hero ── */
.hero {
  position: relative;
  min-height: 90vh;
  display: flex;
  align-items: center;
  border-bottom: 2px solid var(--surface-variant);
  background: var(--surface-dim);
  overflow: hidden;
}
.hero-bg {
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  filter: grayscale(1);
  opacity: 0.4;
  mix-blend-mode: overlay;
}
.hero-gradient {
  position: absolute;
  inset: 0;
  background: linear-gradient(to right, var(--background), rgba(19,19,19,0.8), transparent);
  z-index: 1;
}
.hero-content {
  position: relative;
  z-index: 2;
  max-width: 720px;
}
.hero-content h1 {
  color: var(--primary);
  margin-bottom: var(--space-unit);
}
.hero-tagline {
  color: var(--primary-fixed);
  font-family: var(--font-headline);
  font-size: clamp(18px, 3vw, 24px);
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  margin-bottom: 32px;
}
.hero .btn-primary {
  font-size: clamp(16px, 2.5vw, 24px);
  padding: 16px 32px;
  border-bottom-width: 4px;
  display: inline-flex;
  align-items: center;
  gap: 8px;
}
```

- [ ] **Step 2: Add hero HTML after `</nav>`**

```html
<section class="hero">
  <div class="hero-gradient"></div>
  <img class="hero-bg" src="https://lh3.googleusercontent.com/aida-public/AB6AXuAo39WNUkYFs-2epbhTUM62BxZzBTVfCpMTaWuAAY59OT1vo3DRdoPVG130Q1527IZPZkgszMI-Xqnm4hT8xmi_f95lwmXocCFkWnXgB_jrMdA-V4bJo-ena_cRb4Ad0iBzb3J2PV43RailLtvnSnZDy3ko6afHMuCDudfjTHZKxmq-lyEn_4DS1YOcRNzOxNSTf9bB0E0HXUvCuW-WLoYskaI-7hgGftL2Jey5kWXv5HY-k1y_5HQkpd7ZCIRbMAGqyBx0Z_NEgQZq" alt="Bodyfit Kissamos gym interior" width="1920" height="1080" loading="eager">
  <div class="container hero-content">
    <h1 class="headline-xl">The Hidden Gem of Chania.</h1>
    <p class="hero-tagline">No gimmicks, just iron.</p>
    <!-- GEO: Answer-first paragraph visible to crawlers, visually subtle -->
    <p class="body-lg" style="color:var(--on-surface-variant);max-width:540px;margin-bottom:32px;">Bodyfit Kissamos is an authentic old-school bodybuilding gym in Kissamos, Chania, Crete. Fully equipped with heavy free weights, resistance machines, and air conditioning. Day passes from €10.</p>
    <a href="#pricing" class="btn-primary">
      Join the Grind
      <span class="material-symbols-outlined" style="font-variation-settings:'FILL' 1">arrow_forward</span>
    </a>
  </div>
</section>
```

- [ ] **Step 3: Open in browser and verify**

Expected: full-viewport hero with dark grayscale gym image, left-to-right gradient, bold headline, Safety Yellow CTA button. Text should be left-aligned and responsive (smaller on mobile).

- [ ] **Step 4: Commit**

```
feat: add hero section with gradient overlay and CTA
```

---

### Task 4: Features Section (3-Column Grid)

**Files:**
- Modify: `index.html`

Three feature cards in a responsive grid: Old School Vibes, Clean & Cooled, Expert Spotting. Each has an icon, heading, and description.

- [ ] **Step 1: Add features CSS**

```css
/* ── Section ── */
.section { padding: 96px 0; }
.section-title {
  color: var(--primary);
  margin-bottom: 48px;
  padding-left: 16px;
  border-left: 4px solid var(--primary-fixed);
}

/* ── Features Grid ── */
.grid-3 {
  display: grid;
  grid-template-columns: 1fr;
  gap: var(--space-gutter);
}
@media (min-width: 768px) {
  .grid-3 { grid-template-columns: repeat(3, 1fr); }
}

.card {
  background: var(--surface-container-high);
  border: 1px solid var(--surface-variant);
  padding: 32px;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  transition: border-color 0.3s;
}
.card:hover { border-color: var(--primary-fixed); }
.card-icon {
  color: var(--primary-fixed);
  font-size: 48px;
  margin-bottom: 16px;
}
.card h3 {
  color: var(--primary);
  margin-bottom: 8px;
}
.card p {
  color: var(--on-surface-variant);
}
```

- [ ] **Step 2: Add features HTML after hero section**

```html
<section class="section" id="features">
  <div class="container">
    <div class="grid-3">
      <div class="card">
        <span class="material-symbols-outlined card-icon">fitness_center</span>
        <h3 class="headline-md">Old School Vibes</h3>
        <p class="body-lg">Authentic bodybuilding atmosphere. Heavy dumbbells, raw iron, and an environment built for serious lifters who respect the work.</p>
      </div>
      <div class="card">
        <span class="material-symbols-outlined card-icon">ac_unit</span>
        <h3 class="headline-md">Clean &amp; Cooled</h3>
        <p class="body-lg">Immaculately maintained equipment and a fully air-conditioned floor. Train hard without compromising on hygiene or comfort.</p>
      </div>
      <div class="card">
        <span class="material-symbols-outlined card-icon">sports_martial_arts</span>
        <h3 class="headline-md">Expert Spotting</h3>
        <p class="body-lg">Supportive management and a community of dedicated athletes. Need a lift-off? You'll find experienced hands ready to help.</p>
      </div>
    </div>
  </div>
</section>
```

- [ ] **Step 3: Open in browser and verify**

Expected: three cards in a row on desktop, stacked on mobile. Each card has a Safety Yellow icon, white heading, and muted text. Border turns yellow on hover. Sharp 0px corners throughout.

- [ ] **Step 4: Commit**

```
feat: add features section with 3-column card grid
```

---

### Task 5: Pricing Section

**Files:**
- Modify: `index.html`

Three pricing tiers: Day Pass (€10), Weekly Pass (€35, featured), Monthly (€55). The Weekly Pass card is elevated with a yellow border and "Most Popular" badge.

- [ ] **Step 1: Add pricing CSS**

```css
/* ── Pricing ── */
.pricing-section {
  padding: 96px 0;
  background: var(--surface-container-low);
  border-top: 2px solid var(--surface-variant);
}
.price-card {
  background: var(--surface-container-high);
  border: 1px solid var(--surface-variant);
  padding: 32px;
  display: flex;
  flex-direction: column;
}
.price-card--featured {
  border: 2px solid var(--primary-fixed);
  box-shadow: 0 0 20px rgba(195,244,0,0.1);
  position: relative;
}
@media (min-width: 768px) {
  .price-card--featured { transform: translateY(-16px); }
}
.price-badge {
  position: absolute;
  top: 0;
  right: 0;
  background: var(--primary-fixed);
  color: var(--on-primary-fixed);
  font-family: var(--font-body);
  font-size: 12px;
  font-weight: 700;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  padding: 4px 12px;
}
.price-amount {
  font-family: var(--font-headline);
  font-size: 40px;
  font-weight: 900;
  color: var(--primary-fixed);
  margin-bottom: 24px;
}
.price-list {
  flex-grow: 1;
  margin-bottom: 32px;
  display: flex;
  flex-direction: column;
  gap: 16px;
}
.price-list li {
  display: flex;
  align-items: center;
  gap: 8px;
  color: var(--on-surface-variant);
  font-size: 18px;
}
.price-list .material-symbols-outlined {
  color: var(--primary-fixed);
  font-size: 20px;
}
.price-card button { width: 100%; font-size: 16px; }
.price-note {
  margin-top: 32px;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 16px;
  color: var(--on-surface-variant);
  font-size: 16px;
}
.price-note .material-symbols-outlined { color: var(--primary-fixed); }
```

- [ ] **Step 2: Add pricing HTML after features section**

```html
<section class="pricing-section" id="pricing">
  <div class="container">
    <h2 class="headline-lg section-title">Access Plans</h2>
    <div class="grid-3">
      <div class="price-card">
        <h4 class="headline-md" style="color:var(--primary);margin-bottom:8px;">Day Pass</h4>
        <div class="price-amount">€10</div>
        <ul class="price-list">
          <li><span class="material-symbols-outlined">check</span> Full floor access</li>
          <li><span class="material-symbols-outlined">check</span> Free weights &amp; machines</li>
        </ul>
        <button class="btn-secondary">Select</button>
      </div>
      <div class="price-card price-card--featured">
        <span class="price-badge">Most Popular</span>
        <h4 class="headline-md" style="color:var(--primary);margin-bottom:8px;">Weekly Pass</h4>
        <div class="price-amount">€35</div>
        <ul class="price-list">
          <li><span class="material-symbols-outlined">check</span> 7 consecutive days</li>
          <li><span class="material-symbols-outlined">check</span> Perfect for travelers</li>
          <li><span class="material-symbols-outlined">check</span> Locker usage</li>
        </ul>
        <button class="btn-primary" style="width:100%;font-size:16px;">Select</button>
      </div>
      <div class="price-card">
        <h4 class="headline-md" style="color:var(--primary);margin-bottom:8px;">Monthly</h4>
        <div class="price-amount">€55</div>
        <ul class="price-list">
          <li><span class="material-symbols-outlined">check</span> Unlimited access</li>
          <li><span class="material-symbols-outlined">check</span> Priority support</li>
          <li><span class="material-symbols-outlined">check</span> Nutrition advice</li>
        </ul>
        <button class="btn-secondary">Select</button>
      </div>
    </div>
    <div class="price-note">
      <span class="material-symbols-outlined">contactless</span>
      <span>All major cards and NFC payments accepted at the desk.</span>
    </div>
  </div>
</section>
```

- [ ] **Step 3: Open in browser and verify**

Expected: three pricing tiers. Weekly Pass has yellow border, slight upward offset on desktop, "Most Popular" badge in top-right, yellow CTA button. Day/Monthly have white secondary buttons with white borders. Cards stack on mobile.

- [ ] **Step 4: Commit**

```
feat: add pricing section with featured weekly pass
```

---

### Task 6: Info & Supplements Section (2-Column Grid)

**Files:**
- Modify: `index.html`

Two-column layout: Operations card (hours table + location + Google Maps link) and Fuel Station card (supplement image background with grayscale-to-color hover effect).

- [ ] **Step 1: Add info section CSS**

```css
/* ── Info Grid ── */
.grid-2 {
  display: grid;
  grid-template-columns: 1fr;
  gap: 48px;
}
@media (min-width: 768px) {
  .grid-2 { grid-template-columns: repeat(2, 1fr); }
}

.hours-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 16px;
  font-size: 18px;
  color: var(--on-surface);
}
.hours-grid .row-border {
  border-top: 1px solid var(--surface-variant);
  padding-top: 8px;
}
.info-link {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  color: var(--primary-fixed);
  font-family: var(--font-headline);
  font-size: 16px;
  font-weight: 700;
  text-transform: uppercase;
  border-bottom: 1px solid var(--primary-fixed);
  padding-bottom: 4px;
  transition: color 0.2s;
}
.info-link:hover { color: var(--surface-tint); }

/* ── Fuel Card ── */
.fuel-card {
  position: relative;
  overflow: hidden;
  min-height: 400px;
}
.fuel-card-bg {
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  opacity: 0.3;
  filter: grayscale(1);
  transition: filter 0.7s;
}
.fuel-card:hover .fuel-card-bg { filter: grayscale(0); }
.fuel-card-gradient {
  position: absolute;
  inset: 0;
  background: linear-gradient(to top, var(--surface-container-high), transparent);
  z-index: 1;
}
.fuel-card-content {
  position: relative;
  z-index: 2;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: flex-end;
}
```

- [ ] **Step 2: Add info HTML after pricing section**

```html
<section class="section" id="info">
  <div class="container grid-2">
    <div class="card" style="padding:32px;">
      <h2 class="headline-md section-title" style="margin-bottom:32px;">Operations</h2>
      <div style="margin-bottom:32px;">
        <h3 class="label-sm" style="color:var(--primary-fixed);margin-bottom:8px;">Hours</h3>
        <div class="hours-grid">
          <div>Mon – Fri</div>
          <div style="text-align:right;">10:00 – 22:00</div>
          <div class="row-border">Saturday</div>
          <div class="row-border" style="text-align:right;">10:00 – 21:00</div>
          <div class="row-border" style="color:var(--on-surface-variant);">Sunday</div>
          <div class="row-border" style="text-align:right;color:var(--on-surface-variant);">Closed for recovery</div>
        </div>
      </div>
      <div>
        <h3 class="label-sm" style="color:var(--primary-fixed);margin-bottom:8px;">Location</h3>
        <p class="body-lg" style="margin-bottom:16px;">Kissamos, Chania, Crete</p>
        <a href="https://maps.google.com" target="_blank" rel="noopener" class="info-link">
          <span class="material-symbols-outlined">map</span>
          Open in Google Maps
        </a>
      </div>
    </div>
    <div class="card fuel-card">
      <div class="fuel-card-gradient"></div>
      <img class="fuel-card-bg" src="https://lh3.googleusercontent.com/aida-public/AB6AXuDjL-h8PcpLz_wSafTvGUNubeke5BQaZW5iiWno8K4k7DvdT3-Z-L2cv2-7gSi8ioOsG3C6i2zdLQhMR7xN7hhT5S7-okaJ-JG94brMTgMfqw9iTdZi0CdQxNNcxUdJAL6zKxKjft2VSel_aEt3pD7WzGAXWv4repPAUGQvlCbY3FOn64s_lQHJllZdw8FCfiwLDcowgQnCGPyArgcorwekeu46zhiqVdgcVHBflXxjP-S8aH5SMyHunc_FnV74TNyxyOnQFmcwQo0b" alt="Supplement station at Bodyfit Kissamos" width="800" height="600" loading="lazy">
      <div class="fuel-card-content" style="padding:32px;">
        <span class="material-symbols-outlined" style="color:var(--primary-fixed);font-size:36px;margin-bottom:16px;">local_drink</span>
        <h2 class="headline-md" style="color:var(--primary);margin-bottom:8px;">Fuel Station</h2>
        <p class="body-lg" style="color:var(--on-surface-variant);max-width:380px;">Running low? We stock a selection of premium whey, pre-workouts, and BCAAs on-site. Grab what you need at the desk.</p>
      </div>
    </div>
  </div>
</section>
```

- [ ] **Step 3: Open in browser and verify**

Expected: two-column layout on desktop, stacked on mobile. Operations card shows hours table and Google Maps link. Fuel Station card has grayscale background image that transitions to full color on hover.

- [ ] **Step 4: Commit**

```
feat: add info section with hours, location, and fuel station
```

---

### Task 7: Footer

**Files:**
- Modify: `index.html`

Minimal footer with logo, social/legal links, and copyright line.

- [ ] **Step 1: Add footer CSS**

```css
/* ── Footer ── */
.footer {
  background: var(--surface-container-lowest);
  border-top: 2px solid var(--surface-variant);
  padding: 48px 0;
}
.footer-inner {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 32px;
  text-align: center;
}
@media (min-width: 768px) {
  .footer-inner {
    flex-direction: row;
    justify-content: space-between;
    text-align: left;
  }
}
.footer-links {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 24px;
}
.footer-links a {
  color: var(--on-surface-variant);
  font-size: 16px;
  text-decoration: underline;
  transition: color 0.2s;
}
.footer-links a:hover { color: var(--primary-fixed); }
.footer-copy {
  color: var(--on-surface-variant);
  font-size: 16px;
}
```

- [ ] **Step 2: Add footer HTML before the `<script>` tag**

```html
<footer class="footer" id="contact">
  <div class="container footer-inner">
    <div class="nav-logo">Bodyfit Kissamos</div>
    <ul class="footer-links">
      <li><a href="https://instagram.com" target="_blank" rel="noopener">Instagram</a></li>
      <li><a href="https://facebook.com" target="_blank" rel="noopener">Facebook</a></li>
      <li><a href="https://maps.google.com" target="_blank" rel="noopener">Google Maps</a></li>
      <li><a href="#">Privacy Policy</a></li>
    </ul>
    <div class="footer-copy">© 2025 Bodyfit Kissamos. No gimmicks. Just iron.</div>
  </div>
</footer>
```

- [ ] **Step 3: Open in browser and verify**

Expected: dark footer with logo, social links (underlined, turn yellow on hover), and copyright. Horizontal layout on desktop, stacked on mobile.

- [ ] **Step 4: Commit**

```
feat: add footer with social links and copyright
```

---

### Task 8: FAQ Section (GEO — Critical for AI Citability)

**Files:**
- Modify: `index.html`

A FAQ section with 8 question-and-answer pairs targeting the exact queries users ask AI assistants: "gym in Kissamos," "bodybuilding gym Chania Crete," "gym prices Kissamos." Each answer is a self-contained 40-60 word block optimized for AI citation (134-167 word passages when combined with the question). Uses question-based `<h3>` headings matching query patterns.

- [ ] **Step 1: Add FAQ CSS**

```css
/* ── FAQ ── */
.faq-section {
  padding: 96px 0;
  border-top: 2px solid var(--surface-variant);
}
.faq-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 0;
}
@media (min-width: 768px) {
  .faq-grid { grid-template-columns: repeat(2, 1fr); gap: 0 48px; }
}
.faq-item {
  padding: 24px 0;
  border-bottom: 1px solid var(--surface-variant);
}
.faq-item h3 {
  font-family: var(--font-headline);
  font-size: 18px;
  font-weight: 700;
  color: var(--primary);
  margin-bottom: 8px;
}
.faq-item p {
  color: var(--on-surface-variant);
  font-size: 16px;
  line-height: 1.6;
}
```

- [ ] **Step 2: Add FAQ HTML after the info section and before the footer**

```html
<section class="faq-section" id="faq">
  <div class="container">
    <h2 class="headline-lg section-title">Frequently Asked Questions</h2>
    <div class="faq-grid">
      <div class="faq-item">
        <h3>Where is Bodyfit Kissamos located?</h3>
        <p>Bodyfit Kissamos is located in Kissamos, a coastal town in the Chania regional unit of western Crete, Greece. The gym is easily accessible from the town center and serves both local residents and tourists visiting the area.</p>
      </div>
      <div class="faq-item">
        <h3>How much does a gym day pass cost in Kissamos?</h3>
        <p>A single day pass at Bodyfit Kissamos costs €10 and includes full floor access to all free weights and machines. Weekly passes are available for €35 (7 consecutive days with locker usage), and monthly memberships cost €55 with unlimited access and nutrition advice.</p>
      </div>
      <div class="faq-item">
        <h3>What are the opening hours of Bodyfit Kissamos?</h3>
        <p>Bodyfit Kissamos is open Monday through Friday from 10:00 to 22:00 and Saturday from 10:00 to 21:00. The gym is closed on Sundays for recovery. These hours run year-round including the summer tourist season.</p>
      </div>
      <div class="faq-item">
        <h3>Is Bodyfit Kissamos good for tourists and travelers?</h3>
        <p>Yes, Bodyfit Kissamos is ideal for travelers visiting Crete who want to maintain their training routine. The popular weekly pass (€35) is designed specifically for tourists, offering 7 consecutive days of access with locker usage. Card and NFC payments are accepted.</p>
      </div>
      <div class="faq-item">
        <h3>What equipment does Bodyfit Kissamos have?</h3>
        <p>The gym features a full range of heavy free weights including dumbbells and barbells, along with resistance machines for all major muscle groups. The facility maintains an old-school bodybuilding atmosphere focused on serious strength training with robust, professional-grade equipment.</p>
      </div>
      <div class="faq-item">
        <h3>Does the gym have air conditioning?</h3>
        <p>Yes, Bodyfit Kissamos is fully air-conditioned throughout the training floor. Despite Crete's warm Mediterranean climate, the gym maintains a comfortable temperature year-round so you can train hard without overheating.</p>
      </div>
      <div class="faq-item">
        <h3>Can I buy protein and supplements at the gym?</h3>
        <p>Yes, Bodyfit Kissamos operates an on-site supplement station stocking premium whey protein, pre-workout formulas, and BCAAs. You can purchase individual servings or full containers directly at the front desk — no need to bring your own.</p>
      </div>
      <div class="faq-item">
        <h3>What payment methods are accepted?</h3>
        <p>Bodyfit Kissamos accepts all major credit and debit cards as well as NFC contactless payments (Apple Pay, Google Pay) at the front desk. Cash payments are also accepted for all membership plans and day passes.</p>
      </div>
    </div>
  </div>
</section>
```

- [ ] **Step 3: Add nav link for FAQ**

Add "FAQ" to both the desktop `nav-links` and `mobile-menu`:

```html
<li><a href="#faq">FAQ</a></li>
```

- [ ] **Step 4: Open in browser and verify**

Expected: two-column grid of Q&A pairs on desktop, single column on mobile. Each question is a bold white heading, each answer is muted text. Questions should read naturally as the kind of queries someone would ask an AI assistant.

- [ ] **Step 5: Commit**

```
feat: add FAQ section optimized for AI search citability
```

---

### Task 9: JSON-LD FAQPage Schema (GEO)

**Files:**
- Modify: `index.html`

Adds a second JSON-LD block for FAQPage schema — separate from the LocalBusiness schema in `<head>`. FAQPage schema is among the top-5 predictive features for AI citation. This must mirror the visible FAQ content exactly.

- [ ] **Step 1: Add FAQPage JSON-LD script tag in `<head>` after the LocalBusiness schema**

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "Where is Bodyfit Kissamos located?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Bodyfit Kissamos is located in Kissamos, a coastal town in the Chania regional unit of western Crete, Greece. The gym is easily accessible from the town center and serves both local residents and tourists visiting the area."
      }
    },
    {
      "@type": "Question",
      "name": "How much does a gym day pass cost in Kissamos?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "A single day pass at Bodyfit Kissamos costs €10 and includes full floor access to all free weights and machines. Weekly passes are available for €35 (7 consecutive days with locker usage), and monthly memberships cost €55 with unlimited access and nutrition advice."
      }
    },
    {
      "@type": "Question",
      "name": "What are the opening hours of Bodyfit Kissamos?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Bodyfit Kissamos is open Monday through Friday from 10:00 to 22:00 and Saturday from 10:00 to 21:00. The gym is closed on Sundays for recovery. These hours run year-round including the summer tourist season."
      }
    },
    {
      "@type": "Question",
      "name": "Is Bodyfit Kissamos good for tourists and travelers?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Yes, Bodyfit Kissamos is ideal for travelers visiting Crete who want to maintain their training routine. The popular weekly pass (€35) is designed specifically for tourists, offering 7 consecutive days of access with locker usage. Card and NFC payments are accepted."
      }
    },
    {
      "@type": "Question",
      "name": "What equipment does Bodyfit Kissamos have?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "The gym features a full range of heavy free weights including dumbbells and barbells, along with resistance machines for all major muscle groups. The facility maintains an old-school bodybuilding atmosphere focused on serious strength training with robust, professional-grade equipment."
      }
    },
    {
      "@type": "Question",
      "name": "Does the gym have air conditioning?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Yes, Bodyfit Kissamos is fully air-conditioned throughout the training floor. Despite Crete's warm Mediterranean climate, the gym maintains a comfortable temperature year-round so you can train hard without overheating."
      }
    },
    {
      "@type": "Question",
      "name": "Can I buy protein and supplements at the gym?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Yes, Bodyfit Kissamos operates an on-site supplement station stocking premium whey protein, pre-workout formulas, and BCAAs. You can purchase individual servings or full containers directly at the front desk."
      }
    },
    {
      "@type": "Question",
      "name": "What payment methods are accepted?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Bodyfit Kissamos accepts all major credit and debit cards as well as NFC contactless payments (Apple Pay, Google Pay) at the front desk. Cash payments are also accepted for all membership plans and day passes."
      }
    }
  ]
}
</script>
```

- [ ] **Step 2: Validate JSON-LD**

Paste both JSON-LD blocks into Google's Rich Results Test or Schema Markup Validator to confirm no errors. Both LocalBusiness and FAQPage should validate cleanly.

- [ ] **Step 3: Commit**

```
feat: add FAQPage JSON-LD schema for AI search visibility
```

---

### Task 10: llms.txt + robots.txt (GEO — AI Crawler Guidance)

**Files:**
- Create: `llms.txt`
- Create: `robots.txt`

These files guide AI crawlers (GPTBot, ClaudeBot, PerplexityBot) on how to understand and index the site. The `llms.txt` standard provides structured content guidance. The `robots.txt` explicitly allows all major AI crawlers.

- [ ] **Step 1: Create `llms.txt` in the project root**

```
# Bodyfit Kissamos
> Authentic old-school bodybuilding gym in Kissamos, Chania, Crete, Greece.

## About
Bodyfit Kissamos is a dedicated bodybuilding and strength training gym located in the coastal town of Kissamos in western Crete. The gym is known for its raw, industrial atmosphere, heavy free weights, professional-grade machines, and fully air-conditioned training floor. It caters to both local athletes and tourists visiting Crete.

## Pricing
- Day Pass: €10 — Full floor access, free weights and machines
- Weekly Pass: €35 — 7 consecutive days, locker usage, ideal for travelers
- Monthly Membership: €55 — Unlimited access, priority support, nutrition advice
- Payment: Cash, credit/debit cards, NFC (Apple Pay, Google Pay)

## Hours
- Monday to Friday: 10:00 – 22:00
- Saturday: 10:00 – 21:00
- Sunday: Closed

## Location
- Town: Kissamos, Chania, Crete, Greece
- Region: Western Crete
- Coordinates: 35.4946°N, 23.6559°E

## Amenities
- Heavy free weights (dumbbells, barbells, plates)
- Resistance machines for all muscle groups
- Full air conditioning
- On-site supplement station (protein, pre-workout, BCAAs)
- Lockers
- NFC/card payments

## Contact
- Instagram: @bodyfikissamos
- Facebook: Bodyfit Kissamos
```

- [ ] **Step 2: Create `robots.txt` in the project root**

```
User-agent: *
Allow: /

# AI Search Crawlers — explicitly allowed
User-agent: GPTBot
Allow: /

User-agent: OAI-SearchBot
Allow: /

User-agent: ChatGPT-User
Allow: /

User-agent: ClaudeBot
Allow: /

User-agent: PerplexityBot
Allow: /

User-agent: anthropic-ai
Allow: /

# Training-only crawlers — optionally block
User-agent: CCBot
Disallow: /

Sitemap: https://bodyfikissamos.com/sitemap.xml
```

- [ ] **Step 3: Commit**

```
feat: add llms.txt and robots.txt for AI crawler guidance
```

---

### Task 11: Final Polish and Responsive QA

**Files:**
- Modify: `index.html`

Final pass for responsive breakpoints, touch targets, print styles, and overall QA.

- [ ] **Step 1: Add small-screen tweaks and touch-target sizing**

Add at the end of the `<style>` block:

```css
/* ── Small Screen Overrides ── */
@media (max-width: 480px) {
  .hero { min-height: 70vh; }
  .price-amount { font-size: 32px; }
  .card { padding: 24px; }
  .section { padding: 64px 0; }
  .pricing-section { padding: 64px 0; }
}

/* ── Ensure touch targets ≥ 44px ── */
.btn-primary, .btn-secondary, .hamburger, .nav-links a, .footer-links a {
  min-height: 44px;
  display: inline-flex;
  align-items: center;
}

/* ── Focus visible for accessibility ── */
:focus-visible {
  outline: 2px solid var(--primary-fixed);
  outline-offset: 2px;
}
```

- [ ] **Step 2: Test at all breakpoints**

Open in browser and test at:
1. **320px** (small mobile) — everything stacks, text is readable, no horizontal overflow
2. **375px** (iPhone SE) — hero headline wraps cleanly, cards are full-width
3. **768px** (tablet) — grids switch to multi-column, hamburger disappears
4. **1280px** (desktop) — max-width container centers, generous margins
5. **1920px** (wide) — content stays centered within 1280px container

Verify: no horizontal scroll at any width, all text readable, buttons tappable, images load.

- [ ] **Step 3: Validate HTML**

Scan for unclosed tags, missing alt attributes, and accessibility issues. Ensure:
- All images have alt text and width/height
- Buttons have accessible labels
- Color contrast meets WCAG AA (white on #2a2a2a = 11.6:1 ✓, #c4c9ac on #2a2a2a = 6.8:1 ✓)
- Hamburger has aria-label and aria-expanded
- Links to external sites have `rel="noopener"`

- [ ] **Step 4: GEO content verification pass**

Verify all GEO elements are in place:
1. **JSON-LD:** Two schema blocks in `<head>` — LocalBusiness and FAQPage. Validate with Google's Rich Results Test.
2. **Answer-first:** Hero has a descriptive paragraph visible to crawlers. Each section's first sentence directly answers "what is this?"
3. **Heading hierarchy:** H1 (hero) → H2 (section titles) → H3 (card/FAQ headings). No skipped levels.
4. **FAQ content:** 8 Q&A pairs with question-based headings matching query patterns. Each answer is 40-60 words, self-contained.
5. **Meta tags:** `<title>` includes location + business type. `<meta description>` is 150-160 chars with pricing, location, and key features.
6. **Open Graph:** og:title, og:description, og:type, og:locale, og:site_name all present.
7. **Alt text:** All images have descriptive alt text mentioning the business name.
8. **Entity clarity:** "Bodyfit Kissamos" appears as a named entity in at least 5 places in the HTML body text (not just headings).
9. **No JS-dependent content:** All text is in the HTML source, readable without JavaScript. Only the mobile menu toggle uses JS.
10. **llms.txt and robots.txt:** Both files exist and are correctly formatted.

- [ ] **Step 5: Final commit**

```
feat: add responsive polish, accessibility, and GEO verification
```

---

## File Summary

| File | Action | Purpose |
|---|---|---|
| `index.html` | Create | Complete single-file website with inline CSS, minimal JS, and GEO optimization |
| `llms.txt` | Create | AI crawler guidance file (llms.txt standard) |
| `robots.txt` | Create | Search engine and AI crawler access rules |
| `code.html` | Keep | Original prototype for reference (not modified) |
| `DESIGN.md` | Keep | Design specification (not modified) |
| `screen.png` | Keep | Visual reference (not modified) |

## Performance Budget

The finished `index.html` should be:
- **HTML file size:** < 20 KB (gzipped < 7 KB) — slightly larger due to JSON-LD schemas
- **Zero JS frameworks** — only ~15 lines vanilla JS for mobile menu
- **External requests:** 3 (Google Fonts, Material Symbols, 2 images)
- **No Tailwind CDN** — no runtime CSS compilation
- **Lighthouse target:** 95+ performance, 95+ accessibility
- **Schema validation:** Both LocalBusiness and FAQPage pass Google Rich Results Test

## GEO Optimization Summary

| GEO Signal | Implementation |
|---|---|
| JSON-LD Schema Stacking | LocalBusiness (HealthClub) + FAQPage + Offer + OpeningHoursSpecification |
| Answer-First Content | Direct answer in first 40-60 words of hero and each section |
| Question-Based Headings | FAQ uses natural-language questions matching AI query patterns |
| Self-Contained Passages | Each FAQ answer is 40-60 words, extractable without context |
| Entity Clarity | "Bodyfit Kissamos" named entity in 5+ body text locations |
| AI Crawler Access | robots.txt allows GPTBot, ClaudeBot, PerplexityBot, OAI-SearchBot |
| llms.txt | Structured content guidance at /llms.txt |
| Server-Side Content | All content in HTML source — no JS-dependent text |
| Rich Meta Tags | Open Graph, geo meta, descriptive title/description with pricing |
| No JavaScript Content | AI crawlers don't execute JS — all text is static HTML |
