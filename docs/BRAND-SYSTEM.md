# ZUGO Bike — Brand System

> Extracted from **ZGU Brand Guidelines v1.0** (42-page PDF).
> This is the digital reference for all brand decisions in this repo.
> Source PDF: `ZGU - Brand Guidelines - Final.pdf`

---

## Brand Identity

### Mission
Blur the lines between life and mobility by pairing determined people with equally determined e-bikes.

### Values
1. **Quality Driven**
2. **Supportive of our tribe**
3. **Driven to empower people**
4. **Wellness is always top of mind**
5. **Innovative**

### Brand Archetype — The Creator
Innovative, Inspirational, Daring, Provocative, Imaginative. Non-conformist by nature. The Creator gives new ideas to the world and creates structure by bringing something that didn't previously exist into being.

### Brand Voice
- Premium, fun, and powerful
- Educate and build trust — don't just sell
- Inspire exploration and adventure
- Heritage aesthetics with modern innovation
- Confident without arrogance

---

## Colors

### Primary Palette

| Name | HEX | RGB | Usage |
|---|---|---|---|
| **Electric Pink** | `#a22155` | 162, 33, 85 | Primary brand color |
| **Deep Purple** | `#3c175c` | 60, 23, 92 | Primary brand color |
| **Stylish Gradient** | `#3c175c` → `#a22155` | — | Top-to-bottom, transition at midpoint |

### Secondary Palette

| Name | HEX | RGB | Usage |
|---|---|---|---|
| **Action Pink** | `#F0488B` | 240, 72, 139 | CTAs, buttons, interactive elements |
| **Tree Green** | `#21A328` | — | Tree planting content only |
| **Foliage Green** | `#1b572b` | 27, 88, 44 | Tree planting content only |

### Neutrals

| Name | HEX | Usage |
|---|---|---|
| **Perfect White** | `#ffffff` | Backgrounds, negative space |
| **True Black** | `#000000` | Text, dark backgrounds |

### Color Rules
- Use brand colors without editing whenever possible
- Tints: use a 20% step system (100%, 80%, 60%, 40%, 20%)
- Any tint below 60% used as background requires dark text
- Secondary colors should not overpower the primary palette
- Green colors are restricted to tree planting related content unless directed otherwise

### CSS Variables (for `styles/tokens.css`)
```css
:root {
  /* Primary */
  --color-electric-pink: #a22155;
  --color-deep-purple: #3c175c;
  --color-gradient: linear-gradient(to bottom, #3c175c, #a22155);

  /* Secondary */
  --color-action-pink: #F0488B;
  --color-tree-green: #21A328;
  --color-foliage-green: #1b572b;

  /* Neutrals */
  --color-white: #ffffff;
  --color-black: #000000;
}
```

---

## Typography

### Primary Typeface — Helvetica Neue
A minimal, robust geometric sans-serif. Versatile, bold, and confident. Demands attention without fuss — just like our e-bikes.

### Approved Weights
| Weight | Name | Usage |
|---|---|---|
| 43 | Light Extended | Body text, secondary content |
| 93 | Black Extended | Headlines, emphasis, primary headings |

### Web Fallback Stack
```css
font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif;
```

### Type Rules
1. **Left-aligned, rag right** — always. Never centered or fully justified for multi-line text
2. **Align x-heights or baselines** when placing text elements next to each other
3. **Skip a weight** when pairing two weights for contrast
4. **Double the size** between two text elements for hierarchy
5. **Line length:** 45–70 characters per line
6. **Avoid orphans** (single-word lines at end of paragraphs)
7. **No strokes, outlines, or drop shadows** on typography
8. **No angles** other than 0 or 90 degrees. If vertical (90), text reads upward
9. **No unauthorized fonts** — Helvetica Neue only

---

## Logo

### Primary Lockup
- Icon + wordmark, horizontal layout
- Icon height is 2.25x the wordmark height
- Icon aligns to horizontal center of wordmark

### Minimum Sizes
| Version | Digital | Print |
|---|---|---|
| Horizontal lockup | 35px height | — |
| Icon only | 50px height | 0.75" height |

### Color Variations (only these are approved)
1. White on black/dark background
2. True Black on white/light background
3. White on gradient background (Deep Purple → Electric Pink)
4. Electric Pink on white background

### Clear Space
Minimum clear space equals the height and width of the icon from the wordmark, on all four sides. More space is always better.

### Placement
- **Preferred:** left-aligned on the primary grid line (the "spine")
- **Web:** upper left corner of navigation bar. Never centered, even on mobile
- **Page:** top or bottom left corners if spine position unavailable
- **Social avatars:** icon-only with proper clear space. Use Electric Pink, Deep Purple, or gradient background
- **Favicon:** 32x32px, icon only, solid fill (only approved solid-fill usage)

### Logo Errors (never do these)
- Stretch, squash, skew, or distort
- Encroach on required clear space
- Add drop shadows or graphic effects
- Use off-brand colors or reduce opacity
- Place on busy photographs or high-contrast patterns
- Change layout or relationship between icon and wordmark

---

## Photography

### Tone
**Cool, high contrast, and dynamic.** ZuGo has proprietary color grading applied to all brand photography.

### Guidelines
- Show people being active, dynamic, and riding with safety in mind
- Prefer documentary-style series: wide, medium, and tight shots
- Seek high-contrast lighting (strong highlights and shadows)
- Avoid stock photo aesthetics
- Content should convey brand values and inspire e-bike exploration

---

## Social Media

### Templates
- Grid-based: 24x24 grid system
- Maintain 1.5–2 grid squares from edge for clean layout
- **4:5 ratio** — single posts with details (pricing, product model)
- **1:1 ratio** — short messages, quotes, announcements, carousels

---

## Contacts

| Role | Name | Email |
|---|---|---|
| Chief Executive Officer | Hunter Bailey | hunter@zugo.bike |
| Chief Operating Officer | Juls Bindi | juls@zugo.bike |
| General Inquiries | — | info@zugobikes.com |
