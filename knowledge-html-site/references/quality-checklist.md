# Knowledge HTML Quality Checklist

## Before Build

- Topic promise is clear in one sentence.
- Target reader and reader outcome are named.
- Source map separates verified facts, interpretation, analogy, and unknowns.
- Board outline has 5-8 boards and each board has a purpose.
- Claims that need citations are marked before copywriting.

## Content

- Homepage gives concept, why it matters, how it works, and where to go next.
- Subpages answer one clear question each.
- Headings are memorable but not vague.
- Body copy explains, not decorates.
- Citations sit near the claims they support.
- Resource page includes primary sources, glossary, and practical next steps.

## Visual System

- Tokens are explicit: background, surface, text, muted text, accent, border, radius, type, motion.
- Components repeat consistently across pages.
- Layout uses grids, TOC, section labels, and content tiles for scanning.
- Cards are used for actual repeated items, not as decoration around every section.
- Motion is subtle and does not block reading.

## Interaction

- Every interactive element has a teaching purpose.
- Simulators have a scenario, steps, active state, progress, and final result.
- Tabs and buttons update real UI state.
- Hover/focus states are visible but restrained.
- Reduced-motion behavior does not break content access.

## Technical QA

- All local `href/src` targets exist.
- JS files pass syntax checks.
- Pages have titles and meta descriptions.
- Top nav and subpage TOC point to real pages/sections.
- Mobile layout has no horizontal overflow except intentional nav scrolling.
- External links open in a new tab when appropriate.
- Browser render, screenshots, and console checks are completed when the environment allows them.

## Final Handoff

- List created/changed files.
- State what was verified and what could not be verified.
- Mention any intentional deviations from the reference.
- Record broken links or source-site issues that were fixed locally.
