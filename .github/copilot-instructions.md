## Purpose

These instructions help AI coding agents become productive immediately in the Jacklete repository — a small static website learning project with plain HTML, CSS and JavaScript.

## Project Snapshot

- **Type:** Static site (no build tool, no package.json).
- **Entrypoint:** `index.html` at the repository root.
- **Client files:** `index.html`, `script.js`, `style.css`.
- **Language:** Dutch primary copy (`<html lang="nl">`).

## High-level architecture / why things are structured this way

- This is a single-page static layout: `index.html` renders all content, `style.css` provides styles, and `script.js` contains minimal interactive behavior. There are no backend services or frameworks.
- The site is intentionally small and incremental — changes should be focused and conservative to preserve the learning/project tone.

## Important repository-specific details & gotchas

- The HTML currently links to `styles.css` but the repository contains `style.css`. Confirm which filename to standardize before large edits. Example: update `<link rel="stylesheet" href="styles.css" />` in `index.html` to `style.css` or rename the CSS file.
- `script.js` uses a direct DOM lookup (`getElementById("helloButton")`) and an `alert()` on click. When modifying JS, keep the DOM IDs in sync with `index.html`.
- Copy is Dutch; do not change site copy to another language without explicit instruction from the repository owner.

## Developer workflows (what works here)

- Preview: Open `index.html` in a browser or run a lightweight static server (examples below) when testing fetches or Service Worker behavior.

  - With Python (if needed): `python -m http.server 8000`
  - With npm package `http-server`: `npx http-server -c-1 . -p 8000`

- No build/test steps are present. If you add a toolchain, update this file with the new commands and a short rationale.

## Code patterns & conventions to follow

- Keep changes minimal and atomic. This repository favors incremental edits over large refactors.
- HTML structure: `header`, `main` with `section` elements (`#intro`, `#philosophy`, `#training`), and `footer`. Maintain these anchors and IDs when adding content.
- CSS scope: styles are global in `style.css`; prefer adding class names (e.g., `.card`, `.hero`) rather than relying on element selectors to avoid regressions.
- JS behavior: small, unobtrusive scripts. Avoid introducing large frameworks. If you add new JS modules, add them as separate files and reference from `index.html`.

## Examples (do / don't)

- Do: Fix the stylesheet link to match the actual filename in the repo:

  - In `index.html` change `<link rel="stylesheet" href="styles.css" />` to `<link rel="stylesheet" href="style.css" />`.

- Don't: Replace all textual content with automated translations. The content is authored in Dutch and intended as a learning project.

## When to open PRs and what to include

- Small UI/text/code fixes: one PR per change, describe exact files changed and intent.
- If adding a new dependency or dev tool (e.g., bundler, linter), include: rationale, minimal config, and updated README with how to run the new workflow.

## Files to inspect first for any change

- `index.html` — structure, IDs, linked assets
- `style.css` — global styles; preferred place for style edits
- `script.js` — interactive behavior and event listeners
- `README.md` — repository description; update if workflow changes

## Questions to ask the repo owner (add as PR checklist if uncertain)

- Should the CSS filename be `styles.css` or `style.css`? Which path should `index.html` reference?
- Are we allowed to change language copy or only add content in Dutch?

---
If any part of this guide is unclear or you'd like me to include a small suggested patch (for example, to fix the stylesheet link), tell me which approach you prefer and I will draft the change.
