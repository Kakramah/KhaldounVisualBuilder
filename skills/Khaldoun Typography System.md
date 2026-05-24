# Khaldoun Typography System

Use this skill when designing Arabic typography for KhaldounVisualBuilder websites and visual concepts.

## Core Rules

- Arabic RTL is the default.
- Typography must support the Khaldoun cinematic documentary visual style.
- Do not invent facts outside `input.md`.
- Public pages must never show image prompts.
- Image prompts stay only in `output/image_prompts.md`.
- Poster prompts stay only in `output/poster_prompt.md`.
- Images must be stored only in `output/images/`.
- Use relative image paths only.
- Never use `file:///` paths.
- Never use `/Users/` paths.
- Public output must be clean HTML/CSS and GitHub Pages-ready.

## Arabic Typography Rules

- Use clear Arabic hierarchy: strong title, concise section headings, readable body text, and quiet captions.
- Set `lang="ar"` and `dir="rtl"` on public HTML pages.
- Use RTL-aware alignment, spacing, punctuation, and reading flow.
- Choose type sizes that remain readable on mobile.
- Avoid cramped Arabic line-height.
- Avoid decorative typography that weakens documentary seriousness.
- Do not use negative letter spacing.
- Keep line lengths comfortable for Arabic reading.

## Recommended Styling Direction

- Titles should feel cinematic and editorial, not loud or gimmicky.
- Body text should be calm, readable, and precise.
- Captions should feel documentary: short, grounded, and visually secondary.
- Use contrast and spacing to create drama instead of excessive effects.
- Pair typography with image rhythm so text supports the visual story.

## CSS Rules

- Keep CSS clean and organized.
- Use responsive sizing with sensible breakpoints.
- Do not rely on local fonts from `/Users/` paths.
- If using web fonts, use stable public references or graceful system fallbacks.
- Ensure buttons, captions, headings, and navigation remain readable in RTL.

## Public Page Restrictions

- Do not include image prompts in visible text.
- Do not include poster prompts in visible text.
- Do not expose internal notes.
- Do not include absolute local paths.
