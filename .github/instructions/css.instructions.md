---
description: "CSS coding standards and conventions"
applyTo: "**/*.css"
name: "CSS-Coding-Standards"
---

# CSS Instructions

**Purpose:** Maintainable, responsive, accessible stylesheets. Store in `css/` folder. Use external files only (no inline styles).

## Structure & Naming
- Use external stylesheets only; link in HTML `<head>`
- Use descriptive class names: BEM methodology (`.block`, `.block__element`, `.block--modifier`)
- Prefer classes over IDs for styling; reserve IDs for JavaScript hooks
- Use CSS custom properties for colors, spacing, sizing: `--primary-color`, `--spacing-unit`

## Layout & Responsiveness
- Mobile-first: base styles for mobile, enhance with `@media (min-width: 768px)` for larger screens
- Use CSS Grid or Flexbox only; no floats or tables for layout
- Max nesting: 3 levels

## Accessibility & Usability
- Color contrast: WCAG AA minimum (4.5:1 for text)
- Don't convey info via color alone
- Focus styles: `:focus-visible` with high-contrast indicators (e.g., 3px solid outline)

## Code Quality
- Low specificity; avoid `!important`
- Simple selectors; minimal nesting
- Comments explain layout techniques and breakpoints (help students understand "why")

## Examples

```css
/* CSS Variables */
:root {
    --primary-color: #007bff;
    --spacing-unit: 1rem;
    --border-radius: 0.25rem;
}

/* Mobile-first Grid */
.grid {
    display: grid;
    grid-template-columns: 1fr;
    gap: var(--spacing-unit);
}

@media (min-width: 768px) {
    .grid {
        grid-template-columns: repeat(2, 1fr);
    }
}

/* Button with Focus */
.btn {
    padding: 0.5rem 1rem;
    background-color: var(--primary-color);
    color: white;
    border: none;
    cursor: pointer;
}

.btn:focus-visible {
    outline: 3px solid #ffbf47;
    outline-offset: 2px;
}

/* Flexbox Navigation */
.nav {
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
    list-style: none;
    padding: 0;
}

@media (min-width: 768px) {
    .nav {
        flex-direction: row;
    }
}
```