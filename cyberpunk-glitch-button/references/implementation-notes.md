# Implementation Notes

## Source Inspiration

Primary inspiration:

- SitePoint, "Recreate the Cyberpunk 2077 Button Glitch Effect in CSS" by Jhey Tompkins, published December 16, 2020 and updated November 15, 2024: https://www.sitepoint.com/recreate-the-cyberpunk-2077-button-glitch-effect-in-css/
- MDN `clip-path` reference for polygon clipping and browser behavior: https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path
- MDN `@keyframes` reference for CSS animation structure: https://developer.mozilla.org/en-US/docs/Web/CSS/@keyframes
- MDN `prefers-reduced-motion` reference for motion accessibility: https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-reduced-motion

Use these as technique references. Generate fresh CSS and markup for the user's project.

## Technique Breakdown

The reusable pattern has four layers:

1. Real label: the accessible text the user sees and assistive tech reads.
2. Body layer: a clipped polygon background.
3. Edge layer: the same clipped polygon shifted a few pixels to create a neon edge without a layout-affecting border.
4. Glitch layer: a decorative duplicate label that briefly appears as horizontal slices with small x/y shifts.

The key design decision is to put the clipped shape on pseudo-elements and overlays instead of clipping the whole button. That keeps the label readable and makes the edge easier to control.

## Markup Contract

Use this shape:

```html
<button class="cbg-button" type="button">
  <span class="cbg-button__label">Deploy</span>
  <span class="cbg-button__glitch" aria-hidden="true">Deploy</span>
</button>
```

If adding a decorative status tag, keep it hidden from assistive tech:

```html
<span class="cbg-button__tag" aria-hidden="true">R25</span>
```

## CSS Contract

Use custom properties for all reusable decisions:

- Shape: `--cbg-cut`
- Colors: `--cbg-bg`, `--cbg-ink`, `--cbg-edge`, `--cbg-hot`
- Sizing: `--cbg-edge-size`, `--cbg-pad-x`, `--cbg-pad-y`

Keep the button root `position: relative` and `isolation: isolate` so negative z-index pseudo-elements cannot disappear behind unrelated page layers.

## Variations

- Yellow CTA: use yellow body, black ink, cyan edge, red glitch shadow.
- Cyan CTA: use cyan body, black ink, yellow edge, red glitch shadow.
- Dark stealth CTA: use near-black body, off-white ink, cyan edge, magenta or red glitch shadow.
- Small toolbar control: reduce padding and remove the decorative tag; keep the focus ring.

## Troubleshooting

- If the edge is invisible, check that `::before` is behind `::after` but still inside the isolated stacking context.
- If text becomes hard to read, lower the glitch opacity or reduce text-shadow distance.
- If the shape clips the label, adjust padding before changing the polygon.
- If the animation feels noisy, run it once on hover instead of infinitely.
- If the project uses utility CSS, keep the keyframes in a component stylesheet rather than inline class soup.
