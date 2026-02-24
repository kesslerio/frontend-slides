# Animation Patterns

Production-safe snippets and pattern intentions.

## Entrance Patterns

```css
/* Fade + Slide Up */
.reveal {
  opacity: 0;
  transform: translateY(30px);
  transition: opacity 0.6s var(--ease-out-expo, cubic-bezier(0.16, 1, 0.3, 1)), transform 0.6s var(--ease-out-expo, cubic-bezier(0.16, 1, 0.3, 1));
}
.slide.visible .reveal {
  opacity: 1;
  transform: translateY(0);
}

/* Scale In */
.reveal-scale {
  opacity: 0;
  transform: scale(0.92);
  transition: opacity 0.6s, transform 0.6s var(--ease-out-expo, cubic-bezier(0.16, 1, 0.3, 1));
}

/* Slide From Left */
.reveal-left {
  opacity: 0;
  transform: translateX(-40px);
  transition: opacity 0.6s, transform 0.6s var(--ease-out-expo, cubic-bezier(0.16, 1, 0.3, 1));
}

/* Blur In */
.reveal-blur {
  opacity: 0;
  filter: blur(10px);
  transition: opacity 0.8s, filter 0.8s var(--ease-out-expo, cubic-bezier(0.16, 1, 0.3, 1));
}
```

## Background Motion Patterns
- Gradient mesh breathing (slow cycles)
- Noise texture overlays (fixed, non-scrolling)
- Grid pattern parallax at low amplitude

## Interaction Patterns
- Direction-aware hover fills
- Subtle tilt cards (transform-only)
- Ripple-from-click coordinate feedback

## Guardrails
- Animate transform/opacity only.
- Respect reduced-motion preferences.
- Keep loops subtle and battery-safe.
