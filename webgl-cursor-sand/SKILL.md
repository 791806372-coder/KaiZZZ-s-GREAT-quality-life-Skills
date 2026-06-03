---
name: webgl-cursor-sand
description: Add, adapt, or repair a polished WebGL cursor-sand mouse trail effect for HTML/CSS/JS pages. Use when Codex is asked to reuse a MiMo-style or dodjoy/xiaomeng-style sand, ink, fluid, smoke, or particle cursor overlay; replace cursor-glow/data-glow effects; or package an interactive pointer-following WebGL canvas for presentation pages, landing pages, demos, game sites, and web apps.
---

# WebGL Cursor Sand

## Goal

Add a subtle full-screen WebGL cursor trail that feels like sand, ink, or smoke following the pointer. Keep the effect decorative, non-blocking, and safe to remove.

Use original project code from `assets/cursor-sand-template.html` as the starter implementation.

## Workflow

1. Inspect the target page first. Identify existing cursor effects, hero hover effects, modals, nav bars, and any canvas already on the page.
2. Copy the three required pieces from `assets/cursor-sand-template.html`:
   - `.cursor-sand` CSS and its media queries.
   - `<canvas class="cursor-sand" id="cursorSand" aria-hidden="true"></canvas>` near the start of `<body>`.
   - The script block from `const cursorSand = ...` through `startCursor();`.
3. Remove older competing cursor layers such as `cursor-glow`, `data-glow`, or duplicate pointer listeners unless the user explicitly wants both.
4. Tune the integration:
   - Set `z-index` below modals and critical overlays, but above normal page content.
   - Keep `pointer-events: none` on the canvas.
   - Define `--ease` or replace `var(--ease)` with a concrete easing.
   - Adjust `opacity` and `mix-blend-mode` to match the page background.
5. Customize the hover-target selector inside the pointer listener:
   - Default: `a[href], button, .h-node, .sim-btn`.
   - Replace project-specific classes with real interactive selectors from the target app.
6. Preserve unrelated hero or title effects. For example, a MiMo-style circular title text switch can stay as a separate `.spot` effect while `cursor-sand` handles only the global trail.
7. Verify in a real browser. The effect should appear only on fine-pointer devices, respect reduced motion, hide on mobile, and never block clicks.

## When To Read More

Read `references/implementation-notes.md` when you need to tune performance, change the visual feel, debug blank WebGL output, or adapt the effect into React/Vite.

## Verification

Before finishing, confirm:

- The page has exactly one `#cursorSand` canvas.
- The JavaScript parses without syntax errors.
- The effect initializes only when WebGL is available and `prefers-reduced-motion` is not active.
- Links and buttons still click normally.
- Mobile or coarse-pointer views hide the canvas.
- Old cursor effects requested for removal are actually gone.
