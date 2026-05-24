# KhaldounVisualBuilder Operating Rules

This project is called `KhaldounVisualBuilder`.

`KhaldounVisualBuilder` is a permanent reusable workspace for transforming raw user text into a cinematic Arabic visual website package.

## Source Input

- The user will paste raw text into `input.md`.
- `input.md` is the source of truth for each build.
- Codex must read and understand `input.md` before proposing or generating output.
- Do not invent facts, names, claims, dates, places, statistics, or story details outside `input.md`.
- If important information is missing, either leave it general or ask the user for clarification before building.

## Required Transformation

When the user asks Codex to build from `input.md`, Codex must transform the source text into:

- A responsive Arabic RTL HTML website.
- A poster/cover concept.
- Image prompts for GPT Image.
- An image plan with organized image slots.
- GitHub Pages-ready output.

## Required Pre-Build Plan

Before building or creating generated website files, Codex must show the user:

- Content summary.
- Website structure.
- Image plan.
- Files to create or update.

Codex must wait for the user to approve or request changes before building the final website output.

## Output Locations

- All generated website files must go inside `output/`.
- The GitHub Pages-ready website must be generated from files inside `output/`.
- Images must be stored in `output/images/`.
- Image prompts must stay only in `output/image_prompts.md`.
- The poster prompt must stay only in `output/poster_prompt.md`.
- Public website files must never show image prompts.

## Path Rules

- All image paths must be relative.
- Use paths such as `images/hero.jpg`, `images/section-01.jpg`, or `images/poster.jpg`.
- Never use `file:///` paths.
- Never use `/Users/` paths.
- Do not use absolute local filesystem paths in public website files.

## Language And Direction

- Arabic RTL is the default.
- Public pages should use Arabic language content unless the user asks otherwise.
- HTML should declare Arabic and RTL defaults, such as `lang="ar"` and `dir="rtl"`.

## Visual System

- Style must follow the Khaldoun cinematic documentary visual system.
- Favor cinematic contrast, documentary realism, editorial composition, dramatic but restrained lighting, strong hierarchy, and refined Arabic typography.
- The result should feel like a serious visual documentary package, not a generic template or marketing landing page.

## Public Website Rules

- Public website files must be clean, browsable, responsive, and GitHub Pages-ready.
- Public pages must never include internal planning notes, image prompts, prompt engineering text, or local machine paths.
- Keep prompts and production notes in their dedicated markdown files only.
