---
name: frontend-slides
description: Create stunning, animation-rich HTML presentations from scratch or by converting PowerPoint files. Use when the user wants to build a presentation, convert a PPT/PPTX to web, or create slides for a talk/pitch. Helps non-designers discover their aesthetic through visual exploration rather than abstract choices.
---

# Frontend Slides Skill

## Mission
Create production-quality, animation-rich HTML presentations that run directly in the browser with zero build tooling.

## Legacy Phrase Compatibility
- **Show, don't tell**: prefer visual exploration with preview choices over abstract style questionnaires.
- **No AI slop defaults**: avoid generic templates and clichéd aesthetics (including purple-on-white default looks).
- **No build tools by default**: generate single-file HTML with inline CSS/JS; do not require npm or bundlers unless explicitly requested.

## When To Use
- Build a new slide deck from notes, outline, or raw text.
- Convert `.ppt`/`.pptx` into a web slideshow with preserved content and assets.
- Improve an existing HTML presentation (design, motion, accessibility, responsiveness).
- Run visual style discovery for users who cannot name a design direction up front.

## When Not To Use
- The user wants a framework-heavy app or a multi-page product UI.
- The output is not a slide deck.
- The user explicitly wants dependency-heavy bundling workflows.

## Workflow Summary
1. Detect mode: `new`, `ppt-conversion`, or `enhancement`.
2. Gather content: purpose, length, available material, and constraints.
3. Pick style path:
- `strict mode`: guided discovery with 3 previews, then selection.
- `fast mode`: direct preset selection and immediate generation.
4. Generate deck: single HTML output + optional local assets.
5. Validate: viewport fit, navigation, animation triggers, accessibility, reduced-motion behavior.
6. Deliver: file path, style used, slide count, and clear customization pointers.

## Hard Non-Negotiables
1. Zero dependencies by default: one self-contained HTML file with inline CSS/JS.
2. Viewport fitting is mandatory: every slide must fully fit `100vh/100dvh` with no in-slide scrolling.
3. Every `.slide` must enforce `overflow: hidden` and respect content density limits.
4. All typography and spacing must scale responsively using `clamp()` or viewport-relative units.
5. If content does not fit, split slides; never cram content or add slide-internal scroll.
6. Keep anti-generic design discipline: avoid default AI aesthetics and boilerplate visual patterns.
7. Use semantic HTML and preserve keyboard navigation support.
8. Include reduced-motion behavior and avoid excessive animation cost on low-power devices.
9. Provide touch/swipe, keyboard, and wheel navigation for generated decks.
10. For conversion, preserve slide order and extracted assets unless user asks otherwise.
11. Keep code commented where decisions are non-obvious, especially animation/control logic.
12. Do not introduce npm/build-tool requirements unless the user explicitly opts in.

## Output Contract
- Primary output: `[presentation-name].html` (single-file, browser-runnable).
- Optional output for conversion/import flows: `[presentation-name]-assets/` or `assets/`.
- Optional preview workspace during style discovery: `.claude-design/slide-previews/`.
- Final report fields: output file path, selected preset/style direction, slide count, and any constraints/tradeoffs applied (viewport-fit splits, content compression choices).

## Routing
- Viewport guarantees, density limits, and fit testing: [references/viewport-fitting.md](references/viewport-fitting.md)
- Mandatory CSS and JS baseline architecture: [references/css-foundation.md](references/css-foundation.md)
- Preset catalog, mood mapping, anti-slop style guardrails: [references/design-presets.md](references/design-presets.md)
- PPT/PPTX extraction and conversion workflow: [references/ppt-conversion.md](references/ppt-conversion.md)
- Preflight and delivery QA gates: [references/checklist.md](references/checklist.md)

Apply non-negotiables first, then load routed references as needed for the active mode.
