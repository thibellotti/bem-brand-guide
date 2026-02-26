# Social Media Templates — Implementation Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Add 3 pages to the Bem.ai Brand Expansion Guide with social media templates for LinkedIn, X, and Instagram.

**Architecture:** Static HTML pages following the exact same pattern as `pages/07-slide-template.html`. Each page is a 1920x1080 artboard showing scaled-down template mockups with format labels and dimensions. Uses existing `shared.css` tokens and PP Neue Corp font.

**Tech Stack:** HTML, CSS (no JS). Existing shared.css design tokens.

---

## Reference: Pattern from 07-slide-template.html

Every social media page follows this structure:
- `<link rel="stylesheet" href="shared.css">`
- `<div class="page">` wrapper (1920x1080)
- Page header: `.page-title` label + subtitle describing the format
- Templates rendered at correct aspect ratio, scaled to fit within the page
- Each template inside a bordered card (`.mini-slide` equivalent) with format label below
- Real brand copy as placeholder text
- Logo via `<img src="../assets/bem-logo.svg">`
- `<span class="page-number">` bottom-right
- Blue gradient blob accents where appropriate

---

## Task 1: Page 11 — LinkedIn Templates

**Files:**
- Create: `pages/11-social-linkedin.html`

**Step 1: Create the LinkedIn page**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=1920">
  <title>Bem.ai — Social Media: LinkedIn</title>
  <link rel="stylesheet" href="shared.css">
  <style>
    .social-header {
      margin-bottom: var(--sp-7);
    }

    .social-page-title {
      font-size: 12px;
      font-weight: 500;
      color: var(--gray-40);
      letter-spacing: 0.15em;
      text-transform: uppercase;
      margin-bottom: var(--sp-2);
    }

    .social-subtitle {
      font-size: 18px;
      font-weight: 200;
      color: var(--gray-40);
    }

    /* Layout: templates stacked vertically */
    .templates-stack {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 48px;
      width: 100%;
    }

    .template-cell {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: var(--sp-3);
    }

    .template-label {
      font-size: 12px;
      font-weight: 200;
      color: var(--gray-40);
      letter-spacing: 0.05em;
    }

    .template-dims {
      font-size: 11px;
      font-weight: 200;
      color: var(--gray-20);
      letter-spacing: 0.05em;
    }

    /* LinkedIn Post — 1200x627 scaled to ~720x376 */
    .li-post {
      width: 720px;
      height: 376px;
      border: 1px solid var(--gray-20);
      border-radius: 8px;
      background: var(--black);
      position: relative;
      overflow: hidden;
      display: flex;
      flex-direction: column;
      justify-content: center;
      padding: 48px;
    }

    .li-post .post-label {
      font-size: 10px;
      font-weight: 500;
      color: var(--blue-bright);
      letter-spacing: 0.15em;
      text-transform: uppercase;
      margin-bottom: 12px;
    }

    .li-post .post-headline {
      font-size: 36px;
      font-weight: 800;
      color: var(--white);
      line-height: 1.05;
      letter-spacing: -0.02em;
      max-width: 65%;
    }

    .li-post .post-sub {
      font-size: 14px;
      font-weight: 200;
      color: var(--gray-60);
      margin-top: 16px;
      max-width: 50%;
    }

    .li-post .post-logo {
      position: absolute;
      bottom: 24px;
      left: 48px;
    }

    .li-post .post-blob {
      position: absolute;
      top: -60px;
      right: -40px;
      width: 280px;
      height: 280px;
      border-radius: 50%;
      background: radial-gradient(
        circle at center,
        var(--blue) 0%,
        rgba(44, 58, 180, 0.3) 40%,
        transparent 70%
      );
      opacity: 0.5;
      pointer-events: none;
    }

    .li-post .post-accent {
      position: absolute;
      bottom: -80px;
      right: 120px;
      width: 200px;
      height: 200px;
      border-radius: 50%;
      background: radial-gradient(
        circle at center,
        var(--light-blue) 0%,
        rgba(13, 246, 248, 0.15) 40%,
        transparent 70%
      );
      opacity: 0.4;
      pointer-events: none;
    }

    .li-post .post-url {
      position: absolute;
      bottom: 24px;
      right: 48px;
      font-size: 11px;
      font-weight: 200;
      color: var(--gray-40);
    }

    /* LinkedIn Banner — 1584x396 scaled to ~720x180 */
    .li-banner {
      width: 720px;
      height: 180px;
      border: 1px solid var(--gray-20);
      border-radius: 8px;
      background: var(--black);
      position: relative;
      overflow: hidden;
      display: flex;
      align-items: center;
      padding: 0 48px;
    }

    .li-banner .banner-left {
      display: flex;
      align-items: center;
      gap: 16px;
    }

    .li-banner .banner-wordmark {
      font-size: 28px;
      font-weight: 800;
      color: var(--white);
      line-height: 1;
    }

    .li-banner .banner-divider {
      width: 1px;
      height: 24px;
      background: var(--gray-20);
    }

    .li-banner .banner-tagline {
      font-size: 14px;
      font-weight: 200;
      color: var(--gray-60);
    }

    .li-banner .banner-gradient {
      position: absolute;
      top: 0;
      right: 0;
      width: 40%;
      height: 100%;
      background: linear-gradient(135deg, transparent 0%, rgba(44, 58, 180, 0.15) 50%, rgba(13, 246, 248, 0.1) 100%);
      pointer-events: none;
    }
  </style>
