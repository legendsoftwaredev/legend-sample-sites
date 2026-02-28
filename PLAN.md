# PLAN.md — Legend Media & Print Portfolio Landing Page

## Overview

A single-page portfolio showcase for Legend Media & Print's sample website projects. The page must exactly replicate the design language of the main Legend Media & Print website: pure black background, neon lime green (#c6ff00) accents, GlitchGoblin-style headings (with Share Tech Mono fallback), monospace body text, glowing neon text-shadows, and dark card UI with green border glow on hover.

**Deliverable:** One `index.html` file with all CSS embedded inline (no external stylesheets).

---

## Design Tokens

| Token | Value |
|---|---|
| Background | `#000000` |
| Muted Background / Cards | `#111111` |
| Primary Accent | `#c6ff00` |
| Secondary Accent | `#8eff00` |
| Text | `#ffffff` |
| Border | `rgba(198, 255, 0, 0.2)` |
| Gradient | `linear-gradient(135deg, #c6ff00 0%, #8eff00 100%)` |
| Heading Font | `'GlitchGoblin', 'Share Tech Mono', monospace` |
| Body Font | `'Courier New', Courier, monospace` |
| Button Border Radius | `50px` |
| Card Border Radius | `15px` |
| Neon Glow Text-Shadow | `0 0 7px #fff, 0 0 10px #fff, 0 0 21px #fff, 0 0 42px #c6ff00, 0 0 82px #c6ff00, 0 0 92px #c6ff00` |
| Card Hover Box-Shadow | `0 0 15px rgba(198, 255, 0, 0.4), 0 0 30px rgba(198, 255, 0, 0.1)` |

---

## External Resources

- **Google Font:** `Share Tech Mono` — loaded via `<link>` from Google Fonts (sole external request)
- **No external CSS frameworks.** All styles embedded in `<style>` within `index.html`.
- **No JavaScript frameworks.** Vanilla JS only (for category filtering).

---

## Page Sections (Top → Bottom)

### 1. Navigation Bar

- **Position:** `fixed` top, full width, `z-index: 1000`
- **Style:** `#000000` background, `backdrop-filter: blur(10px)`, `border-bottom: 1px solid rgba(198, 255, 0, 0.2)`
- **Content:**
  - Left: "LEGEND MEDIA & PRINT" wordmark (Share Tech Mono, neon green, glow)
  - Right: "← Back to Main Site" link → `https://legendsoftwaredev.github.io/legendmediaprint/`
- **Mobile:** Stays single row; wordmark shrinks, link stays visible (no hamburger needed for two items)

---

### 2. Hero Section

- **Background:** `#000000` with subtle radial gradient or faint grid-line pattern (CSS only) for depth
- **Headline:** `OUR WORK SPEAKS FOR ITSELF` — large, uppercase, Share Tech Mono, neon glow text-shadow
- **Subtitle:** "Legend Media & Print builds bold, high-converting websites for businesses across every industry. Browse our portfolio below."
- **CTA Button:** "Visit Legend Media & Print" → links to `https://legendsoftwaredev.github.io/legendmediaprint/`
  - Style: transparent bg, `2px solid #c6ff00`, `border-radius: 50px`, green text, hover fills with gradient
- **Spacing:** Generous vertical padding (`120px` top to clear fixed nav, `80px` bottom)

---

### 3. Category Filter Bar

- **Position:** Sticky below hero (or inline above the grid)
- **Style:** Row of pill-shaped filter buttons on `#111111` strip with green top/bottom borders (mirrors the stats-section pattern from the main site)
- **Buttons:** One per category + "All" (selected by default)
  - `All` | `Home Services` | `Construction` | `Food & Hospitality` | `Health & Wellness` | `Professional Services` | `Technology` | `Personal Care`
- **Active state:** Filled gradient background, dark text
- **Inactive state:** Transparent, green border, green text
- **Behavior (vanilla JS):**
  - Clicking a category shows only matching cards (CSS class toggle, no page reload)
  - "All" resets to show every card
  - Smooth fade/scale transition on show/hide

---

### 4. Portfolio Grid

- **Layout:** CSS Grid, responsive
  - Desktop (≥1024px): 3 columns
  - Tablet (≥640px): 2 columns
  - Mobile (<640px): 1 column
- **Gap:** `30px`
- **Container:** Max-width `1200px`, centered

#### Card Spec (×12)

Each card is a `<div>` (or `<article>`) with:

| Element | Details |
|---|---|
| Category Tag | Small uppercase pill label top-left (e.g., "CONSTRUCTION"), green border, green text, `border-radius: 50px` |
| Business Name | `<h3>`, Share Tech Mono, `#c6ff00`, neon glow text-shadow |
| Description | One-line, `#ffffff` at 80% opacity, Courier New |
| View Site Button | "View Site →", same pill button style as hero CTA, links to the GitHub Pages URL, `target="_blank"` |

**Card Styling:**
- Background: `#111111`
- Border: `1px solid rgba(198, 255, 0, 0.2)`
- Border-radius: `15px`
- Padding: `30px`
- Transition: `transform 0.3s, box-shadow 0.3s`
- **Hover:** `transform: translateY(-5px)`, `box-shadow: 0 0 15px rgba(198, 255, 0, 0.4), 0 0 30px rgba(198, 255, 0, 0.1)`

#### The 12 Sites

