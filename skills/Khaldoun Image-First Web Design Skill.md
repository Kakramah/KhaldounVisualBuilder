# Khaldoun Image-First Web Design Skill

Use this skill when planning or building the public Arabic RTL website inside `output/`.

## Core Rules

- Arabic RTL is the default for all public website pages.
- Build image-first pages: visuals should lead the structure, rhythm, and emotional pacing.
- Follow the Khaldoun cinematic documentary visual style.
- Do not invent facts outside `input.md`.
- All generated website files must go inside `output/`.
- Images must be stored only in `output/images/`.
- Use relative image paths only.
- Never use `file:///` paths.
- Never use `/Users/` paths.
- Public pages must never show image prompts.
- Image prompts must stay only in `output/image_prompts.md`.
- Poster prompts must stay only in `output/poster_prompt.md`.
- Output must be clean HTML/CSS and GitHub Pages-ready.

## Page Design Rules

- Start from the content in `input.md`, then shape the page around strong visual sections.
- Use full-width image moments, poster-like openings, documentary section breaks, and editorial pacing.
- Keep the first screen visually strong and immediately connected to the subject.
- Use Arabic headings, captions, and body copy in RTL flow.
- Make the page responsive across mobile and desktop.
- Avoid generic marketing layouts unless the input clearly asks for one.
- Do not place prompt text, production notes, or internal planning notes on public pages.

## Image Integration Rules

- Use image slots from the image plan.
- Reference images with paths such as `images/hero.jpg`, `images/poster.jpg`, or `images/section-01.jpg`.
- Include useful Arabic alt text.
- If an image has not been generated yet, use a clean placeholder area or expected relative path without local filesystem references.
- Do not use absolute local paths.

## HTML/CSS Rules

- Keep HTML semantic and readable.
- Set Arabic defaults, including `lang="ar"` and `dir="rtl"`.
- Keep CSS organized and maintainable.
- Avoid unnecessary frameworks unless the user asks for them.
- Keep public output static and deployable on GitHub Pages.
- Make sure content does not overlap, clip awkwardly, or depend on local machine paths.

## GitHub Pages Readiness

- Public entry files belong in `output/`.
- Use relative links between pages and assets.
- Avoid build steps unless explicitly requested.
- Keep the final public website easy to publish from the `output/` folder.
