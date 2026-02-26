# Social Media Templates — Design Doc

## Goal

Add 3 new pages to the Bem.ai Brand Expansion Guide with social media templates for LinkedIn, X (Twitter), and Instagram. Each page shows 1 master template per format, rendered at correct proportions.

## Formats

| Platform | Format | Dimensions | Layout |
|----------|--------|-----------|--------|
| LinkedIn | Post | 1200x627 | Headline + visual area + logo |
| LinkedIn | Banner/Cover | 1584x396 | Wordmark + tagline + gradient |
| X | Post | 1200x675 | Headline + visual area + logo |
| X | Header | 1500x500 | Wordmark + tagline + gradient |
| Instagram | Feed | 1080x1080 | Headline + visual area + logo |
| Instagram | Stories | 1080x1920 | Vertical: headline + visual |
| Instagram | Carrossel | 1080x1350 | Headline + body text + CTA |

## Pages

- `pages/11-social-linkedin.html` — LinkedIn Post + Banner
- `pages/12-social-x.html` — X Post + Header
- `pages/13-social-instagram.html` — Instagram Feed + Stories + Carrossel

## Visual Language

- Black background, PP Neue Corp typography
- Blue-to-lightblue gradients as accent
- bem.ai logo consistently positioned
- Real brand copy as placeholder: "Chaos in. Clarity out.", "Built for clarity.", etc.
- Templates shown at reduced scale with format label + dimensions (same pattern as 07-slide-template.html)

## Technical Approach

- Static HTML pages using existing shared.css
- Each template rendered at correct aspect ratio, scaled to fit page
- Follows same structure as existing pages (page frame, page number, page title)
- Update index.html to include new pages

## Design Tokens

Uses existing tokens from shared.css — no new tokens needed.