| # | Business Name | Category | Description | URL |
|---|---|---|---|---|
| 1 | ComfortAir HVAC | Home Services | Heating, cooling & ventilation | `https://legendsoftwaredev.github.io/comfortair-hvac-demo/` |
| 2 | Ironclad Builders | Construction | General contracting & construction | `https://legendsoftwaredev.github.io/ironclad-builders-demo/` |
| 3 | GreenScape Outdoors | Construction | Landscaping & lawn care | `https://legendsoftwaredev.github.io/greenscape-landscaping-demo/` |
| 4 | Savor & Serve Catering | Food & Hospitality | Event catering & private dining | `https://legendsoftwaredev.github.io/savor-serve-catering-demo/` |
| 5 | The Copper Table | Food & Hospitality | Upscale dining restaurant | `https://legendsoftwaredev.github.io/copper-table-restaurant-demo/` |
| 6 | Bright Smile Dental | Health & Wellness | General & cosmetic dentistry | `https://legendsoftwaredev.github.io/dental-practice-demo/` |
| 7 | Glow Aesthetics MedSpa | Health & Wellness | Botox, fillers & skincare | `https://legendsoftwaredev.github.io/medspa-demo/` |
| 8 | Summit Financial Group | Professional Services | Tax, bookkeeping & financial consulting | `https://legendsoftwaredev.github.io/accounting-firm-demo/` |
| 9 | Sterling & Associates | Professional Services | Business law & civil litigation | `https://legendsoftwaredev.github.io/law-firm-demo/` |
| 10 | SwiftPay Solutions | Technology | Payment processing & POS systems | `https://legendsoftwaredev.github.io/payment-fintech-demo/` |
| 11 | Sharp Cuts Barbershop | Personal Care | Haircuts, beard trims & grooming | `https://legendsoftwaredev.github.io/sharp-cuts-barber-demo/` |
| 12 | Luxe Hair Studio | Personal Care | Cuts, color, balayage & bridal styling | `https://legendsoftwaredev.github.io/luxe-hair-salon-demo/` |

---

### 5. CTA Section

- **Background:** `#111111` with green top and bottom borders (`1px solid rgba(198, 255, 0, 0.2)`) — mirrors the stats-section pattern
- **Headline:** `READY TO GET YOUR OWN CUSTOM WEBSITE?` — neon glow, centered
- **Subtext:** "Let Legend Media & Print build a website that works as hard as you do."
- **CTA Button:** "Get Started" → links to `https://legendsoftwaredev.github.io/legendmediaprint/#contact` (or main site contact section)
  - Same pill button style; on hover fills with gradient

---

### 6. Footer

- **Background:** `#111111`
- **Border-top:** `1px solid rgba(198, 255, 0, 0.2)`
- **Content (centered, stacked):**
  - "LEGEND MEDIA & PRINT" wordmark (Share Tech Mono, neon green, smaller glow)
  - "Websites That Work As Hard As You Do" tagline (white, 70% opacity)
  - Link: "← Back to Main Site" → `https://legendsoftwaredev.github.io/legendmediaprint/`
  - Copyright: `© 2025 Legend Media & Print. All rights reserved.`
- **Padding:** `60px` vertical

---

## Responsive Breakpoints

| Breakpoint | Grid Cols | Font Scale | Padding |
|---|---|---|---|
| ≥1024px (Desktop) | 3 | 100% | Standard |
| 640px–1023px (Tablet) | 2 | 90% | Reduced |
| <640px (Mobile) | 1 | 85% | Compact |

- Filter bar wraps to 2 rows on mobile
- Hero headline scales down (`clamp()` or media queries)
- Cards go full-width on mobile with less padding

---

## Vanilla JavaScript (Minimal)

1. **Category Filter** — Event listeners on filter buttons; toggle a `data-category` attribute on cards; use CSS class `.hidden { display: none }` with a fade transition
2. **Smooth Scroll** — `scroll-behavior: smooth` in CSS (no JS needed)
3. **No other JS required**

---

## File Structure

```
SAMPLE SITES/
└── index.html    ← Single file, all CSS in <style>, minimal JS in <script>
```

No additional files. No external CSS. One Google Font `<link>` tag.

---

## Implementation Checklist

- [ ] Create `index.html` skeleton with `<head>` (meta, Google Font link, embedded `<style>`)
- [ ] CSS: Reset, custom properties (design tokens), typography, nav, hero, filter bar, grid, cards, CTA, footer
- [ ] CSS: Neon glow text-shadow mixin on all headings
- [ ] CSS: Card hover lift + green box-shadow
- [ ] CSS: Responsive media queries (mobile-first)
- [ ] CSS: Button styles (transparent, green border, pill shape, hover gradient fill)
- [ ] HTML: Fixed nav bar
- [ ] HTML: Hero section with headline, subtitle, CTA
- [ ] HTML: Category filter bar with 8 buttons
- [ ] HTML: Portfolio grid with 12 cards (each with category tag, name, description, View Site button)
- [ ] HTML: CTA section
- [ ] HTML: Footer
- [ ] JS: Category filter toggle logic
- [ ] Test: All 12 links open correct GitHub Pages URLs
- [ ] Test: Responsive at 320px, 640px, 1024px, 1440px
- [ ] Test: Neon glow renders on headings
- [ ] Test: Cards lift and glow on hover
