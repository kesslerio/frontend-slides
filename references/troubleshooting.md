# Troubleshooting

## Fonts not loading
- Check font URL availability.
- Verify family names match CSS usage.
- Provide fallback stacks.

## Animations not triggering
- Confirm IntersectionObserver setup.
- Verify `.visible` class is applied on slide enter.
- Check reduced-motion override behavior.

## Scroll snap not working
- Ensure `scroll-snap-type` on document root.
- Ensure each slide has `scroll-snap-align: start`.
- Confirm no nested overflow container hijacks scroll.

## Mobile layout breakage
- Re-check viewport fit constraints (`100vh/100dvh`, overflow hidden).
- Reduce card count/content density.
- Apply short-height breakpoints (`700`, `600`, `500`).

## Performance issues
- Remove heavy repaints from scrolling layers.
- Keep animations transform/opacity only.
- Throttle or simplify cursor/scroll handlers.
- Disable expensive effects on small/low-power devices.
