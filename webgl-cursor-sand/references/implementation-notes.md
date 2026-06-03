# Cursor Sand Implementation Notes

## Parts

- CSS: `.cursor-sand` is a fixed full-screen canvas layer with `pointer-events: none`.
- HTML: place one `<canvas class="cursor-sand" id="cursorSand" aria-hidden="true"></canvas>` near the start of `<body>`.
- JavaScript: `startCursor()` creates WebGL framebuffers, shader programs, pointer splats, and a render loop.

## Layering

- Keep the canvas above normal content and below modals, command palettes, dropdowns, and debug overlays.
- If a page also has a hero spotlight cursor, keep that effect separate. The spotlight should own text switching; `cursor-sand` should own the global pointer trail.
- On dark pages, reduce opacity or change `mix-blend-mode` from `multiply` to `screen`, `soft-light`, or normal alpha blending.

## Performance

- The template already avoids coarse-pointer devices and `prefers-reduced-motion: reduce`.
- Lower `dyeResolution` first if the page stutters.
- Lower `simResolution`, `curl`, or `pressureIterations` only after checking that the visual feel is still acceptable.
- Avoid initializing more than one cursor canvas per page.

## React Or Vite

- Put the canvas in the top-level layout component.
- Wrap `startCursor()` in an effect that runs once on mount.
- Add cleanup if the component can unmount: remove the pointer listener and cancel the animation frame.
- Keep the shader code out of render logic. Store it in a helper module or a static asset.

## Common Fixes

- Blank effect: check WebGL availability, canvas size, and whether the canvas is hidden by CSS.
- No fade-in: define `--ease` or replace it with a concrete easing in the transition.
- Clicks blocked: confirm `pointer-events: none` is still on `.cursor-sand`.
- Effect covers too much UI: reduce `.cursor-sand` opacity or z-index.
- Hover feels wrong: update the `event.target.closest(...)` selector to match the page's actual interactive elements.
