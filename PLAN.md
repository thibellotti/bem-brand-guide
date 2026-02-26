# Bem.ai Brand Expansion Guide — Implementation Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Create 10 pixel-perfect HTML/CSS pages (1920x1080) that serve as visual reference for the Figma brand guide delivery.

**Architecture:** Static HTML pages with inline CSS. Each page is a standalone 1920x1080 artboard. Shared CSS variables for tokens. Assets from existing Figma export.

**Tech Stack:** HTML, CSS (no JS needed), PP Neue Corp font (via @font-face or fallback to system)

---

## Design Tokens

```css
/* Colors */
--black: #000000;
--near-black: #0A0A0A;
--white: #FFFFFF;
--gray-60: #999999;
--gray-40: #666666;
--blue: #2c3ab4;
--blue-bright: #3344FF;
--light-blue: #0df6f8;
--coral: #ff6f91;
--pink: #e075ff;

/* Typography — PP Neue Corp */
--font: 'PP Neue Corp', 'Inter', 'SF Pro Display', system-ui, sans-serif;
--h1: 120px / 1.0 / Bold;
--h2: 72px / 1.05 / Medium;
--h3: 48px / 1.1 / Regular;
--h4: 32px / 1.2 / Regular;
--body: 18px / 1.5 / Regular;
--caption: 14px / 1.4 / Light;
--label: 12px / 1.3 / Medium / uppercase / tracking 0.1em;

/* Spacing (8pt grid) */
--space-xs: 4px;
--space-sm: 8px;
--space-md: 16px;
--space-lg: 24px;
--space-xl: 32px;
--space-2xl: 48px;
--space-3xl: 64px;
--space-4xl: 96px;
--space-5xl: 128px;

/* Page */
--page-w: 1920px;
--page-h: 1080px;
--page-padding: 96px;
```

---

## Pages Overview

| # | File | Title | Content |
|---|------|-------|---------|
| 01 | 01-cover.html | Cover | Logo + "Brand Expansion Guide" + tagline |
| 02 | 02-logo.html | Logo System | Logo, versions, clear space, min size |
| 03 | 03-colors.html | Color System | 4 brand colors + neutrals + usage rules |
| 04 | 04-typography.html | Typography | PP Neue Corp scale, hierarchy, weights |
| 05 | 05-iconography.html | Icon System | 3 layers: Functions, Inputs, Operations |
| 06 | 06-key-visuals.html | Key Visuals | 4 hero compositions as reference |
| 07 | 07-slide-template.html | Slide Template | Master slide layouts (cover, content, divider, closing) |
| 08 | 08-one-pager.html | One-Pager Template | Product/feature one-pager layout |
| 09 | 09-starter-system.html | Starter: System Overview | Flow diagram with icons |
| 10 | 10-starter-event.html | Starter: Conference Slide | Event/conference reference asset |

---

## Task 1: Shared CSS + Index

**Files:**
- Create: `pages/shared.css`
- Create: `index.html`

Shared CSS with all tokens, reset, page frame. Index links to all 10 pages.

---

## Task 2: Page 01 — Cover

**Files:** `pages/01-cover.html`

- Full black background
- Bem logo (white) centered top-third
- "Brand Expansion Guide" in H2 below
- "bem.ai" small label bottom-left
- Subtle blue gradient accent bottom-right corner
- Date: February 2026

---

## Task 3: Page 02 — Logo System

**Files:** `pages/02-logo.html`

- Page title "Logo" top-left
- Logo large center (white on black)
- Below: 4 versions grid — White/Black, With icon/Without icon
- Clear space diagram (using the square icon as unit)
- Minimum size: 24px height

---

## Task 4: Page 03 — Color System

**Files:** `pages/03-colors.html`

- Page title "Color System" top-left
- 4 large color swatches in a row:
  - Blue #2c3ab4 (Primary)
  - Light Blue #0df6f8 (Accent)
  - Coral #ff6f91 (Secondary)
  - Pink #e075ff (Highlight)
- Below: Neutrals row (Black, Near-Black, Gray-60, Gray-40, White)
- Usage rules section:
  - "Dark backgrounds as default"
  - "Blue for primary actions and accents"
  - "Coral/Pink sparingly for emphasis"
  - "Gradients: Blue to Light Blue (primary), Blue to Black (depth)"

---

## Task 5: Page 04 — Typography

**Files:** `pages/04-typography.html`

