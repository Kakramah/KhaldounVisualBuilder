# Khaldoun Auto Build & Publish Skill

Use this skill when turning `input.md` into a GitHub Pages-ready static output package.

## Core Rules

- Arabic RTL is the default.
- Follow the Khaldoun cinematic documentary visual style.
- Do not invent facts outside `input.md`.
- All generated website files must go inside `output/`.
- Images must be stored only in `output/images/`.
- Image prompts must stay only in `output/image_prompts.md`.
- The poster prompt must stay only in `output/poster_prompt.md`.
- Public website files must never show image prompts.
- Use relative image paths only.
- Never use `file:///` paths.
- Never use `/Users/` paths.
- Output must be clean HTML/CSS and GitHub Pages-ready.
- Do not commit or push unless the user explicitly asks.

## Required Build Sequence

1. Read `input.md`.
2. Summarize the content without adding unsupported facts.
3. Show the proposed website structure.
4. Show the image plan.
5. Show the files to create or update.
6. Wait for user approval before creating the final website files.
7. Create or update files only inside the approved locations.
8. Verify that public pages do not expose prompts or local paths.

## File Placement Rules

- Public HTML, CSS, and any public JavaScript belong inside `output/`.
- Website images belong inside `output/images/`.
- GPT Image prompts belong only in `output/image_prompts.md`.
- Poster prompt belongs only in `output/poster_prompt.md`.
- Do not scatter generated files outside `output/`.
- Keep `input.md`, `AGENTS.md`, `README.md`, and `skills/` as project control files.

## GitHub Pages Rules

- Keep output static and portable.
- Use `index.html` as the public entry point when building a single-page website.
- Use relative paths for CSS, JavaScript, pages, and images.
- Avoid local development-only paths.
- Avoid private machine paths.
- The `output/` folder should be publishable as the GitHub Pages source.

## Final Verification Checklist

- Public pages are Arabic RTL.
- Public pages are responsive.
- Public pages do not show image prompts.
- Public pages do not show poster prompts.
- No `file:///` paths appear in public files.
- No `/Users/` paths appear in public files.
- Image references are relative.
- Images are expected under `output/images/`.
- The site can be published from `output/`.