</head>
<body>

  <div class="page">

    <!-- Header -->
    <div class="social-header">
      <div class="social-page-title">Social Media Templates</div>
      <div class="social-subtitle">LinkedIn — Post & Company Banner</div>
    </div>

    <!-- Templates -->
    <div class="templates-stack">

      <!-- LinkedIn Post -->
      <div class="template-cell">
        <div class="li-post">
          <div class="post-label">Announcement</div>
          <div class="post-headline">Chaos in.<br>Clarity out.</div>
          <div class="post-sub">Turn unstructured data into structured intelligence.</div>
          <div class="post-logo">
            <img src="../assets/bem-logo.svg" alt="bem" style="height:14px;width:auto;opacity:0.6">
          </div>
          <div class="post-url">bem.ai</div>
          <div class="post-blob"></div>
          <div class="post-accent"></div>
        </div>
        <span class="template-label">Post</span>
        <span class="template-dims">1200 x 627</span>
      </div>

      <!-- LinkedIn Banner -->
      <div class="template-cell">
        <div class="li-banner">
          <div class="banner-left">
            <img src="../assets/bem-logo.svg" alt="bem" style="height:18px;width:auto">
            <div class="banner-divider"></div>
            <div class="banner-tagline">Intelligence, engineered.</div>
          </div>
          <div class="banner-gradient"></div>
        </div>
        <span class="template-label">Company Banner</span>
        <span class="template-dims">1584 x 396</span>
      </div>

    </div>

    <!-- Page number -->
    <span class="page-number">11</span>

  </div>

