# Cover Page Layout Specification

This document defines the precise layout, typography, spacing, and required elements for a professional GDD cover page. Follow this spec when generating cover pages in any output format (docx, pdf, pptx). The cover page is the first thing a publisher, investor, or team member sees — it must communicate professionalism instantly.

---

## Page Setup

| Property | Value |
|----------|-------|
| Page size | A4 (210mm × 297mm) or US Letter (8.5" × 11") |
| Orientation | Portrait only |
| Margins | Top: 0, Left: 0, Right: 0, Bottom: 0 (full bleed for background) |
| Effective content area margins | Top: 25mm, Left: 25mm, Right: 25mm, Bottom: 25mm |

---

## Layout Structure

```
┌─────────────────────────────────────────────────────────────────────┐
│░░░░░░░░░░░░░░░░ TOP ACCENT BAR (full width, 8mm tall) ░░░░░░░░░░░░░│  ← Dark navy background
├─────────────────────────────────────────────────────────────────────┤
│                                                                       │
│                                                                       │
│                                                                       │  ← Empty space: 50-60mm
│                                                                       │
│                                                                       │
│                                                                       │
│                  ┌─────────────────────────────────┐                 │
│                  │                                 │                 │
│                  │         GAME TITLE              │  ← Centered     │
│                  │     (36-48pt, Dark Navy Bold)   │    or left-     │
│                  │                                 │    aligned      │
│                  └─────────────────────────────────┘                 │
│                                                                       │
│               ─────────────────────────────────                      │  ← Accent line (40-60mm wide, gold/blue)
│                                                                       │
│              "Tagline — italic, 14-16pt, grey"                        │  ← Tagline
│                                                                       │
│                                                                       │  ← Space: 20-30mm
│                                                                       │
│           Genre  ·  Platform  ·  Target Audience                     │  ← Metadata (10-12pt, grey)
│                                                                       │
│                                                                       │  ← Space: 40-60mm
│                                                                       │
│                         Studio Name                                  │  ← Studio (12-14pt, Bold, Navy)
│                   Game Design Document                               │  ← Document type (11pt, grey)
│                   Version: v0.1  ·  January 2025                     │  ← Version + Date (10pt, grey)
│                   Lead Designer: [Name]                              │  ← Designers (10pt, grey)
│                                                                       │
│                                                                       │  ← Space: 15-25mm
│                                                                       │
│  CONFIDENTIAL — For internal use and authorized partners only.       │  ← Confidentiality (8-9pt, italic, light grey)
│  Do not distribute without written permission.                        │
│                                                                       │
├─────────────────────────────────────────────────────────────────────┤
│░░░░░░░░░░░░░░░░ BOTTOM ACCENT BAR (full width, 8mm tall) ░░░░░░░░░░│  ← Same dark navy
└─────────────────────────────────────────────────────────────────────┘
```

---

## Element Specifications

### Top Accent Bar
- **Dimensions:** Full page width × 8mm tall
- **Position:** Top of page, bleeds to edges
- **Color:** Dark Navy RGB(26, 60, 94)
- **Content:** None (decoration only) OR studio name in white 7pt right-aligned with 8mm margin

### Game Title
- **Font family:** Cambria (headings font)
- **Font size:** 36-48pt depending on title length
  - Short title (1-2 words): 48pt
  - Medium title (3-4 words): 40pt
  - Long title (5+ words): 32-36pt
- **Font weight:** Bold
- **Color:** Dark Navy RGB(26, 60, 94)
- **Alignment:** Center (preferred) or Left
- **Case:** ALL CAPS or Title Case — decide per title (ALL CAPS for single/short titles, Title Case for long titles)
- **Position:** Vertical center of top third of page (~80-100mm from top)
- **Letter spacing:** Slightly expanded (+5%) for ALL CAPS titles

### Accent Separator Line
- **Width:** 40-60mm, centered horizontally
- **Thickness:** 1.5-2pt
- **Color:** Mid Blue RGB(41, 89, 133) OR Gold RGB(200, 150, 40) — choose one consistently
- **Position:** 8-12mm below game title
- **Style:** Solid line (no dashes)

### Tagline
- **Font family:** Calibri (body font)
- **Font size:** 14-16pt
- **Font weight:** Regular, Italic
- **Color:** Dark Grey RGB(80, 80, 80)
- **Alignment:** Center
- **Position:** 6-8mm below accent line
- **Max length:** 1 line preferred; 2 lines acceptable for longer taglines
- **Format:** Quoted with curly quotes preferred: *"Every map is a memory. Every death rewrites the world."*

