---
name: create-presentations
description: Create, edit, restructure, render, or visually validate PowerPoint presentations in PPTX format. Use when the user asks for PPT, PowerPoint, slides, a presentation deck, speaker notes, slide redesign, or conversion of source material into a deck.
---

# PowerPoint 演示文稿

Create a valid `.pptx` and verify both structure and rendered appearance.

## Workflow

1. Confirm audience, purpose, language, approximate slide count, and any supplied template or brand assets. Infer reasonable defaults when these do not materially change the request.
2. Check for Python 3, `python-pptx`, Node presentation libraries, and `soffice`. Select an available local toolchain.
3. Build an answer-first story: title, executive summary, supporting sections, evidence, and next steps. One slide should communicate one primary message.
4. Use editable text, shapes, tables, and charts where practical. Avoid rasterizing all content into slide-sized images.
5. Save the PPTX, reopen it programmatically, and verify slide count, titles, notes, and relationship integrity.
6. Render to PDF or images with LibreOffice when available. Inspect for clipped text, overlaps, empty slides, missing fonts, broken images, and unreadable charts; revise until acceptable.

## Design defaults

- Use a restrained color system, strong hierarchy, generous whitespace, and consistent margins.
- Keep body text readable in presentation conditions; shorten content instead of shrinking excessively.
- Add citations or source notes for externally sourced claims and charts.
- Preserve an existing template's masters and layouts when editing a supplied deck.

## Guardrails

- Do not claim visual QA if no renderer was available; state that only structural validation was completed.
- Do not embed confidential source material into sample assets or commit generated user decks to a plugin repository.
