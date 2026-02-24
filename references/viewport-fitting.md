# Viewport Fitting

## Critical Rule
Every slide must be fully visible in the viewport. No scrolling within slides.

```text
Each slide = exactly one viewport height (100vh/100dvh)
If content overflows: split into multiple slides or reduce content.
Never allow in-slide scroll.
```

## Content Density Limits

| Slide Type | Maximum Content |
|---|---|
| Title slide | 1 heading + 1 subtitle + optional tagline |
| Content slide | 1 heading + 4-6 bullets or 2 short paragraphs |
| Feature grid | 1 heading + up to 6 cards |
| Code slide | 1 heading + 8-10 lines of code |
| Quote slide | 1 quote (up to 3 lines) + attribution |
| Image slide | 1 heading + 1 image (max around 60vh) |

If a slide exceeds limits, split it.

## Overflow Prevention Checklist
- Every `.slide` has `height: 100vh; height: 100dvh; overflow: hidden;`.
- Containers constrain height (`max-height: 100%`, `overflow: hidden`).
- Text sizing uses `clamp()`.
- Spacing uses `clamp()` or viewport-relative sizing.
- Images have `max-height` constraints.
- Grids use adaptive columns (`auto-fit` + `minmax`).
- Height breakpoints exist for `700px`, `600px`, and `500px`.
- No fixed pixel heights for core content regions.

## If Content Does Not Fit
Do:
- Split into continuation slides.
- Shorten bullets to one or two lines.
- Reduce card count.
- Trim code excerpts.

Do not:
- Drop font sizes below readability thresholds.
- Remove all spacing.
- Enable in-slide scrolling.
- Overpack the viewport.

## Test Matrix
Validate at minimum:
- Desktop: `1920x1080`, `1440x900`, `1280x720`
- Tablet: `1024x768`, `768x1024`
- Mobile: `375x667`, `414x896`
- Landscape phone: `667x375`, `896x414`
