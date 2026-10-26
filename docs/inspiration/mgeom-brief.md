# mgeom.cz: design brief

Source: https://www.mgeom.cz/ (Webflow, built on the "Constructor X" template). Captured 2026-10-14.
Screenshots: [screenshots/](screenshots/)

## Section order

| # | Section | Background | Layout |
|---|---|---|---|
| 1 | Header: logo left, "Poptat cenu" button right (nav links in the hamburger menu) | white | flex, space-between |
| 2 | Hero: H1 + lead + 2 buttons (primary, ghost) over a full-bleed photo with a dark overlay | photo | text column, max 595px |
| 3 | Contact strip: 3 cards (Telefon / E-mail / Sídlo firmy), pulled up over the hero edge; the 3rd card is orange | white cards, last one `#ED5521` | 3-col, divided by 1px rules |
| 4 | About: orange subtitle, H2, quote paragraph on the left; photo on the right with an orange block offset behind it | white | 2-col ~50/50 |
| 5 | **Services slider** (`data-w-id="7e1f225f…"`): subtitle + H2 on the left, ← → square arrows on the right; image cards underneath | `#F8F8F8` | horizontal slider, 2 cards visible |
| 6 | CTA band: "S čím vám poradíme?" + white solid and white ghost buttons, line-art buildings in the corners | `#ED5521` | centered |
| 7 | Projects: subtitle + H2 on the left, 2 buttons on the right; 2 project cards (plan image, title, text, date) | `#F8F8F8` | 2-col grid |
| 8 | Footer: 3-col contact bar in an outlined box → logo + tagline / menu / company info → copyright | `#151515` | 3-col |

## Section 5 bug (what step 3 will fix)

The slider has 5 slides. Slide 1 holds a CMS Collection List with **no item limit**, so all 6 services
stack vertically inside it (4,182px tall). Slides 2–5 each hold one item. The section ends up 4,659px
tall: one column of stacked cards with the other slides off to the right.
Fix in code: **one** horizontal track of the 6 cards (each service once, no duplicates), sliding
left/right with the arrow buttons, 2 cards visible on desktop and 1 on mobile.
(Fix in Webflow: set slide 1's list to Limit 1, or replace the slider with a single collection list in a flex row.)

## Palette

| Token | Hex | Use |
|---|---|---|
| primary | `#ED5521` | buttons, subtitles, links, icon tiles, CTA band |
| primary-50 | `rgba(237,85,33,.5)` | link underline track |
| primary-tint | `#FDF1ED` | light icon backgrounds |
| ink | `#151515` | headings, footer background |
| body | `#7A7A7A` | body text |
| neutral-200 | `#F8F8F8` | alternate section background |
| line | `#DFDFDF` | dividers |
| arrow-border | `#A7A7A7` | slider arrows |
| white | `#FFFFFF` | cards |

## Type scale

Font: **General Sans** (Fontshare), sans-serif fallback. Body text is weight 400, headings 600, buttons 500.

| Role | Size / line-height | Weight |
|---|---|---|
| H1 | 55 / 70px | 600 |
| H2 (section) | 38 / 54px | 600 |
| H3 (card) | 24 / 36px | 600 |
| Subtitle (eyebrow) | 18px, orange | 600 |
| Body | 18 / 30px, `#7A7A7A` | 400 |
| Button (large / header) | 18px / 16px | 500 |

## Spacing and grid

- Container: max 1248px with 24px side padding (1200px content).
- Section padding: 160px top / 144px bottom (hero 163 / 262, about 176, CTA 143).
- Gutter: 32px between cards. Card body padding 0 40px 65px. Image 4:3 (572 × 428).
- Buttons: square corners, 24 × 44px padding (large) and 18 × 30px (header), 1px border in the same color.
- Icon tile: 80px orange square that overlaps the bottom edge of the card image.
- Card shadow: `0 5px 18px rgba(46,46,46,.03)`, a 4px orange bottom border on hover (as on the site).

## What makes it work

1. **One accent color, used with discipline:** orange appears only on actions, eyebrows and icon tiles, so it reads as "click here".
2. **Square corners everywhere:** buttons, cards, arrows. It fits a technical, surveying brand.
3. **Overlap creates depth:** the contact strip sits over the hero's edge, icon tiles sit over the card images, and an orange block sits behind the about photo.
4. **A steady rhythm:** an orange eyebrow, a two-line H2, then content. Every section opens the same way.
5. **Alternating backgrounds** (white → `#F8F8F8` → orange → `#F8F8F8` → black) separate the sections without dividers.

## Build plan (after OK)

- `campaigns/mgeom/mgeom.html`: a single self-contained page with inline CSS and vanilla JS. It hotlinks the site's images (fine for an inspiration copy; swap them before any real use).
- Rebuild all 8 sections in semantic HTML with CSS grid/flex, plus the responsive breakpoints at 991 / 767 / 479px.
- Services: a scroll-snap track plus arrow buttons and the 6 unique cards.
- Check it at 600px and 375px against these screenshots.