</body>
</html>
```

**Step 2: Verify in browser**

Open `pages/11-social-linkedin.html` in browser. Confirm:
- Page renders at 1920x1080
- Post template is ~720x376 with headline, gradient blobs, logo
- Banner template is ~720x180 with wordmark + tagline + gradient
- Labels and dimensions visible below each template

---

## Task 2: Page 12 — X (Twitter) Templates

**Files:**
- Create: `pages/12-social-x.html`

**Step 1: Create the X page**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=1920">
  <title>Bem.ai — Social Media: X</title>
  <link rel="stylesheet" href="shared.css">
  <style>
    .social-header {
      margin-bottom: var(--sp-7);
    }

    .social-page-title {
      font-size: 12px;
      font-weight: 500;
      color: var(--gray-40);
      letter-spacing: 0.15em;
      text-transform: uppercase;
      margin-bottom: var(--sp-2);
    }

    .social-subtitle {
      font-size: 18px;
      font-weight: 200;
      color: var(--gray-40);
    }

    .templates-stack {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 48px;
      width: 100%;
    }

    .template-cell {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: var(--sp-3);
    }

    .template-label {
      font-size: 12px;
      font-weight: 200;
      color: var(--gray-40);
      letter-spacing: 0.05em;
    }

    .template-dims {
      font-size: 11px;
      font-weight: 200;
      color: var(--gray-20);
      letter-spacing: 0.05em;
    }

    /* X Post — 1200x675 scaled to ~720x405 */
    .x-post {
      width: 720px;
      height: 405px;
      border: 1px solid var(--gray-20);
      border-radius: 8px;
      background: var(--black);
      position: relative;
      overflow: hidden;
      display: flex;
      flex-direction: column;
      justify-content: center;
      padding: 48px;
    }

    .x-post .post-headline {
      font-size: 40px;
      font-weight: 800;
      color: var(--white);
      line-height: 1.05;
      letter-spacing: -0.02em;
      max-width: 70%;
    }

    .x-post .post-sub {
      font-size: 16px;
      font-weight: 200;
      color: var(--gray-60);
      margin-top: 16px;
      max-width: 55%;
    }

    .x-post .post-logo {
      position: absolute;
      bottom: 24px;
      left: 48px;
    }

    .x-post .post-cta {
      position: absolute;
      bottom: 24px;
      right: 48px;
      font-size: 12px;
      font-weight: 500;
      color: var(--blue-bright);
      letter-spacing: 0.1em;
      text-transform: uppercase;
    }

    .x-post .post-line {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 3px;
      background: linear-gradient(90deg, var(--blue) 0%, var(--light-blue) 60%, transparent 100%);
    }

    .x-post .post-blob {
      position: absolute;
      bottom: -100px;
      right: -60px;
      width: 300px;
      height: 300px;
      border-radius: 50%;
      background: radial-gradient(
        circle at center,
        var(--blue) 0%,
        rgba(44, 58, 180, 0.25) 40%,
        transparent 70%
      );
      opacity: 0.4;
      pointer-events: none;
    }

    /* X Header — 1500x500 scaled to ~720x240 */
    .x-header {
      width: 720px;
      height: 240px;
      border: 1px solid var(--gray-20);
      border-radius: 8px;
      background: var(--black);
      position: relative;
      overflow: hidden;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .x-header .header-content {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 12px;
    }

    .x-header .header-tagline {
      font-size: 18px;
      font-weight: 200;
      color: var(--gray-60);
      letter-spacing: -0.01em;
    }

    .x-header .header-gradient-left {
      position: absolute;
      top: 0;
      left: 0;
      width: 30%;
      height: 100%;
      background: linear-gradient(90deg, rgba(44, 58, 180, 0.12) 0%, transparent 100%);
      pointer-events: none;
    }

    .x-header .header-gradient-right {
      position: absolute;
      top: 0;
      right: 0;
      width: 30%;
      height: 100%;
      background: linear-gradient(270deg, rgba(13, 246, 248, 0.08) 0%, transparent 100%);
      pointer-events: none;
    }

    .x-header .header-line {
      position: absolute;
      bottom: 0;
      left: 0;
      width: 100%;
      height: 2px;
      background: linear-gradient(90deg, var(--blue) 0%, var(--light-blue) 50%, transparent 100%);
      opacity: 0.5;
    }
  </style>
</head>
<body>

  <div class="page">

    <!-- Header -->
    <div class="social-header">
      <div class="social-page-title">Social Media Templates</div>
      <div class="social-subtitle">X (Twitter) — Post Image & Profile Header</div>
    </div>

    <!-- Templates -->
    <div class="templates-stack">

      <!-- X Post -->
      <div class="template-cell">
        <div class="x-post">
          <div class="post-line"></div>
          <div class="post-headline">Built for<br>clarity.</div>
          <div class="post-sub">From unstructured input to structured output — automatically.</div>
          <div class="post-logo">
            <img src="../assets/bem-logo.svg" alt="bem" style="height:14px;width:auto;opacity:0.6">
          </div>
          <div class="post-cta">Learn more &rarr;</div>
          <div class="post-blob"></div>
        </div>
        <span class="template-label">Post Image</span>
        <span class="template-dims">1200 x 675</span>
      </div>

      <!-- X Header -->
      <div class="template-cell">
        <div class="x-header">
          <div class="header-gradient-left"></div>
          <div class="header-gradient-right"></div>
          <div class="header-content">
            <img src="../assets/bem-logo.svg" alt="bem" style="height:22px;width:auto">
            <div class="header-tagline">Intelligence, engineered.</div>
          </div>
          <div class="header-line"></div>
        </div>
        <span class="template-label">Profile Header</span>
        <span class="template-dims">1500 x 500</span>
      </div>

    </div>

    <!-- Page number -->
    <span class="page-number">12</span>

  </div>

</body>
</html>
```

**Step 2: Verify in browser**

Open `pages/12-social-x.html`. Confirm same quality as LinkedIn page.

---

## Task 3: Page 13 — Instagram Templates

**Files:**
- Create: `pages/13-social-instagram.html`

