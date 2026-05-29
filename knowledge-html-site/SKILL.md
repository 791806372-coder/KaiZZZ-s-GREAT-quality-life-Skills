---
name: knowledge-html-site
description: Build polished, source-grounded knowledge-content HTML reference sites at the level of an editorial product microsite. Use when Codex needs to create, clone, improve, or QA static HTML/CSS/JS sites for Chinese or bilingual knowledge explainers, course notes, research digests, product concepts, technical maps, source libraries, glossaries, or multi-page reference hubs.
---

# Knowledge HTML Site

## Overview

Use this skill to turn a knowledge topic plus source packet into a polished static HTML site: strong first viewport, multi-page information architecture, reusable visual system, source-backed claims, interactive explainers where useful, and QA gates before handoff.

Default to a static site unless the user or repo clearly requires a framework. For a knowledge reference hub, prefer:

- `index.html` for the cinematic overview and board entry points.
- `pages/*.html` for deep boards with a fixed table of contents.
- `assets/shared.css`, `assets/page.css`, and optional feature CSS/JS files for reusable patterns.

## Workflow

1. Ground the source packet.
   Read the user's source docs, links, notes, spreadsheets, or reference site first. Separate verified facts, interpretation, analogy, and open questions. Do not invent claims to fill visual space.

2. Define the learning promise.
   Name the target reader, the concrete question the site answers, and the final capability the reader should gain. Turn that into a one-sentence site promise and a 5-8 board outline.

3. Build the content spine.
   For each board, define `核心问题 / 关键结论 / 证据来源 / 交互或图解 / 下一步入口`. Use progressive disclosure: overview on the homepage, deep explanation on subpages, source library at the end.

4. Choose the page system.
   Use a high-signal homepage plus dense subpages:
   - Homepage: full-viewport hero, short concept definition, system diagram, why-it-matters contrast, board cards, footer source links.
   - Subpage: fixed top nav, left TOC, page header, 4-8 sections, tiles/tables/diagrams, citations near claims, previous/next links.
   - Resource page: source cards, glossary, interview/checklist material, further reading.

5. Create the visual system before coding.
   Define tokens for background, surface, text, muted text, accent, border, radius, grid, type families, and motion. Keep repeated components consistent: nav, buttons, citations, TOC, tiles, concept pills, comparison cards, flow steps, simulator panels.

6. Add interactivity only where it teaches.
   Use small native JS for reveal-on-scroll, active nav/TOC, cursor/card glow, tabs, and step-by-step simulators. Interactive elements must explain a process, compare choices, or make a concept tangible.

7. Build in slices.
   Implement shared assets first, then homepage, then one representative subpage, then remaining pages. Reuse components instead of copy-tweaking each page. Keep all local links relative.

8. Verify before handoff.
   Run syntax checks for JS, static link checks for local `href/src`, browser smoke tests when allowed, desktop and mobile visual checks, and a source/citation pass. Fix broken links even if they came from the reference.

## Quality Bar

A good knowledge HTML site should feel like a product, not a notes dump:

- The first viewport states the concept, audience, and reason to keep reading within seconds.
- The homepage shows the whole knowledge map without flattening the deep content.
- Subpages are dense but scannable: TOC, section labels, lead paragraphs, tiles, diagrams, citations, and next-step links.
- Every major claim has either a nearby source, a clear "inference" marker, or is removed.
- Visual design is distinctive but restrained: strong typography, disciplined spacing, few colors, deliberate motion, no filler decoration.
- Interactions serve explanation: simulations, tabs, comparison states, progressive traces, not generic hover effects alone.
- Mobile layout remains usable: horizontal nav can scroll, TOC becomes sticky/inline, cards collapse predictably, text never overlaps.

## Sub-Skills To Apply

Use this checklist as the repeatable capability stack:

- Source research and claim triage: collect first-hand sources, mark uncertainty, reject unsupported facts.
- Content architecture: turn a topic into boards, sections, and a reader journey.
- Editorial writing: compress concepts into memorable Chinese headings and explanatory body copy.
- Evidence design: place citations and source libraries where readers need trust.
- Visual system design: tokens, type hierarchy, component grammar, and spacing rhythm.
- Static frontend build: semantic HTML, shared CSS, small JS modules, relative links.
- Explainer interaction design: tabs, step simulators, flow diagrams, comparison cards.
- Responsive QA: desktop/mobile layout, text wrapping, nav/TOC behavior.
- Link and source audit: local link integrity, external source presence, broken-anchor fixes.
- Skill packaging: after a successful site, update this workflow with reusable findings.

## File Pattern

```text
site-root/
  index.html
  pages/
    what.html
    why.html
    method.html
    resources.html
  assets/
    shared.css
    page.css
    shared.js
    page.js
    simulator.css
    simulator.js
  docs/
    source-map.md
    qa-notes.md
```

## Verification Commands

Use equivalent commands for the local environment:

```powershell
node --check assets/shared.js
node --check assets/page.js
node --check assets/simulator.js
```

Run a local link check that treats `https:`, `mailto:`, `#`, `javascript:`, and `data:` as external/non-file targets, and verifies every relative `href/src` exists on disk.

When the browser is available, verify:

- Page identity and title.
- First meaningful screen is not blank.
- No framework or runtime overlay.
- No relevant console errors.
- One core navigation path.
- One interactive explainer path, if the page has simulators/tabs.
- Desktop plus one mobile viewport.

## References

Read `references/harness-site-case-study.md` when cloning or matching the Harness Engineering reference level.

Read `references/quality-checklist.md` before final handoff.
