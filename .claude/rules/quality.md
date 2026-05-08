---
paths:
  - "index.html"
  - "style.css"
---

# Code quality

- Semantic HTML5 elements throughout (`<header>`, `<nav>`, `<main>`,
  `<section>`, `<article>`, `<footer>`)
- Every image must have a descriptive `alt` attribute
- All color combinations must pass WCAG AA contrast (4.5:1 for body text)
- The page must validate with no errors at validator.w3.org
- CSS variables defined once in `:root`, never hardcoded hex values in rules
- Class names use kebab-case (e.g. `section-heading`, `tag-tech`)
- No vendor prefixes unless actually required for a specific property
