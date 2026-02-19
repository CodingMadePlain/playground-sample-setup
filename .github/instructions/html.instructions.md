---
description: "HTML5 structural and accessibility guidelines"
applyTo: "**/*.html"
name: "HTML5-Structure-Standards"
---

# HTML5 Instructions

**Purpose:** Semantic, accessible, SEO-friendly HTML. Provide teaching comments. Work without JavaScript (progressive enhancement).

## Document Structure & Meta
- HTML5 doctype; required `<head>` meta tags: `charset="utf-8"`, `viewport`, `lang` on `<html>`
- One `<h1>` per page (page title)
- Link external CSS in `<head>`; defer non-critical scripts (`defer` or `async`)

## Semantic Elements
- Use landmarks: `<header>`, `<nav>`, `<main>`, `<article>`, `<section>`, `<aside>`, `<footer>`
- Prefer semantic elements over generic `<div>`
- Navigation: use `<nav>` with skip link: `<a class="skip-link" href="#main">Skip to main</a>`

## Accessibility
- Descriptive alt text for images; use `aria-*` only when semantic HTML is insufficient
- Form controls: associated `<label>` elements; group with `<fieldset>`/`<legend>`
- Color contrast: WCAG AA minimum; keyboard accessible interactive controls

## Forms & Media
- Images with captions: `<figure>` and `<figcaption>`
- Videos/audio: provide captions or transcripts

## Performance & SEO
- Meta description, Open Graph tags where relevant
- Responsive images: use `srcset`
- Validate HTML; run accessibility checks (WAVE, Lighthouse)

## Examples

```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Page Title</title>
  <meta name="description" content="Page description" />
  <link rel="stylesheet" href="/css/styles.css" />
</head>
<body>
  <a class="skip-link" href="#main">Skip to main</a>

  <header>
    <h1>Site Title</h1>
  </header>

  <nav>
    <ul>
      <li><a href="/">Home</a></li>
      <li><a href="/about">About</a></li>
    </ul>
  </nav>

  <main id="main">
    <article>
      <h2>Article Title</h2>
      <p>By Author — <time datetime="2026-02-09">Feb 9, 2026</time></p>
      
      <section>
        <h3>Section</h3>
        <p>Content with <a href="#">link</a>.</p>
        <figure>
          <img src="/image.jpg" alt="Descriptive alt text" />
          <figcaption>Caption</figcaption>
        </figure>
      </section>
    </article>
  </main>

  <footer>
    <p>&copy; 2026. <a href="/privacy">Privacy</a></p>
  </footer>

  <script src="/js/main.js" defer></script>
</body>
</html>
```