- Page title "Typography" top-left
- Font name "PP Neue Corp" large
- Weight specimens: Light / Regular / Medium / Bold
- Type scale showing:
  - H1: 120px Bold — "Intelligence"
  - H2: 72px Medium — "Built for clarity"
  - H3: 48px Regular — "Structure the chaos"
  - H4: 32px Regular — "Deploy the intelligence"
  - Body: 18px Regular — paragraph sample
  - Caption: 14px Light — metadata sample
  - Label: 12px Medium Uppercase — "TRANSFORM"

---

## Task 6: Page 05 — Icon System

**Files:** `pages/05-iconography.html`

- Page title "Icon System" top-left
- Three rows with layer labels:
  - **Layer #1 — Functions (3D Shapes):** Transform, Analyze, Route, Split, Join, Payload Shaping, Enrich
  - **Layer #2 — Inputs (2D Shapes):** Documents, Images, Spreadsheets, Structured Data, Audio, Video
  - **Layer #3 — Operations (Iconic):** String, Number, Boolean, Object, Array
- Each icon as a dark card with blue icon + label below
- Description text per layer explaining the visual logic

---

## Task 7: Page 06 — Key Visuals

**Files:** `pages/06-key-visuals.html`

- Page title "Key Visuals" top-left
- 2x2 grid showing 4 compositions:
  1. "Intelligence, engineered." (blue gradient)
  2. "Turn unstructured data into product" (dark + 3D pyramid)
  3. "Built for clarity." (diamond split)
  4. "From input to impact" (geometric lines)
- Each as a scaled-down card with caption

---

## Task 8: Page 07 — Slide Template

**Files:** `pages/07-slide-template.html`

- Page title "Slide Templates" top-left
- 4 mini-slides (scaled to ~440x248 each) in 2x2:
  1. **Cover slide:** Logo + presentation title + date
  2. **Content slide:** Title left + content area right
  3. **Divider slide:** Large quote/statement centered
  4. **Closing slide:** Logo + contact + CTA
- Grid and margin guides visible (subtle lines)

---

## Task 9: Page 08 — One-Pager Template

**Files:** `pages/08-one-pager.html`

- Page title "One-Pager Template" top-left
- Large 16:9 template preview showing:
  - Header: Logo + product name
  - Hero: Key visual area + headline
  - Body: 2-column content (text left, visual right)
  - Footer: URL + tagline
- Wireframe style with placeholder text + layout guides

---

## Task 10: Page 09 — Starter Asset: System Overview

**Files:** `pages/09-starter-system.html`

- Full bleed composition (no page frame UI)
- Based on bem2-23 flow diagram concept
- Logo center-left, "bem" wordmark
- Icon nodes connected by thin lines showing data flow
- Functions icons at key nodes
- Dark background, blue accents
- "System Overview" as slide title

---

## Task 11: Page 10 — Starter Asset: Conference Slide

**Files:** `pages/10-starter-event.html`

- Full bleed composition (no page frame UI)
- Bold typographic composition
- "Chaos in. Clarity out." or "Built for clarity." as headline
- bem logo top-left
- Large 3D shape (diamond/pyramid) as visual anchor
- Event-ready format: clean, high-impact
- Dark background, blue gradient accents

---

## Task 12: Page 11 — Social Media: LinkedIn

**Files:** `pages/11-social-linkedin.html`

- Page title "Social Media Templates" top-left, subtitle "LinkedIn"
- LinkedIn Post (1200x627) — headline + gradient blobs + logo
- LinkedIn Banner (1584x396) — wordmark + tagline + gradient
- Templates scaled and centered with format label + dimensions

---

## Task 13: Page 12 — Social Media: X

**Files:** `pages/12-social-x.html`

- Page title "Social Media Templates" top-left, subtitle "X (Twitter)"
- X Post (1200x675) — headline + gradient line accent + logo
- X Header (1500x500) — centered wordmark + tagline + subtle gradients
- Templates scaled and centered with format label + dimensions

---

## Task 14: Page 13 — Social Media: Instagram

**Files:** `pages/13-social-instagram.html`

- Page title "Social Media Templates" top-left, subtitle "Instagram"
- Feed (1080x1080), Stories (1080x1920), Carrossel (1080x1350)
- 3 templates side by side, correct proportions
- Each with brand copy, gradients, logo

---

## Execution Order

1. Task 1 (shared CSS + index) — foundation
2. Tasks 2-6 (brand system pages) — parallel possible
3. Tasks 7-9 (templates) — parallel possible
4. Tasks 10-11 (starter assets) — parallel possible
5. Tasks 12-14 (social media templates) — parallel possible

Total: ~13 files + shared CSS + index
