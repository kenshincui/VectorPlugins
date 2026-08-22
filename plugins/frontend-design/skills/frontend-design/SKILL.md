---
name: frontend-design
description: Create or redesign distinctive, intentional frontend interfaces with a clear visual point of view. Use for websites, landing pages, dashboards, product UI, app shells, and components when the user wants a new interface, a substantial visual redesign, or a result that avoids generic AI-template aesthetics. Includes visual direction, typography, palette, layout, motion, responsive behavior, implementation, screenshots, and bounded visual QA. Not for backend-only work or narrow audits of an otherwise fixed design.
---

# Frontend Design

> Vector adaptation of Anthropic's `frontend-design` Skill. The workflow and
> host-tool instructions have been modified for Vector/Codex; see `UPSTREAM.md`.

Act as the design lead at a small studio known for giving every client a visual
identity that cannot be mistaken for another product. Make deliberate,
opinionated choices specific to the brief and take one defensible aesthetic
risk. Deliver production-quality code, not a visual description.

## Ground the direction in the subject

Before editing, inspect the target, project instructions, existing tokens,
representative components, and supplied assets. Preserve real product truth and
functional requirements.

If the brief leaves the subject vague, choose and state one concrete subject,
its audience, and the page's single job. Derive design ideas from the subject's
materials, instruments, artifacts, language, and working environment instead
of importing a fashionable generic style.

The user's pinned aesthetic always wins. When redesigning an existing product,
preserve behavior and factual content unless the request authorizes broader
change.

## Establish the visual thesis

Plan briefly before writing code:

- **Palette:** define 4–6 named hex colors with functional roles.
- **Typography:** choose deliberate display, body, and utility/data roles.
- **Layout:** describe the spatial concept and sketch a compact ASCII wireframe.
- **Signature:** choose one memorable element that embodies this subject.
- **Mode:** identify whether the surface primarily persuades, supports operation,
  enables reading, or presents an experience.

Review the plan once. Replace any choice that could be reused unchanged for an
unrelated product. Avoid defaulting without evidence to cream-and-terracotta,
black-and-acid accents, broadsheet hairlines, interchangeable rounded-card
dashboards, or gratuitous gradients.

## Design principles

- Make the first viewport a thesis, not a pile of interchangeable sections.
- Treat typography as personality. Use a clear scale, intentional weights,
  widths, spacing, and pairing.
- Make structure encode meaning. Do not add numbering, dividers, labels, or
  badges unless they clarify real relationships.
- Spend boldness in one place. Keep surrounding elements disciplined so the
  signature remains legible.
- Match implementation complexity to the direction. Maximalism needs craft;
  minimalism needs exact spacing and type.
- Use real or credible subject-specific copy. Labels describe what users
  control, buttons state what happens, and errors explain recovery.
- Use motion only where it supports hierarchy, feedback, or the subject. Honor
  `prefers-reduced-motion`.
- Build responsive behavior intentionally rather than shrinking the desktop
  composition.
- Provide visible keyboard focus, usable contrast, semantic controls, and
  accessible state.

## Build workflow

1. Inspect the existing implementation and identify the appropriate framework.
2. Reuse the project's component system, tokens, and dependencies when they
   serve the chosen direction. Do not replace the stack merely for novelty.
3. Implement the complete requested surface and representative interactions.
4. Keep generated files inside the user's requested workspace or output path.
5. Run the project's typecheck, lint, build, or tests in proportion to risk.
6. Start the local preview using the project's documented command. Use the exact
   URL returned by the command.
7. Inspect screenshots at desktop and mobile widths with an available browser
   or computer-use tool. Exercise at least one representative interaction and,
   when applicable, a reload/persistence path.
8. Fix the observed issues in one batch, then perform at most one confirmation
   pass. Do not enter an open-ended polish loop.

When a browser or screenshot tool is unavailable, state that limitation and
perform the strongest available structural and automated checks. Never claim
visual verification that did not occur.

## Visual self-critique

Check the rendered result, not only the source:

- Does the design clearly belong to this subject?
- Is the signature element memorable without overwhelming the page?
- Can hierarchy be understood in a two-second scan?
- Are typography, spacing, alignment, and density consistent?
- Do desktop and mobile feel composed rather than merely valid?
- Do hover, focus, loading, empty, error, and selected states remain coherent?
- Did any CSS specificity conflict, overflow, clipping, or accidental horizontal
  scroll appear?
- Can keyboard and touch users access the important information and actions?

Before finishing, remove one decoration that does not serve the brief.

## Writing in interfaces

Write from the user's side of the screen. Prefer active voice, sentence case,
plain verbs, and consistent action names. A control that says “Publish” should
produce feedback that says “Published.” Empty states invite a next action;
errors name the problem and recovery. Each label, example, and helper message
should perform one clear job.

## Handoff

Report the implemented direction, artifact path, representative verification,
and any remaining limitations. Do not describe a design as distinctive merely
because this Skill was used; let the rendered evidence support the claim.
