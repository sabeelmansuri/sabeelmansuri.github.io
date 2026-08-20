# AGENTS.md

## What this is

A static, hand-written HTML site (personal homepage + teaching page) served by GitHub Pages at `sabeelmansuri.com` (CNAME). There is **no build system, package manager, tests, or CI** — commits to `master` (not `main`) go live directly.

## Pages and structure

- `index.html` — homepage
- `cv.html` — Curriculum Vitae
- `cse6xsdfa23.html` — Teaching page (CSE 6, "XSD FA23"); links a CV PDF (`199_poster.pdf`, don't delete)
- `newer_files/` — shared static assets (terminal.min.css, normalize.css, highlight.min.js, buttons.js, `script.js`). Do **not** rename; all pages reference it.
- `images/` — page images

## Gotchas

- **Nav menu is copy-pasted verbatim into all three pages** (the `<nav class="terminal-menu">` block). Any nav/head change must be applied to all three files to stay consistent.
- Nav links are root-relative and extensionless (`/cv`, `/cse6xsdfa23`, `/`). Keep them extensionless — GitHub Pages resolves them.
- `index.html` includes the Fathom analytics script (`script.js` with `data-site="LCUDFNYO"`) — do not remove.
- Stale absolute refs to `/manifest.json` and `/favicon/*.png` exist in every `<head>` but **those files are not in the repo** and the site works fine without them. Don't "fix" them or add the files.
- The `<!-- saved from url=(0029)/dark/ -->` comment at the top of each file is a browser-save artifact. Leave it.
- Site uses a custom light theme via CSS variables in a `<head>` `<style>` block (colors like `#4689CC`, `#C65087`, `#58A39B`). Match those when adding content.
- Copyright footer says `(c) 2026`; there's a history of yearly footer/date update commits.

## Verifying changes

No linter/tests. Serve locally and eyeball it:

```
python3 -m http.server
```
