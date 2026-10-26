# MGeom.cz — handoff

Single-file static site (`mgeom.html`) rebuilt from https://www.mgeom.cz/.
Currently set up for a **client A/B review of the "O nás" (About) section**: the page
contains two switchable variants with a floating demo switch. Everything else on the
page exists once and is shared between both variants.

## Preview locally

From this folder:

```bash
python3 -m http.server 8788
# then open http://localhost:8788/mgeom.html
```

## The "O nás" A/B toggle

- **Verze 1** — quote-style bio (`„…“ — Miroslav Marinčič, jednatel`).
- **Verze 2** — profile with chips (Geodet / 20+ let praxe / Osobní přístup / Komplexní služby).
- Switch bottom-right of the page, **or** deep-link a version: `?verze=1` / `?verze=2`.
- Default is Verze 1 (`<body data-onas="v1">`).

In the markup both variants live inside `<section class="about" id="o-nas">` as
`<div class="about-grid v1">` and `<div class="about-grid v2">`; CSS shows only the active one.

### Finalizing when the client picks a winner

Everything demo-only is marked with the comment **"remove before final export"**. To ship one variant:

1. Delete the losing `<div class="about-grid vX">…</div>` block.
2. Delete that variant's scoped CSS (`.about-grid.vX …` rules).
3. Delete the three demo blocks: the `.variant-switch` CSS, the `<div class="variant-switch">` markup, and its `<script>`.
4. Remove the `data-onas` / `.about-grid { display:none }` visibility rules and just let the remaining grid show.

Ask Claude to do this in one step if preferred.

## Changes made (Oct 2026)

- **Consolidated two separate branches/folders into one source of truth** — a single
  `mgeom.html` with the variant toggle, so the shared parts can no longer drift.
- **O nás:** removed the orange block behind the photo (both variants); photo width-capped
  (420px) and height-matched to the text column; chips restyled to bordered white tiles with a
  small orange square marker.
- **Removed section subtitles:** the "O nás" eyebrow is gone; "Nabídka služeb" and
  "Realizované projekty" were promoted from subtitle to the section **title**.
- **Services:** removed the "Všechny služby / Více informací" links; replaced the hotlinked
  Webflow template icons with inline SVG line-icons (map, document, crosshair, node-network,
  pin, clipboard-check).
- **Spacing:** uniform symmetric section padding — 144px desktop / 112px tablet / 88px mobile
  (top = bottom, same across all sections). Hero keeps its own full-bleed padding.
- **Backgrounds:** alternating white/gray bands so every section boundary is visible
  (Hero → O nás white → Služby gray → Projekty white → Kontakt gray → CTA orange).
- **Footer:** removed the duplicate contact row (Telefon / E-mail / Sídlo firmy). The same
  contact details remain in the "Kontakt – Ozvěte se nám" section above the footer.

## TODO before production

- **Replace hotlinked images** — all photos/logo are hotlinked from the original
  `cdn.prod.website-files.com` (Webflow) and must be downloaded and served locally.
- **Remove the demo variant switch** once the final O nás variant is chosen (see above).
- Review copy/contact details with the client.

## Notes

- No build step, no dependencies. One font loaded from fontshare (General Sans).
- The `project/` folder holds the two detail pages linked from "Realizované projekty".
