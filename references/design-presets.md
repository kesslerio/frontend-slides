# Design Presets

## Selection Paths
- Guided discovery (default): ask mood, generate three preview files, user picks one.
- Direct selection: user names a preset and generation starts immediately.

## Preset Catalog

| Preset | Vibe | Best For |
|---|---|---|
| Bold Signal | Confident, high-impact | Pitch decks, keynotes |
| Electric Studio | Clean, professional | Agency, client delivery |
| Creative Voltage | Energetic, retro-modern | Creative/product pitches |
| Dark Botanical | Elegant, premium | Luxury and brand narratives |
| Notebook Tabs | Editorial, organized | Reports, internal reviews |
| Pastel Geometry | Friendly, approachable | Product explainers |
| Split Pastel | Playful, modern | Creative agencies |
| Vintage Editorial | Witty, personality-led | Personal brand storytelling |
| Neon Cyber | Futuristic, tech-forward | Startups and developer audiences |
| Terminal Green | Developer-focused | Tooling, API decks |
| Swiss Modern | Minimal, precise | Corporate and data-heavy decks |
| Paper & Ink | Literary, thoughtful | Story-led presentations |

## Mood to Preset Mapping
- Impressed/Confident: Bold Signal, Electric Studio, Dark Botanical
- Excited/Energized: Creative Voltage, Neon Cyber, Split Pastel
- Calm/Focused: Notebook Tabs, Paper & Ink, Swiss Modern
- Inspired/Moved: Dark Botanical, Vintage Editorial, Pastel Geometry

## Preview Workspace
Create style previews in:

```text
.claude-design/slide-previews/
  style-a.html
  style-b.html
  style-c.html
```

Each preview should be one title slide, self-contained, and animation-demonstrative.

## Anti-Slop Guardrails
Never default to:
- Purple-on-white gradient cliches
- Inter/Roboto/system-font-first aesthetics
- Generic hero + card template repetition

Prefer:
- Distinctive font pairings
- Cohesive palette with clear accent strategy
- Atmospheric backgrounds with subtle depth
- One signature motion moment per style direction
