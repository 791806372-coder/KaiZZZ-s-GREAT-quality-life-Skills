# Cursor Sand Implementation Notes

## Parts

- CSS: `.cursor-sand` is a fixed full-screen canvas layer with `pointer-events: none`.
- HTML: place one `<canvas class="cursor-sand" id="cursorSand" aria-hidden="true"></canvas>` near the start of `<body>`.
- JavaScript: `startCursorSand()` creates a compact WebGL shader, stores recent pointer splats, and redraws a grainy ink field each frame.

## Layering

- The starter template puts the canvas behind content and above the page background. Raise it above content only when the design intentionally wants cursor ink to tint text or controls.
- If a page also has a hero spotlight cursor, keep that effect separate. The spotlight should own text switching; `cursor-sand` should own the global pointer trail.
- On dark pages, reduce opacity or change `mix-blend-mode` from `multiply` to `screen`, `soft-light`, or normal alpha blending.

## Performance

- The template already avoids coarse-pointer devices and `prefers-reduced-motion: reduce`.
- Lower `maxSplats` first if the page stutters.
- Reduce `window.devicePixelRatio` clamping from `2` to `1.5` or `1` on heavy pages.
- Reduce splat radius growth if the effect becomes too cloudy.
- Avoid initializing more than one cursor canvas per page.

## React Or Vite

- Put the canvas in the top-level layout component.
- Wrap `startCursorSand()` in an effect that runs once on mount.
- Add cleanup if the component can unmount: remove the pointer listener and cancel the animation frame.
- Keep the shader strings and `startCursorSand()` helper outside render logic. Store them in a helper module or a static asset.

## Common Fixes

- Blank effect: check WebGL availability, canvas size, and whether the canvas is hidden by CSS.
- No fade-in: define `--ease` or replace it with a concrete easing in the transition.
- Clicks blocked: confirm `pointer-events: none` is still on `.cursor-sand`.
- Effect covers too much UI: reduce `.cursor-sand` opacity or z-index.
- Hover feels wrong: update the `event.target.closest(...)` selector to match the page's actual interactive elements.