### Genre / Platform / Audience Line
- **Font family:** Calibri
- **Font size:** 11-12pt
- **Font weight:** Regular
- **Color:** Medium Grey RGB(100, 100, 100)
- **Alignment:** Center
- **Position:** 15-20mm below tagline
- **Format:** `[Genre]  ·  [Platform(s)]  ·  [Audience]`
- **Separator:** Middle dot (·) with 2 spaces each side
- **Example:** `Roguelike Deckbuilder  ·  PC (Steam), Switch  ·  Ages 22–40, Midcore PC Gamers`

### Studio Information Block
- **Position:** Bottom third of page, above confidentiality notice
- **Alignment:** Center
- **Elements and sizes:**
  - Studio name: 13-14pt, Bold, Dark Navy RGB(26, 60, 94)
  - "Game Design Document": 11pt, Regular, Medium Grey
  - "Version: v0.X  ·  [Month YYYY]": 10pt, Regular, Medium Grey
  - "Lead Designer(s): [Name(s)]": 10pt, Regular, Medium Grey
- **Line spacing:** 1.1× between each element

### Confidentiality Notice
- **Font family:** Calibri
- **Font size:** 8-9pt
- **Font weight:** Regular, Italic
- **Color:** Light Grey RGB(130, 130, 130)
- **Alignment:** Center
- **Position:** 15-20mm above bottom accent bar
- **Text:** `"CONFIDENTIAL — For internal use and authorized partners only. Do not distribute without written permission."`
- **Width:** Limited to 120-140mm (centered block) — not full page width

### Bottom Accent Bar
- **Identical to top accent bar:** Full width × 8mm, Dark Navy RGB(26, 60, 94)
- **Position:** Bottom of page, bleeds to edges
- **Content:** None (decoration) OR copyright/contact line in white 7pt centered

---

## Optional Background Treatments

For projects with a strong visual identity, a background treatment can be applied. Always keep text legibility as the priority — never use dark text on dark background.

### Option A: Pure White (Default)
Background: White `#FFFFFF`. Top/bottom bars are the only color. Clean, professional, suitable for all genres.

### Option B: Subtle Texture
Background: Very light noise/grain texture at 3-5% opacity over white. Adds tactile quality without affecting legibility.

### Option C: Dark Background (For Dark/Horror/Sci-Fi Games)
Background: Dark Navy `#0E0E1A`. All text shifts to light colors:
- Game Title: Gold or White
- Tagline: Silver/Off-white (italic)
- Metadata: Light grey
- Studio info: Off-white
- Bars: Can be removed (already dark background) or use accent gold/blue
- Confidentiality: Light grey

### Option D: Gradient Band
A subtle gradient behind the title area only (center 40% of the page). Background `#F5F7FA` to `#FFFFFF`. Does not affect text colors.

---

## Version History Table (Page 2 or Verso)

The cover page is typically followed by a version history table. Format:

| Column | Content |
|--------|---------|
| Version | v0.1, v0.2, v1.0 |
| Date | Month YYYY |
| Author | Lead designer name |
| Summary of Changes | Brief description of what changed in this version |

**Table styling:**
- Header row: Dark Navy background, White Bold text, 10pt
- Data rows: Alternating white / very light blue
- Borders: Light grey 0.5pt all cells
- Font: Calibri 10pt

---

## Common Anti-Patterns

| Anti-Pattern | Why It Fails | Fix |
|-------------|--------------|-----|
| Title too small (< 28pt) | Doesn't command attention | Increase to minimum 32pt |
| No version number | Document can't be identified in email threads | Always include version |
| No confidentiality notice | Legal and professional expectation for commercial documents | Always include it |
| Tagline missing | Cover tells you the title but not the experience | Write a tagline that captures the feeling |
| Too many decorative elements | Looks amateur, distracts from content | White space is professional — use it |
| Genre/audience line missing | Publisher can't immediately categorize | Always include genre · platform · audience |
| Studio name larger than game title | Studio's brand > game — wrong hierarchy | Game title is always the largest text element |
| Dark text on image/photo background | Legibility destroyed | Never place text over background images without semi-opaque overlay |
| Decorative fonts for title | Impossible to read at a glance | Stick to Cambria/Garamond/Helvetica — design through spacing and weight, not font choice |

---

## Cover Page Checklist

Before finalizing the cover page, verify:

- [ ] Game title is the largest text element on the page
- [ ] Version number is present and current
- [ ] Document date matches current version
- [ ] Studio/developer name is accurate
- [ ] Lead designer name(s) are spelled correctly
- [ ] Genre, platform, and audience are up-to-date
- [ ] Confidentiality notice is included
- [ ] Tagline is present and specific (not generic)
- [ ] Top and bottom accent bars are visually consistent
- [ ] No spelling errors (this is the first thing anyone reads)
- [ ] Text is legible at 100% zoom AND when printed
- [ ] Font choices are consistent with the rest of the document