**Step 1: Create the Instagram page**

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=1920">
  <title>Bem.ai — Social Media: Instagram</title>
  <link rel="stylesheet" href="shared.css">
  <style>
    .social-header {
      margin-bottom: var(--sp-7);
    }

    .social-page-title {
      font-size: 12px;
      font-weight: 500;
      color: var(--gray-40);
      letter-spacing: 0.15em;
      text-transform: uppercase;
      margin-bottom: var(--sp-2);
    }

    .social-subtitle {
      font-size: 18px;
      font-weight: 200;
      color: var(--gray-40);
    }

    /* Horizontal layout for 3 templates */
    .templates-row {
      display: flex;
      justify-content: center;
      align-items: flex-start;
      gap: 40px;
      width: 100%;
      margin-top: 16px;
    }

    .template-cell {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: var(--sp-3);
    }

    .template-label {
      font-size: 12px;
      font-weight: 200;
      color: var(--gray-40);
      letter-spacing: 0.05em;
    }

    .template-dims {
      font-size: 11px;
      font-weight: 200;
      color: var(--gray-20);
      letter-spacing: 0.05em;
    }

    /* Shared template card styles */
    .ig-card {
      border: 1px solid var(--gray-20);
      border-radius: 8px;
      background: var(--black);
      position: relative;
      overflow: hidden;
    }

    /* Instagram Feed — 1080x1080 scaled to ~420x420 */
    .ig-feed {
      width: 420px;
      height: 420px;
      display: flex;
      flex-direction: column;
      justify-content: center;
      padding: 40px;
    }

    .ig-feed .feed-label {
      font-size: 9px;
      font-weight: 500;
      color: var(--blue-bright);
      letter-spacing: 0.15em;
      text-transform: uppercase;
      margin-bottom: 12px;
    }

    .ig-feed .feed-headline {
      font-size: 36px;
      font-weight: 800;
      color: var(--white);
      line-height: 1.05;
      letter-spacing: -0.02em;
    }

    .ig-feed .feed-sub {
      font-size: 13px;
      font-weight: 200;
      color: var(--gray-60);
      margin-top: 16px;
      max-width: 80%;
    }

    .ig-feed .feed-logo {
      position: absolute;
      bottom: 24px;
      left: 40px;
    }

    .ig-feed .feed-url {
      position: absolute;
      bottom: 24px;
      right: 40px;
      font-size: 10px;
      font-weight: 200;
      color: var(--gray-40);
    }

    .ig-feed .feed-blob {
      position: absolute;
      top: -80px;
      right: -60px;
      width: 240px;
      height: 240px;
      border-radius: 50%;
      background: radial-gradient(
        circle at center,
        var(--blue) 0%,
        rgba(44, 58, 180, 0.3) 40%,
        transparent 70%
      );
      opacity: 0.5;
      pointer-events: none;
    }

    /* Instagram Stories — 1080x1920 scaled to ~350x622 */
    .ig-stories {
      width: 350px;
      height: 622px;
      display: flex;
      flex-direction: column;
      justify-content: flex-end;
      padding: 32px;
    }

    .ig-stories .stories-logo {
      position: absolute;
      top: 24px;
      left: 32px;
    }

    .ig-stories .stories-headline {
      font-size: 32px;
      font-weight: 800;
      color: var(--white);
      line-height: 1.05;
      letter-spacing: -0.02em;
      margin-bottom: 12px;
    }

    .ig-stories .stories-sub {
      font-size: 12px;
      font-weight: 200;
      color: var(--gray-60);
      margin-bottom: 24px;
    }

    .ig-stories .stories-cta {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      font-size: 11px;
      font-weight: 500;
      color: var(--white);
      background: var(--blue);
      padding: 8px 16px;
      border-radius: 4px;
      width: fit-content;
      letter-spacing: 0.05em;
      text-transform: uppercase;
    }

    .ig-stories .stories-blob {
      position: absolute;
      top: 20%;
      right: -40px;
      width: 200px;
      height: 200px;
      border-radius: 50%;
      background: radial-gradient(
        circle at center,
        var(--blue) 0%,
        rgba(44, 58, 180, 0.3) 40%,
        transparent 70%
      );
      opacity: 0.45;
      pointer-events: none;
    }

    .ig-stories .stories-accent {
      position: absolute;
      bottom: 30%;
      left: -60px;
      width: 180px;
      height: 180px;
      border-radius: 50%;
      background: radial-gradient(
        circle at center,
        var(--light-blue) 0%,
        rgba(13, 246, 248, 0.15) 40%,
        transparent 70%
      );
      opacity: 0.35;
      pointer-events: none;
    }

    /* Instagram Carrossel — 1080x1350 scaled to ~350x437 */
    .ig-carrossel {
      width: 350px;
      height: 437px;
      display: flex;
      flex-direction: column;
      justify-content: center;
      padding: 32px;
    }

    .ig-carrossel .car-label {
      font-size: 9px;
      font-weight: 500;
      color: var(--blue-bright);
      letter-spacing: 0.15em;
      text-transform: uppercase;
      margin-bottom: 12px;
    }

    .ig-carrossel .car-headline {
      font-size: 28px;
      font-weight: 800;
      color: var(--white);
      line-height: 1.1;
      letter-spacing: -0.02em;
      margin-bottom: 16px;
    }

    .ig-carrossel .car-body {
      font-size: 12px;
      font-weight: 200;
      color: var(--gray-60);
      line-height: 1.6;
      margin-bottom: 24px;
    }

    .ig-carrossel .car-cta {
      font-size: 11px;
      font-weight: 500;
      color: var(--blue-bright);
      letter-spacing: 0.1em;
      text-transform: uppercase;
    }

    .ig-carrossel .car-logo {
      position: absolute;
      bottom: 20px;
      left: 32px;
    }

    .ig-carrossel .car-dots {
      position: absolute;
      bottom: 20px;
      right: 32px;
      display: flex;
      gap: 4px;
    }

    .ig-carrossel .car-dot {
      width: 5px;
      height: 5px;
      border-radius: 50%;
      background: var(--gray-20);
    }

    .ig-carrossel .car-dot.active {
      background: var(--blue-bright);
    }

    .ig-carrossel .car-line {
      position: absolute;
      bottom: 0;
      left: 0;
      width: 100%;
      height: 2px;
      background: linear-gradient(90deg, var(--blue) 0%, var(--light-blue) 100%);
      opacity: 0.4;
    }
  </style>
