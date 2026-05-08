# Project

A single-page personal resume website for a machine learning researcher
specializing in medical AI (ECG signal processing, medical imaging, diagnosis).
The site must feel academic, precise, and trustworthy — not creative or flashy.

Target audience: academic hiring committees, medical AI research teams,
clinical AI companies, and collaborators in the medical/ML space.

## File structure

```
/
├── index.html       ← the entire site lives here (single file)
├── style.css        ← all styles in one external stylesheet
├── CLAUDE.md        ← this file
└── assets/
    └── profile.jpg  ← optional profile photo (add later if needed)
```

No frameworks. No JavaScript libraries. No build tools. No npm.
Pure HTML + CSS + minimal vanilla JS only where strictly necessary.
This constraint is intentional: the site deploys directly to GitHub Pages
and Netlify with zero build configuration.

## Deployment targets

- **GitHub Pages**: static hosting, no server-side code, no build step.
- **Netlify**: connected to the same GitHub repo, auto-deploys on push.

Never add anything that requires a build step (React, Sass, TypeScript, etc.).
All assets must use relative paths so the site works from any subdirectory.
