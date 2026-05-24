# KhaldounVisualBuilder

`KhaldounVisualBuilder` is a reusable workspace for turning raw text into an Arabic RTL cinematic website package.

## How To Use

1. Paste your text into `input.md`.
2. Ask Codex to build from `input.md`.
3. Review the plan Codex shows you.
4. Allow file creation when the plan looks right.
5. Generate images separately if needed, using the prompts saved in `output/image_prompts.md` and `output/poster_prompt.md`.
6. Publish the files in `output/` when ready.

## Important Rules

- Website files are generated inside `output/`.
- Website images are stored inside `output/images/`.
- Public website pages do not show image prompts.
- Image paths must be relative.
- Arabic RTL is the default.
