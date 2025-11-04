# WKND Trendsetters Design System

> **Complete design system reference extracted from styles.css and all block implementations**
>
> Use this guide when generating new blocks or pages to maintain visual consistency

---

## Table of Contents
1. [Color Palette](#color-palette)
2. [Typography](#typography)
3. [Spacing System](#spacing-system)
4. [Components](#components)
5. [Layout Patterns](#layout-patterns)
6. [Responsive Breakpoints](#responsive-breakpoints)
7. [Effects & Shadows](#effects--shadows)
8. [Animation & Transitions](#animation--transitions)

---

## Color Palette

### Primary Colors
```css
--background-color: #fff;           /* White background */
--dark-color: #000;                 /* Pure black */
--light-color: #f7f8f5;             /* Off-white/light gray */
--accent-color: #f4fe8b;            /* Neon yellow (signature color) */
```

### Text Colors
```css
--text-color: #000;                        /* Black text on light backgrounds */
--text-color-inverse: #fff;                /* White text on dark backgrounds */
--text-color-muted: rgba(255, 255, 255, 0.7);  /* Muted white (70% opacity) */
```

### Accent Variations
```css
--accent-color-transparent: rgba(244, 254, 139, 0.5);  /* 50% opacity yellow */
--accent-color-bg: rgba(244, 254, 139, 0.1);           /* 10% opacity yellow background */
```

### Usage Guidelines
- **Black backgrounds** for dramatic sections (use `.section.dark`)
- **White backgrounds** for standard content (default or `.section.light`)
- **Light gray backgrounds** for subtle section separation (`.section.grey`)
- **Neon yellow accent** for buttons, highlights, and interactive elements
- **Text on dark** always use `--text-color-inverse` for headings, `--text-color-muted` for body text

---

## Typography

### Font Families
```css
--body-font-family: "Instrument Sans", instrument-sans-fallback, sans-serif;
--heading-font-family: Syncopate, syncopate-fallback, sans-serif;
```

**Source:** Google Fonts
```html
@import url('https://fonts.googleapis.com/css2?family=Instrument+Sans:wght@400;500;600;700&family=Syncopate:wght@400;700&display=swap');
```

### Typography Scale

#### Body Text (Mobile-first)
```css
--body-font-size-m: 14.08px;   /* Standard body text */
--body-font-size-s: 14.08px;   /* Smaller body text */
--body-font-size-xs: 14.08px;  /* Extra small text */
--body-line-height: 1.6;       /* Comfortable reading */
```

#### Body Text (Desktop ≥900px)
```css
--body-font-size-m: 18px;
--body-font-size-s: 16px;
--body-font-size-xs: 14px;
```

#### Heading Sizes (Mobile-first)
```css
--heading-font-size-xxl: 90.4px;   /* H1 - Hero headlines */
--heading-font-size-xl: 45.28px;   /* H2 - Section headings */
--heading-font-size-l: 22.56px;    /* H3 - Sub-sections */
--heading-font-size-m: 22.56px;    /* H4 */
--heading-font-size-s: 22.56px;    /* H5 */
--heading-font-size-xs: 22.56px;   /* H6 */
```

#### Heading Sizes (Desktop ≥900px)
```css
--heading-font-size-xxl: 45px;     /* Slightly smaller on desktop */
--heading-font-size-xl: 36px;
--heading-font-size-l: 28px;
--heading-font-size-m: 22px;
--heading-font-size-s: 20px;
--heading-font-size-xs: 18px;
```

### Heading Properties
```css
--heading-font-weight: 400;       /* Regular weight (not bold) */
--heading-line-height: 1.04;      /* Tight line height for impact */
--h1-letter-spacing: -0.904px;    /* Negative spacing for large text */
--h2-letter-spacing: -0.4528px;
--h3-letter-spacing: -0.2256px;
--h1-margin-bottom: 27.12px;
--h2-margin-top: 20px;
--h3-margin-bottom: 11.28px;
```

### Typography Usage Rules
1. **Always use Syncopate for headings** - distinctive, condensed, impactful
2. **Always use Instrument Sans for body** - clean, modern, readable
3. **Headings are regular weight (400)** - not bold, relies on font design
4. **Large headings use negative letter-spacing** - tighter, more compact
5. **Line height 1.04 for headings** - tight, dramatic
6. **Line height 1.6 for body** - comfortable reading

---

## Spacing System

### Section Spacing
```css
--section-padding: 128px 0;   /* Generous vertical rhythm */
```

### Container Widths
```css
max-width: 1200px;           /* Standard content container */
max-width: 1248px;           /* Slightly wider for cards/grids */
padding: 0 24px;             /* Mobile horizontal padding */
padding: 0 32px;             /* Desktop horizontal padding (≥900px) */
```

### Common Gaps
```css
gap: 8px;         /* Tight spacing (button groups) */
gap: 16px;        /* Small spacing (card metadata) */
gap: 24px;        /* Medium spacing (mobile columns) */
gap: 32px;        /* Standard spacing (cards, grids) */
gap: 48px;        /* Large spacing (card rows) */
gap: 64px;        /* Extra large spacing (hero sections) */
gap: 96px;        /* Huge spacing (columns-banner desktop) */
```

### Spacing Philosophy
- **Mobile:** More compact, smaller gaps
- **Desktop:** Generous spacing, room to breathe
- **Consistent multiples:** 8px, 16px, 24px, 32px, 48px, 64px, 96px, 128px

---

## Components

### Buttons

#### Default Button Style
```css
border-radius: 1600px;  /* Fully rounded pill shape */
padding: 16px 24px;
font-size: 16px;
font-weight: 400;
color: var(--text-color);
background-color: transparent;
box-shadow: rgb(0, 0, 0) 0px 0px 0px 2px inset,     /* Black border */
            rgba(244, 254, 139, 0.5) 4px 4px 0px 0px;  /* Yellow offset shadow */
transition: border-color 0.2s, color 0.2s,
            background-color 0.2s cubic-bezier(0.165, 0.84, 0.44, 1),
            box-shadow 0.2s;
```

#### Button Hover State
```css
background-color: rgba(244, 254, 139, 0.1);  /* Subtle yellow tint */
box-shadow: rgb(0, 0, 0) 0px 0px 0px 2px inset,
            rgba(244, 254, 139, 0.5) 7px 7px 0px 0px;  /* Larger offset on hover */
```

#### Button Variations

**Primary Accent Button:**
```css
background-color: rgb(244, 254, 139);  /* Solid yellow background */
color: rgb(0, 0, 0);
box-shadow: none;  /* No shadow */
```

**White Button on Dark Background:**
```css
color: rgb(255, 255, 255);
box-shadow: rgb(255, 255, 255) 0px 0px 0px 2px inset,
            rgba(244, 254, 139, 0.5) 4px 4px 0px 0px;
```

**Simple Border Button:**
```css
box-shadow: rgb(0, 0, 0) 0px 0px 0px 2px inset;  /* Just black border, no offset */
```

### Cards

#### Standard Card
```css
border-radius: 20px;
box-shadow: rgb(0, 0, 0) 0px 0px 0px 2px,           /* 2px black border */
            rgba(0, 0, 0, 0.2) 6px 6px 0px 0px;     /* Offset shadow */
background-color: transparent;
overflow: hidden;
```

**Usage:** `cards-trends`, `banner-cta`, `hero-feature`

#### Card Images
```css
border-radius: 20px;
object-fit: cover;
```

Common aspect ratios:
- **1:1** - Square images (columns-pictures, profile images)
- **3:2** - Landscape cards (cards-trends)
- **2:3** - Portrait cards (cards-articles)

### Tags/Badges
```css
background-color: rgba(0, 0, 0, 0.1);  /* Subtle gray background */
color: rgb(0, 0, 0);
font-size: 12px;
font-weight: 400;
padding: 2px 9px;
border-radius: 1600px;  /* Pill shape */
text-transform: uppercase;
letter-spacing: 0.42px;
```

**Usage:** Category tags in `cards-articles`, `cards-trends`

### Images
```css
border-radius: 20px;        /* Consistent rounded corners */
object-fit: cover;          /* Crop to fill container */
```

---

## Layout Patterns

### Grid Patterns

#### 2-Column Grid (Desktop)
```css
display: grid;
grid-template-columns: 1fr 1fr;
gap: 48px;
```
**Usage:** `cards` block (blog-style cards), `columns-banner`

#### 3-Column Grid
```css
display: grid;
grid-template-columns: repeat(3, 1fr);
gap: 32px;
```
**Usage:** `cards-trends` (tablet), 3-column layouts

#### 4-Column Grid
```css
display: grid;
grid-template-columns: repeat(4, 1fr);
gap: 32px;
```
**Usage:** `cards-articles`, `cards-trends` (desktop ≥1200px)

#### 3-Column Fixed Width Grid
```css
display: grid;
grid-template-columns: 368px 368px 368px;  /* Fixed column widths */
gap: 32px;
```
**Usage:** `text-feature`, `banner-cta` (precise desktop layouts)

### Mobile-First Approach
```css
/* Mobile default */
grid-template-columns: 1fr;

/* Tablet (≥600px) */
@media (width >= 600px) {
  grid-template-columns: repeat(2, 1fr);
}

/* Desktop (≥900px) */
@media (width >= 900px) {
  grid-template-columns: repeat(4, 1fr);
}
```

### Flex Patterns

#### Horizontal Button Group
```css
display: flex;
gap: 8px;
justify-content: center;  /* or flex-start */
align-items: center;
```

#### Column to Row
```css
/* Mobile */
display: flex;
flex-direction: column;
gap: 24px;

/* Desktop (≥900px) */
@media (width >= 900px) {
  flex-direction: row;
  gap: 96px;
  align-items: center;
}
```

### Full-Width Sections
```css
.section > div.block-wrapper {
  max-width: unset;  /* Remove max-width */
  padding: 0;        /* Remove horizontal padding */
}
```
**Usage:** `hero-grid`, `tabs`, `hero-feature`, `columns-pictures`

---

## Responsive Breakpoints

### Standard Breakpoints
```css
/* Mobile-first (default): 0-599px */

/* Tablet: 600px-899px */
@media (width >= 600px) { }

/* Desktop: 900px+ */
@media (width >= 900px) { }

/* Large Desktop: 1200px+ */
@media (width >= 1200px) { }
```

### Breakpoint Strategy
1. **Mobile-first** - start with mobile layout
2. **600px** - tablets, 2-column grids
3. **900px** - desktop, full layouts, larger typography
4. **1200px** - optional, for 4-column grids

### Responsive Typography
Mobile and desktop have **different typography scales** (see Typography section)

---

## Effects & Shadows

### Card Shadow (Signature Style)
```css
box-shadow: rgb(0, 0, 0) 0px 0px 0px 2px,           /* 2px solid border */
            rgba(0, 0, 0, 0.2) 6px 6px 0px 0px;     /* Offset drop shadow */
```

### Button Shadow (Yellow Glow)
```css
box-shadow: rgb(0, 0, 0) 0px 0px 0px 2px inset,
            rgba(244, 254, 139, 0.5) 4px 4px 0px 0px;  /* Yellow offset */
```

### Button Shadow Hover
```css
box-shadow: rgb(0, 0, 0) 0px 0px 0px 2px inset,
            rgba(244, 254, 139, 0.5) 7px 7px 0px 0px;  /* Larger offset */
```

### Dark Overlay on Images
```css
background-color: rgba(0, 0, 0, 0.5);   /* 50% black overlay */
background-color: rgba(0, 0, 0, 0.6);   /* 60% black overlay (hero-cta) */
```

---

## Animation & Transitions

### Standard Transitions
```css
--link-transition: color 0.2s;
--button-transition: border-color 0.2s, color 0.2s,
                     background-color 0.2s cubic-bezier(0.165, 0.84, 0.44, 1),
                     box-shadow 0.2s;
```

### Common Transition Patterns

#### Opacity Hover
```css
transition: opacity 0.3s ease;
```
```css
.element:hover {
  opacity: 0.9;  /* Subtle fade */
}
```

#### Transform Hover (Link Arrow)
```css
.link::after {
  content: ' →';
  margin-left: 4px;
  transition: margin-left 0.2s ease;
}

.link:hover::after {
  margin-left: 8px;  /* Arrow moves right */
}
```

#### Accordion Expand
```css
@keyframes accordion-expand {
  from {
    opacity: 0;
    transform: translateY(-8px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
```

### Accessibility - Reduced Motion
```css
@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}
```

---

## Block-Specific Patterns

### Hero Blocks

**Shared Hero Characteristics:**
- Centered text
- Large heading (90.4px desktop, 45px+ mobile)
- Button group below text
- Generous padding (128px, 96px, 64px responsive)

**Hero Types:**
1. **hero** - Simple centered hero with text and buttons
2. **hero-cta** - Hero with background image and dark overlay
3. **hero-feature** - Hero with background image, card overlay, and side image
4. **columns-banner** - Two-column hero with image and content side-by-side

### Card Blocks

**Card Grid Characteristics:**
- `list-style: none` to remove bullets
- Grid layout with responsive columns
- `border-radius: 20px` on images
- Tag/category labels using pill-shaped badges
- Consistent image aspect ratios

**Card Types:**
1. **cards** - Horizontal layout, image left, content right (blog-style)
2. **cards-trends** - Vertical cards with image top, content bottom, card shadows
3. **cards-articles** - Vertical portrait cards, 4-column grid on desktop

### Text Blocks

1. **text-feature** - Eyebrow + heading + body + CTA button
2. **banner-cta** - Card-style container with 3-column grid (text + button)
3. **columns-banner** - Split layout with image and content columns

### Interactive Blocks

1. **accordion** - Collapsible Q&A sections with chevron icons
2. **tabs** - Tabbed content navigation with underline indicators

---

## Quick Reference: Common Patterns

### Section with Dark Background
```css
.section.dark {
  background-color: var(--dark-color);
  color: var(--text-color-inverse);
  padding: var(--section-padding);
}
```

### Centered Content Container
```css
.block-content {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 24px;
}

@media (width >= 900px) {
  .block-content {
    padding: 0 32px;
  }
}
```

### Card Grid (Responsive)
```css
.card-grid {
  display: grid;
  grid-template-columns: 1fr;
  gap: 32px;
}

@media (width >= 600px) {
  .card-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (width >= 900px) {
  .card-grid {
    grid-template-columns: repeat(3, 1fr);
  }
}
```

### Button with Yellow Glow
```css
.button {
  padding: 16px 24px;
  border-radius: 1600px;
  background-color: transparent;
  box-shadow: rgb(0, 0, 0) 0px 0px 0px 2px inset,
              rgba(244, 254, 139, 0.5) 4px 4px 0px 0px;
  transition: box-shadow 0.2s, background-color 0.2s;
}

.button:hover {
  background-color: rgba(244, 254, 139, 0.1);
  box-shadow: rgb(0, 0, 0) 0px 0px 0px 2px inset,
              rgba(244, 254, 139, 0.5) 7px 7px 0px 0px;
}
```

### Rounded Image with Aspect Ratio
```css
img {
  width: 100%;
  height: auto;
  aspect-ratio: 1 / 1;
  object-fit: cover;
  border-radius: 20px;
}
```

---

## Design Principles

### Visual Identity
1. **Bold, high-contrast** - black and white foundation
2. **Neon yellow accent** - signature color for energy and youth
3. **Rounded corners everywhere** - friendly, modern (20px radius, 1600px buttons)
4. **Offset shadows** - distinctive card and button style
5. **Tight condensed headings** - Syncopate font with negative letter-spacing

### Typography Philosophy
- **Headings:** Syncopate (condensed, geometric, impactful)
- **Body:** Instrument Sans (clean, neutral, readable)
- **Weight:** Regular (400) for everything - font design provides personality
- **Scale:** Large jumps between sizes for clear hierarchy

### Layout Philosophy
- **Mobile-first** - design for small screens first
- **Grid-based** - CSS Grid for most layouts
- **Generous spacing** - lots of breathing room on desktop
- **Full-width sections** - some blocks break out of container

### Color Philosophy
- **Monochromatic base** - black and white
- **Single accent** - neon yellow for highlights
- **Transparency** - overlays and muted text use alpha channels
- **Section backgrounds** - white, light gray, or pure black

---

## Usage Guidelines for New Content

### Creating a New Block
1. Start with mobile-first layout (`grid-template-columns: 1fr`)
2. Use standard breakpoints (600px, 900px, 1200px)
3. Apply `border-radius: 20px` to all images
4. Use design tokens for colors, fonts, spacing
5. Follow button shadow pattern for CTAs
6. Add card shadows if using card-style containers

### Creating a New Page
1. Mix light, grey, and dark sections for visual rhythm
2. Start with a hero block for impact
3. Use cards for listing content
4. Add text-feature or columns-banner for storytelling
5. End with a CTA (banner-cta or hero-cta)
6. Ensure proper section spacing (128px vertical)

### Color Selection
- **Hero sections:** Often dark background
- **Content sections:** Usually white or light gray
- **CTA sections:** Often dark for emphasis
- **Buttons:** Use yellow glow shadow pattern

### Typography Selection
- **H1:** 90.4px (desktop), 45px (mobile) - for hero headlines only
- **H2:** 45.28px (desktop), 36px (mobile) - for section headers
- **H3:** 22.56px - for card titles, sub-sections
- **Body:** 16-18px - for readable paragraph text

---

## Checklist: Design System Compliance

When creating new content, verify:

- [ ] Using Syncopate for headings, Instrument Sans for body
- [ ] Headings are regular weight (400), not bold
- [ ] Colors use design tokens (--background-color, --accent-color, etc.)
- [ ] Images have `border-radius: 20px`
- [ ] Buttons use pill shape (`border-radius: 1600px`)
- [ ] Buttons have yellow glow shadow or simple border
- [ ] Card containers use offset shadow pattern
- [ ] Mobile-first responsive design (1-column → 2-column → 3/4-column)
- [ ] Standard breakpoints (600px, 900px, 1200px)
- [ ] Section padding is generous (128px vertical on desktop)
- [ ] Grid gaps follow 8px increments (16px, 24px, 32px, 48px, etc.)
- [ ] Transitions use standard easing (0.2s or 0.3s)
- [ ] Dark sections use `--text-color-inverse` and `--text-color-muted`

---

## File: /Users/paolo/excat/sdk-5/DESIGN_SYSTEM.md
**Generated:** 2025-11-04
**Based on:** styles.css + all block CSS files in /blocks/