</head>
<body>

  <div class="page">

    <!-- Header -->
    <div class="social-header">
      <div class="social-page-title">Social Media Templates</div>
      <div class="social-subtitle">Instagram — Feed Post, Stories & Carrossel</div>
    </div>

    <!-- Templates side by side -->
    <div class="templates-row">

      <!-- Feed -->
      <div class="template-cell">
        <div class="ig-card ig-feed">
          <div class="feed-label">New Feature</div>
          <div class="feed-headline">Chaos in.<br>Clarity out.</div>
          <div class="feed-sub">Structured intelligence for every workflow.</div>
          <div class="feed-logo">
            <img src="../assets/bem-logo.svg" alt="bem" style="height:12px;width:auto;opacity:0.6">
          </div>
          <div class="feed-url">bem.ai</div>
          <div class="feed-blob"></div>
        </div>
        <span class="template-label">Feed</span>
        <span class="template-dims">1080 x 1080</span>
      </div>

      <!-- Stories -->
      <div class="template-cell">
        <div class="ig-card ig-stories">
          <div class="stories-logo">
            <img src="../assets/bem-logo.svg" alt="bem" style="height:12px;width:auto;opacity:0.6">
          </div>
          <div class="stories-headline">From input<br>to impact.</div>
          <div class="stories-sub">Process any data format with AI-powered intelligence.</div>
          <div class="stories-cta">Learn more &rarr;</div>
          <div class="stories-blob"></div>
          <div class="stories-accent"></div>
        </div>
        <span class="template-label">Stories / Reels</span>
        <span class="template-dims">1080 x 1920</span>
      </div>

      <!-- Carrossel -->
      <div class="template-cell">
        <div class="ig-card ig-carrossel">
          <div class="car-label">How it works</div>
          <div class="car-headline">Turn unstructured data into product.</div>
          <div class="car-body">Documents, images, audio — bem processes any input and outputs clean, structured data ready for your product.</div>
          <div class="car-cta">Swipe &rarr;</div>
          <div class="car-logo">
            <img src="../assets/bem-logo.svg" alt="bem" style="height:10px;width:auto;opacity:0.5">
          </div>
          <div class="car-dots">
            <div class="car-dot active"></div>
            <div class="car-dot"></div>
            <div class="car-dot"></div>
            <div class="car-dot"></div>
          </div>
          <div class="car-line"></div>
        </div>
        <span class="template-label">Carrossel</span>
        <span class="template-dims">1080 x 1350</span>
      </div>

    </div>

    <!-- Page number -->
    <span class="page-number">13</span>

  </div>

</body>
</html>
```

**Step 2: Verify in browser**

Open `pages/13-social-instagram.html`. Confirm:
- 3 templates side by side (feed square, stories tall, carrossel portrait)
- All have correct proportions
- Text, gradients, and logos render properly

---

## Task 4: Update PLAN.md and pages-index.html

**Files:**
- Modify: `PLAN.md` (append new tasks)
- Modify: `pages-index.html` (add links to new pages)

**Step 1: Append social media tasks to PLAN.md**

Add after the existing Task 11:

```markdown
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
```

**Step 2: Add links to pages-index.html**

Add new entries for pages 11, 12, 13 in the navigation.

---

## Execution Order

1. Task 1 (LinkedIn) — standalone
2. Task 2 (X) — standalone
3. Task 3 (Instagram) — standalone
4. Task 4 (update PLAN.md + index) — after 1-3

Tasks 1-3 are fully independent and can run in parallel.
