# Khaldoun Image Generation Skill

Use this skill when creating image plans, GPT Image prompts, or poster prompts from `input.md`.

## Core Rules

- Arabic RTL is the default context for all generated visual concepts.
- Follow the Khaldoun cinematic documentary visual style.
- Do not invent facts, people, places, dates, events, quotes, claims, or details outside `input.md`.
- If the source text is vague, create visual prompts that are atmospheric and general rather than factual.
- Public website pages must never show image prompts.
- Image prompts must be written only in `output/image_prompts.md`.
- The poster prompt must be written only in `output/poster_prompt.md`.
- Images must be stored only in `output/images/`.
- Use relative image paths only, such as `images/hero.jpg`.
- Never use `file:///` paths.
- Never use `/Users/` paths.

## Image Prompt Rules

- Write prompts in clear production language.
- Describe the intended image, composition, lighting, mood, camera feel, color palette, and subject treatment.
- Keep prompts faithful to `input.md`.
- Avoid unsupported factual specificity.
- Avoid text-heavy image prompts unless the user specifically requests typography inside the image.
- Do not include image prompts inside `index.html`, CSS, JavaScript, or public content pages.

## Image Slot Rules

- Every image slot should have:
  - A clear filename.
  - A purpose.
  - A short alt text in Arabic.
  - A GPT Image prompt.
- Store planned generated images under `output/images/`.
- Reference images from public pages with paths like `images/filename.jpg`.

## Poster Prompt Rules

- The poster or cover concept must feel cinematic, documentary, and editorial.
- The poster prompt belongs only in `output/poster_prompt.md`.
- The poster image, when generated, should be stored in `output/images/`.
- Public pages may reference the final poster image, but must not display the poster prompt.

## Output Quality

- Make prompts visually specific, practical, and ready for image generation.
- Keep the visual system consistent across all image slots.
- Prepare assets so the website can remain GitHub Pages-ready.
