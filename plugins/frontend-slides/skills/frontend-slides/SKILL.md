---
name: frontend-slides
description: Use when the user wants to create an HTML slide deck, convert a PowerPoint or PPTX into a web presentation, improve an existing presentation, or share/export browser-based slides for a pitch, talk, lesson, or demo.
---

# Frontend Slides

Create zero-dependency, animation-rich HTML presentations that run entirely in the browser.

## Overview

This skill adapts the original `frontend-slides` workflow to Codex. It is for presentation work where the output should be a self-contained HTML deck, not a React app or a design-system project.

Core idea: help the user pick a visual direction by **showing concrete options**, then generate a polished deck that always fits the viewport.

## When to Use

Use this skill when the user wants to:

- create slides for a pitch deck, talk, lesson, demo, report, or launch
- convert `.ppt`/`.pptx` content into a browser-based presentation
- refine or restyle an existing HTML slide deck
- export or share a generated deck as a URL or PDF

Do **not** use this skill when the user wants:

- editable PowerPoint output as the primary artifact
- a React / Reveal.js / Slidev / Marp project with build tooling
- a one-off static infographic instead of a slide deck

## Core Principles

1. **Zero dependencies in the generated deck** — prefer a single HTML file with inline CSS/JS.
2. **Show, don't tell** — style choice should come from visual comparison when possible.
3. **Distinctive design** — avoid generic AI-slop aesthetics.
4. **Viewport fitting is non-negotiable** — every slide must fit within the viewport with no internal scrolling.

## Non-Negotiable Viewport Rules

Apply these invariants to every generated or modified slide:

- Every `.slide` must use exact viewport height and hide overflow.
- All typography and spacing must use `clamp(...)` rather than fixed desktop-only sizes.
- Images must be viewport-constrained.
- Reduced-motion support is required.
- If content does not fit, split it into more slides. Never cram and never allow scroll inside a slide.

**Before generating or editing slides, read `viewport-base.css` and include its full contents in the presentation.**

## Workflow

### Phase 0 — Detect mode

Choose one path:

- **Mode A: New presentation** — make a deck from notes or a topic.
- **Mode B: PPT conversion** — extract content from a PowerPoint, then restyle it as HTML slides.
- **Mode C: Enhancement** — improve an existing HTML presentation without breaking viewport fit.

### Mode C rules

When editing an existing deck:

1. Check the current slide density before adding anything.
2. When adding images, ensure they remain viewport-constrained.
3. When adding text, keep bullets and paragraphs within reasonable per-slide density.
4. After every edit, verify `.slide` overflow, `clamp(...)` sizing, image sizing, and fit at a common presentation size such as 1280×720.
5. If edits would overflow, proactively split content into continuation slides and tell the user.

### Phase 1 — Content discovery

Ask for the minimum information needed to structure the deck:

- purpose: pitch / teaching / conference / internal / other
- target length: short / medium / long
- content readiness: full content / rough notes / topic only
- whether inline browser editing is desired after generation
- whether there are images, screenshots, logos, or diagrams to use

If the user already supplied content, do not re-ask for it.

### Phase 1.2 — Asset evaluation

If the user provides images or a folder of assets:

1. Enumerate the files.
2. Inspect the images with the available file/image tools.
3. Judge which are usable and what role each asset should play.
4. Let the available assets influence the slide outline early; do not treat images as an afterthought.

If a logo is clearly usable, include it in style previews when practical.

### Phase 2 — Style discovery

Prefer concrete visual choice over abstract adjectives.

Two paths are allowed:

- **Guided choice** — generate 3 distinct preview slides and let the user choose.
- **Direct preset selection** — if the user already knows the style, read `STYLE_PRESETS.md` and let them pick quickly.

If generating previews:

1. Ask what the audience should feel, for example confident, energized, calm, or moved.
2. Read `STYLE_PRESETS.md`.
3. Generate 3 clearly different single-slide HTML previews.
4. Save previews to a temporary workspace folder.
5. If your environment supports opening local files, open them; otherwise give the file paths and describe the differences so the user can choose.

### Phase 3 — Generate the deck

Before generating, read these files from this skill directory:

- `html-template.md`
- `viewport-base.css`
- `animation-patterns.md`

Requirements for the generated presentation:

- single self-contained HTML file unless the user explicitly wants a folder-based output
- all CSS and JS inline in the generated deck
- include the **full** contents of `viewport-base.css`
- use non-generic fonts from Fontshare or Google Fonts, not system defaults
- add clear comments for major sections
- tailor motion to the chosen mood and respect `prefers-reduced-motion`
- if inline editing was requested, include only the edit-related code that is needed

### Phase 4 — PPT conversion

For PowerPoint conversion:

1. Run:

```bash
python scripts/extract-pptx.py <input.pptx> <output_dir>
```

2. If `python-pptx` is missing, tell the user it is required and install it only if the environment and user permissions allow.
3. Review the extracted slide titles, text blocks, image assets, and notes.
4. Confirm structure with the user if the extraction looks ambiguous.
5. Continue into style discovery and full HTML generation.

Preserve:

- slide order
- text content
- extracted image assets
- speaker notes when useful, typically as HTML comments or implementation notes

### Phase 5 — Delivery

After generating:

1. Summarize the output path, selected style, and slide count.
2. Explain navigation briefly.
3. Point out the easiest customization points: root CSS variables, font links, animation classes.
4. If inline editing is enabled, explain how to enter edit mode and save/export.

### Phase 6 — Sharing and export

If the user wants distribution help, use the bundled scripts.

#### Deploy to a live URL

Use:

```bash
bash scripts/deploy.sh <presentation-folder-or-html>
```

Notes:

- folder deployment is safer when the deck has many local assets
- check that referenced local assets actually travel with the deployment
- redeploying usually updates the same hosted project

#### Export to PDF

Use:

```bash
bash scripts/export-pdf.sh <path-to-html> [output.pdf]
```

Or smaller output:

```bash
bash scripts/export-pdf.sh <path-to-html> [output.pdf] --compact
```

Notes:

- the PDF is a static snapshot; animations are not preserved
- the export expects slides to use the `.slide` class
- relative asset paths work better than absolute filesystem paths

## Supporting Files

Read only what you need:

- `STYLE_PRESETS.md` — preset catalog for style choice
- `viewport-base.css` — mandatory viewport-safe CSS
- `html-template.md` — base HTML structure and JS expectations
- `animation-patterns.md` — motion guidance by mood
- `scripts/extract-pptx.py` — PowerPoint extractor
- `scripts/deploy.sh` — deployment helper
- `scripts/export-pdf.sh` — PDF export helper

## Quality Bar

A successful result should feel intentionally designed, not merely functional.

Checklist:

- distinctive typography and palette
- clear hierarchy on every slide
- no overflow inside slides
- sensible motion, not animation spam
- easy for the user to edit later
- works locally in a browser without a build step
