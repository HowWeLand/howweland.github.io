# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

`howweland.github.io` is a personal portfolio/resume site for James Myint, published via GitHub Pages
at `https://howweland.github.io`. It is a small set of static, self-contained HTML files — there is no
build system, package manager, framework, or dependency graph. Every page inlines its own `<style>` and
(where needed) `<script>` block; there is no shared CSS/JS file.

## Structure

- `index.html` — the main portfolio page (hero, experience, research, skills, education, contact). This
  is the canonical source of truth for bio/contact/résumé content.
- `card.html` — a stripped-down mobile "digital business card" view (locks to portrait orientation,
  tap-to-call/email/link contact rows). Contact details and tags here are a condensed duplicate of
  `index.html` and should be kept in sync with it manually when either changes.
- `stats/index.html` — a public GitHub-traffic dashboard (clones/views/referrers/paths) rendered client-side
  with Chart.js (loaded from a CDN, no local install). It fetches `stats/data.json` at runtime.
- `stats/data.json` — the data backing the dashboard above. **This file is not edited by hand or by any
  workflow in this repository.** It is overwritten daily by an external automation (commits authored by
  `github-actions[bot]`, message `chore: update stats dashboard <date>`) that lives outside this repo. Do
  not try to "fix" its generation here — there is nothing in `.github/workflows/` that produces it. It is
  a large (~300KB+) JSON blob; read it with `offset`/`limit` or `head`/`jq`, not a full file read.
- `.github/workflows/static.yml` — the only CI/CD in this repo. On every push to `main` (or manual
  dispatch) it uploads the entire repository as a Pages artifact and deploys it as-is — no build/compile
  step runs. This means whatever is committed to `main` is exactly what gets served in production.

## Working in this repo

- There is no `package.json`, no build tool, no linter, no test suite, and no dev server config. There is
  nothing to install and nothing to compile.
- To preview changes, open the HTML file directly in a browser, or serve the directory locally (e.g.
  `python3 -m http.server`) and visit `/`, `/card.html`, or `/stats/`.
- Deployment is automatic: pushing to `main` triggers `static.yml` and republishes the whole repo. There is
  no staging environment or preview build — treat `main` as production.
- Each HTML file defines its own color palette as CSS custom properties in `:root` (an amber-on-black
  "terminal" aesthetic shared across `index.html`, `card.html`, and `stats/index.html`). When editing
  styles, follow the existing token names (`--bg`, `--amber`, `--text-dim`, etc.) rather than introducing
  new hardcoded colors.
- Contact information (email, phone, GitHub, LinkedIn) appears independently in `index.html` (hero section
  and footer contact section) and `card.html`. There is no single source of truth enforced in code — if you
  update one, check the others.
- Fonts are pulled from Google Fonts via `<link>` tags (IBM Plex Mono / Share Tech Mono); Chart.js in
  `stats/index.html` is pulled from a jsDelivr CDN. Both are external, unpinned-by-lockfile dependencies —
  there's no vendoring in this repo.
