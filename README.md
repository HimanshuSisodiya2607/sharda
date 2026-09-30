# Sharda Construction — homepage

Single-file, dependency-free homepage. The centrepiece is a scroll-driven
construction sequence: a tower stays fixed on screen while page scroll builds it
through ten stages (site → piling → columns → steel → slabs → glazing → facade →
landscape → demobilisation → handover).

## Files

- `index.html` — the standalone site. Double-click it, or open with any browser.
- `artifact-source.html` — the same page as published to claude.ai (no
  `<!doctype>` / `<html>` / `<head>` wrapper, since the artifact host supplies
  that). Edit this one if you want to republish the artifact; edit `index.html`
  for the local/hosted site.

Live artifact: https://claude.ai/artifact/AQeNCeghivvE3332dZjbtp

## Local preview with a server (optional)

    cd ~/Desktop/sharda-construction
    python3 -m http.server 8080
    # then open http://localhost:8080

## Stack

No build step, no framework, no images. Typography is Archivo + Instrument Sans
+ IBM Plex Mono from Google Fonts; every visual — the hero, project cards,
viaduct, blueprints and the construction sequence itself — is generated SVG.
Requires an internet connection only for the fonts; it degrades to system fonts
offline.

## Editing notes

- Construction stages: the `STAGES` array in the script, plus the `P(el, start,
  end, kind)` calls that register each element's scroll window (0 → 1 across the
  pinned section).
- Section height controls pacing: `.rig-wrap { height: 760vh }`.
- Palette and type scale: the `:root` custom properties at the top of the CSS.
- Placeholder content to replace with real details — client names in the trust
  grid, phone/email, CIN, GSTIN, RERA number, project figures.
- `prefers-reduced-motion` is respected: the sequence renders the completed
  building and the pinned sections unpin.
