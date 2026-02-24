# Checklist

## Preflight
- Mode detected (`new`, `ppt-conversion`, `enhancement`).
- Content scope confirmed.
- Style path selected (`strict mode` preview flow or `fast mode` direct preset).

## Generation QA
- Every slide fits viewport; no in-slide scrolling.
- Typography and spacing use responsive scaling.
- Navigation works: keyboard, wheel, touch/swipe.
- Reveal animations trigger correctly via observer.
- Reduced-motion behavior is present.
- Semantic structure and basic accessibility labels are present.

## Conversion QA (when applicable)
- Slide order preserved.
- Text content preserved.
- Images extracted and referenced correctly.
- Notes handled per user preference.

## Delivery
- Output file path reported.
- Style/preset reported.
- Slide count reported.
- Any content splitting/tradeoffs reported.
- Optional preview directory cleaned if no longer needed.

## Strict vs Fast
- Strict mode: guided mood prompts + 3 preview comparison before full generation.
- Fast mode: direct preset and immediate generation with only essential checks.
