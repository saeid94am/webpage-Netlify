---
paths:
  - "style.css"
  - "index.html"
---

# Design system

## Color palette

Use these exact hex values. Do not substitute or improvise.

```css
--color-bg:         #F7F9FC;   /* page background — off-white */
--color-surface:    #FFFFFF;   /* card and section surfaces */
--color-navy:       #0A1628;   /* headings, hero name */
--color-blue:       #185FA5;   /* accent, links, section markers */
--color-teal:       #1D9E75;   /* medical/research tags only */
--color-text:       #1A2332;   /* body text */
--color-muted:      #5A6A7E;   /* secondary text, dates, labels */
--color-border:     #DDE3EC;   /* card borders, dividers */
--color-tag-blue:   #E6F1FB;   /* background for tech stack tags */
--color-tag-teal:   #E1F5EE;   /* background for medical domain tags */
```

## Typography

Load these fonts from Google Fonts in the `<head>`:

```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600&family=JetBrains+Mono:wght@400;500&family=Lora:wght@600;700&display=swap" rel="stylesheet">
```

Apply fonts as follows:

- **Hero name, section headings**: `font-family: 'Lora', Georgia, serif`
- **All body text, navigation, labels**: `font-family: 'Inter', sans-serif`
- **Tech stack tags, code references, tool names**: `font-family: 'JetBrains Mono', monospace`

Font sizes:
- Hero name: 2.8rem, weight 700
- Hero subtitle: 1.1rem, weight 400, color `--color-blue`
- Section headings (h2): 1.5rem, weight 600
- Job titles, paper titles: 1rem, weight 500
- Body text: 0.95rem, line-height 1.75
- Labels, dates, secondary info: 0.82rem, color `--color-muted`
- Tags: 0.75rem, weight 500, monospace

## Section heading style

Every section heading (h2) must have:
- A 3px left border in `--color-blue`, height matching the text
- 12px left padding
- A small all-caps label above it in `--color-muted` at 0.7rem with 0.12em letter-spacing
- No underline, no background

Example pattern:
```html
<p class="section-label">Research</p>
<h2 class="section-heading">Publications</h2>
```

```css
.section-label {
  font-size: 0.7rem;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  color: var(--color-muted);
  margin-bottom: 4px;
}
.section-heading {
  font-family: 'Lora', Georgia, serif;
  font-size: 1.5rem;
  font-weight: 600;
  color: var(--color-navy);
  border-left: 3px solid var(--color-blue);
  padding-left: 12px;
  margin-top: 0;
}
```

## Tags

Two tag types only:

```html
<!-- Tech / tools tag (blue) -->
<span class="tag tag-tech">PyTorch</span>

<!-- Medical domain tag (teal) -->
<span class="tag tag-medical">Medical Imaging</span>
```

```css
.tag {
  display: inline-block;
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.75rem;
  font-weight: 500;
  padding: 3px 10px;
  border-radius: 20px;
  margin: 2px 3px 2px 0;
}
.tag-tech    { background: var(--color-tag-blue); color: #0C447C; }
.tag-medical { background: var(--color-tag-teal); color: #085041; }
```

## Cards

Each entry (job, degree, project, paper) sits in a card:
- White background (`--color-surface`)
- 1px border in `--color-border`
- Border radius: 8px
- Padding: 20px 24px
- Margin between cards: 12px
- No shadows

## Layout

- Max content width: 780px, centered with `margin: 0 auto`
- Page padding: 0 24px
- Section vertical spacing: 72px between sections
- Single column layout throughout — no sidebars, no grid layouts
  except the skills section (2-column grid on desktop, 1 column on mobile)

## Navigation

Sticky top bar:
- Background: `rgba(247, 249, 252, 0.95)` with `backdrop-filter: blur(8px)`
- Height: 52px
- Border bottom: 1px solid `--color-border`
- Links: Inter 0.85rem, color `--color-muted`, no underline
- Active/hover link: color `--color-blue`
- GitHub and LinkedIn icon links on the right side (use SVG icons inline)
- The nav should highlight the current section on scroll using
  the Intersection Observer API (vanilla JS, ~20 lines max)
