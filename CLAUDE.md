# CLAUDE.md — Review Angel (리뷰천사)

## Project Overview

Review Angel (리뷰천사) is a **static HTML/CSS landing page** for a B2B SaaS service targeting Korean e-commerce sellers. The service provides AI-powered review response automation combined with human CS phone outreach across major Korean marketplaces (Coupang, Naver Smart Store, 11st, Baemin, Cafe24, Shopify).

**Tagline**: "AI가 답변을 쓰고, 사람이 마음을 잡습니다" (AI writes the answer, humans capture the heart)

**Company**: 루다(Ruda) | 리뷰1004

## Repository Structure

```
review-angel/
├── CLAUDE.md          # This file — AI assistant guide
├── index.html         # Single-page landing site (1,167 lines, HTML + embedded CSS)
└── angel-logo.png     # Logo asset used as favicon and OG image
```

This is a minimal, zero-dependency static site. There is **no JavaScript**, **no build process**, **no package.json**, and **no test infrastructure**.

## Tech Stack

- **HTML5** — Semantic markup, Open Graph & Twitter Card meta tags
- **CSS3** — Embedded in `<style>` within `index.html`; uses CSS custom properties, CSS Grid, Flexbox
- **Google Fonts** — `Noto Sans KR` loaded via `@import` in the `<style>` block
- **No JavaScript** — FAQ accordion uses native `<details>/<summary>` elements
- **No frameworks or libraries**

## Design System (CSS Variables)

All colors are defined as CSS custom properties in `:root`:

| Variable        | Value     | Usage                        |
|-----------------|-----------|------------------------------|
| `--peach`       | `#FF9B7B` | Primary accent, buttons, CTAs |
| `--peach-light` | `#FFD4C4` | Hover states, light accents   |
| `--peach-bg`    | `#FFF8F5` | Background tint               |
| `--gold`        | `#FFD166` | Secondary accent, highlights  |
| `--gold-light`  | `#FFF0C9` | Light gold backgrounds        |
| `--dark`        | `#2D2D2D` | Body text                     |
| `--gray`        | `#777`    | Secondary text                |
| `--light-gray`  | `#F7F7F7` | Section backgrounds           |
| `--white`       | `#FFFFFF` | Base background               |
| `--red`         | `#FF4D4D` | Negative review stars         |

## Page Sections (in order)

1. **Navigation** (`<nav>`) — Fixed top bar with logo and CTA button
2. **Hero** (`<section class="hero">`) — Main headline, subtext, dual CTA buttons
3. **Stats Bar** (`<div class="stats-bar">`) — Key metrics (response time, satisfaction, review increase)
4. **Problem Cards** (`<div class="problem-grid">`) — 3-column grid highlighting seller pain points
5. **Differentiation** (`<div class="diff-section">`) — Dark-themed section with 4 key advantages
6. **Comparison Table** (`<table class="compare-table">`) — Feature comparison vs competitors
7. **How It Works** (`<div class="steps">`) — 4-step process flow
8. **AI Demo** (`<div class="demo-grid">`) — Example responses for good/neutral/bad reviews
9. **ROI Metrics** (`<div class="roi-grid">`) — Performance metrics grid
10. **Testimonials** (`<div class="testimonial">`) — Customer quotes
11. **FAQ** (`<div class="faq-list">`) — Accordion using `<details>` elements
12. **Pricing** (`<div class="pricing-grid">`) — 3-tier cards (Starter/Standard/Premium)
13. **Final CTA** (`<div class="cta-section">`) — Conversion section with KakaoTalk link
14. **Footer** (`<footer>`) — Company info

### Section wrapper patterns

The page uses two alternating wrapper patterns for sections:
- `<div class="section-wrap">` — Standard white background sections
- `<div class="section-bg">` wrapping `<div class="section-wrap">` — Alternate gray (`--light-gray`) background sections
- Each section typically has a `<div class="section-title">` containing `<h2>` and `<p>` for the header

## Responsive Design

- **Desktop-first** layout with a single breakpoint at `768px`
- Mobile styles are defined in a `@media (max-width: 768px)` block near the end of the CSS
- Grid layouts collapse from multi-column to single-column on mobile
- Navigation adjusts font size and padding for mobile

## Deployment

- **Hosting**: GitHub Pages (static file serving)
- **No build step** — Files are served directly as committed
- **Deployment trigger**: Pushing to the `main` branch triggers GitHub Pages rebuild

## Development Workflow

Since this is a static HTML file:

1. Edit `index.html` directly
2. Preview locally by opening `index.html` in a browser
3. Commit and push to deploy

### No build/test/lint commands exist — the project has zero tooling.

## Conventions for AI Assistants

### When editing `index.html`:

- **Preserve the CSS variable system** — Always use `var(--peach)`, `var(--dark)`, etc. instead of hardcoded colors
- **Keep all CSS embedded** in the `<style>` tag within `index.html` — do not extract to separate files unless explicitly asked
- **Maintain responsive design** — Any new sections must include mobile styles in the `@media (max-width: 768px)` block
- **No JavaScript unless requested** — The site is intentionally JS-free for performance
- **Korean language** — All user-facing text is in Korean (한국어). Keep this consistent
- **Section wrapper pattern** — New sections should use the `section-wrap` / `section-bg` wrapper pattern with `section-title` headers (see "Section wrapper patterns" above)
- **Semantic HTML** — Use appropriate elements (`<section>`, `<details>`, `<h1>`–`<h3>`, etc.)

### CSS structure within `index.html`:

The embedded CSS is organized in this order:
1. Google Fonts `@import`
2. Reset (`* { margin: 0; ... }`)
3. `:root` CSS custom properties
4. Base styles (`body`)
5. Component styles in page order (nav → hero → stats → problems → ... → footer)
6. `@media (max-width: 768px)` responsive overrides (at the end)

### Content guidelines:

- **Pricing** is in Korean Won (₩) with comma formatting (e.g., `10만원`)
- **Platform names** should match exact Korean marketplace names (쿠팡, 스마트스토어, etc.)
- **CTA links** point to KakaoTalk open chat (`https://open.kakao.com/`)
- **Brand voice**: Professional but warm, emphasizing the hybrid AI + human approach
- **Pricing tiers**: Starter (5만원/월), Standard (10만원/월), Premium (25만원/월) — all with "첫 달 50% OFF"

### Git practices:

- `main` is the production branch (GitHub Pages source)
- `master` exists as a local branch
- Feature branches use the `claude/` prefix
- Commit messages can be in Korean or English
- Co-authoring with AI tools is acceptable (already established in history)

## External Dependencies

| Dependency | URL | Purpose |
|------------|-----|---------|
| Google Fonts | `fonts.googleapis.com` | Noto Sans KR typeface (weights: 400–900) |

No npm packages, no CDN libraries, no external JS.

## SEO & Metadata

The page includes:
- `<title>` and `<meta name="description">` tags
- `<meta name="keywords">` for Korean search terms
- Open Graph tags (`og:title`, `og:description`, `og:image`, `og:type`, `og:locale`)
- Twitter Card tags (`twitter:card`, `twitter:title`, `twitter:description`)
- Favicon set to `angel-logo.png`
- Korean locale (`lang="ko"`, `og:locale="ko_KR"`)
