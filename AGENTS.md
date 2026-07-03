# Repository Guidelines

## Project Structure & Module Organization
- `index.html` is the entry hub that links to each activity card.
- Standalone learning activities live beside it: `addition-subtraction.html`, `times-tables.html`, `guitar-learning.html`, and `spelling-bee.html`.
- Shared assets belong in the root alongside pages (`spelling-bee.jpg`). Keep any new media under 1 MB and prefer descriptive filenames such as `fractions-quiz.png`.
- Keep each page self-contained with its styles inside `<style>` tags unless multiple files need the same rules—then extract to `/styles/common.css`.

## Build, Test, and Development Commands
- `python3 -m http.server 4173` — serves the static site locally; navigate to `http://localhost:4173`.
- `npx live-server --watch=*.html` — optional hot-reload server for rapid UI tweaks.
- `npx prettier --write "*.html"` — applies consistent formatting before committing.

## Coding Style & Naming Conventions
- Use 4-space indentation in HTML/CSS, matching existing files.
- Keep components semantic: emphasize `<section>`, `<article>`, `<button>` over generic `<div>`.
- Prefer descriptive IDs/classes in kebab-case (e.g., `quiz-wrapper`, `answer-key`).
- Inline scripts belong at the end of `<body>`; isolate reusable logic in a `scripts/` folder if it grows beyond 30 lines.
- Run Prettier (HTML/JS/CSS) before opening a pull request.

## Testing Guidelines
- No automated suite exists yet; manually verify every page in Chromium and Firefox.
- Test flows: ensure each quiz validates input, score resets on replay, and mobile breakpoints (≤600 px) keep controls tappable.
- Capture browser console output; ensure there are no warnings before sign-off.

## Commit & Pull Request Guidelines
- Match the existing imperative, concise subject style (`Limit times tables quiz to 20 random questions`).
- Reference related issues in the body (e.g., `Fixes #12`) and describe UI changes in 2–3 bullet points.
- Attach screenshots or GIFs for UI-visible adjustments; include viewport sizes tested.
- Draft PR checklist: ✅ description, ✅ manual-test notes, ✅ formatting run, ✅ assets optimized.

## Accessibility & Assets
- Maintain WCAG AA contrast; verify gradients and text via `https://webaim.org/resources/contrastchecker/`.
- Provide `alt` text for every decorative image and add `aria-live` regions for score updates to keep screen readers in sync.
