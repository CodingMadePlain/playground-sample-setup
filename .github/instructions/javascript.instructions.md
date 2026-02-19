---
description: "JavaScript coding standards and conventions"
applyTo: "**/*.js"
name: "JavaScript-Coding-Standards"
---

# JavaScript Instructions

**Purpose:** Vanilla ES6+ JavaScript. Student-friendly, readable, well-commented. Store in `scripts/` folder.

## Syntax & Variables
- Use ES6+: let/const, template literals, destructuring, modules
- Prefer `const` by default; use `let` for reassignment; avoid `var`
- Descriptive names; camelCase for multi-word (e.g., `handleClick`, `userName`)
- Single-letter names only for loop indices (i, j, k)

## Functions & Scope
- Prefer named function declarations for readability and stack traces: `function myHandler() { ... }`
- Arrow functions only for short inline callbacks or when lexical `this` is required
- Keep functions small and single-purpose
- Avoid polluting global scope; use modules or single namespace

## DOM & Interactivity
- Wait for `DOMContentLoaded` before DOM manipulation if script in head
- Use event delegation for dynamic lists
- Manipulate semantic elements (role, aria-* attributes); maintain focus management

## Security & Validation
- Server-side validation (PHP/MySQL) is authoritative
- Client-side validation: UX assistance only, never security-critical

## Code Quality
- Brief comments explaining intent when code may confuse students
- Prefer clarity over cleverness
- Link external scripts in HTML with `defer`: `<script src="scripts/main.js" defer></script>`

## Examples

```js
// Named function for clarity
function handleFormSubmit(event) {
    event.preventDefault();
    const formData = new FormData(event.target);
    // send to server, validate server-side
}

document.querySelector('#form').addEventListener('submit', handleFormSubmit);

// Event delegation for dynamic lists
const listContainer = document.querySelector('#list');
listContainer.addEventListener('click', function(event) {
    if (event.target.classList.contains('delete-btn')) {
        event.target.closest('li').remove();
    }
});
```