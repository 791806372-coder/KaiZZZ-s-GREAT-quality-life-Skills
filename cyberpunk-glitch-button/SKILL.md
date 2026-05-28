---
name: cyberpunk-glitch-button
description: Build accessible CSS-only cyberpunk-style glitch buttons and call-to-action controls. Use when Codex is asked to create, clone, polish, or repair futuristic neon UI buttons, Cyberpunk 2077-inspired hover effects, CSS clip-path angled corners, glitch or scanline interactions, or reusable HTML/CSS button templates for websites, games, dashboards, landing pages, and knowledge-content HTML.
---

# Cyberpunk Glitch Button

## Goal

Create polished cyberpunk-style buttons with semantic markup, clipped angular shapes, layered neon edges, short glitch animation, and motion/accessibility fallbacks.

Use original implementation code. Treat external articles as inspiration for technique, not as code to copy verbatim.

## Workflow

1. Inspect the target UI before adding the effect. Match the existing design density, typography scale, and color system.
2. Use a semantic `<button>` for actions or `<a>` for navigation. Keep the real label as visible text.
3. Add one decorative duplicate label for the glitch layer and mark it `aria-hidden="true"`.
4. Build the shape with CSS variables:
   - `--cbg-cut` for the `clip-path` polygon.
   - `--cbg-bg`, `--cbg-ink`, `--cbg-edge`, and `--cbg-hot` for palette control.
   - `--cbg-edge-size` for the offset neon edge.
5. Create the angled button body with `::after` and the shifted neon edge with `::before`. Avoid real borders when they would disturb text alignment.
6. Create the glitch overlay as an absolutely positioned child that appears on `:hover` and `:focus-visible`.
7. Animate only `transform`, `opacity`, and `clip-path` slices. Keep the animation short and jumpy instead of smooth.
8. Add `@media (prefers-reduced-motion: reduce)` so the button still has a clear hover/focus state without animated glitching.
9. Verify the button at mobile and desktop widths. The label must not overflow, focus must be visible, and the hit area should remain comfortable.

## Starter Template

For a standalone implementation, copy from `assets/cyberpunk-glitch-button.html` and adapt:

- Text label and decorative duplicate.
- Color variables on `.cbg-button` or modifier classes.
- `--cbg-cut` if the tag notch or corner angle needs a different silhouette.
- Font family to match the project; do not introduce a remote font unless the project already allows it.

## Integration Rules

- Prefix classes or map the pattern into the project's component naming. Do not leak generic `.button` styles.
- Keep the duplicate glitch text synchronized with the visible label.
- Use `focus-visible` styling at least as prominent as hover styling.
- Avoid infinite always-on animation. Trigger it from interaction or use it sparingly for a hero CTA.
- For dark pages, test contrast for both the normal body color and the cyan/red glitch shadows.
- For UI libraries, implement this as a small component wrapper rather than scattering pseudo-element CSS across pages.

## Deeper Notes

Read `references/implementation-notes.md` when you need the rationale, source provenance, variations, or troubleshooting notes.

## Final Check

Before finishing, confirm:

- The effect works with keyboard focus, not only mouse hover.
- `prefers-reduced-motion` removes the animated slicing.
- The button still reads cleanly when the glitch layer is hidden.
- The implementation does not copy protected article code verbatim.
- The CSS is scoped tightly enough to reuse in a larger page.
