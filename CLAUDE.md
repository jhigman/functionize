# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

Personal site for Julian Higman — senior Ruby on Rails consultant, positioned around AI-native delivery (agentic implementation, automated review, production feedback loops). Plain static HTML and CSS, no framework and no build step, hosted on GitHub Pages at julianhigman.com.

## Commands

```sh
# Local dev server (http://localhost:8000)
python3 -m http.server 8000
```

There is no build step. What is in the repo is what is served.

## Files

- **`index.html`** — the entire site: nav, hero, About, How I Build, Who I Help, Work, Recent Projects, Stack, Pricing, Contact, footer. Sections are anchor targets matching the nav links.
- **`css/main.css`** — all styles. Design tokens live in `:root`. Reusable classes: `.container`, `.bg-light` (alternating section background), `.clean-list` (bordered row list), `.service-grid` / `.service-card` (two-column card grid), `.tag-cloud` / `.tag`, `.section-sub`.
- **`CNAME`** — custom domain (`julianhigman.com`); must stay in the repo root.
- **`.nojekyll`** — disables Jekyll processing on GitHub Pages.

## Conventions

- Sections alternate white and `.bg-light` backgrounds — keep the alternation intact when adding or reordering sections.
- Adding a section means adding a matching `#id` and a nav link; the nav is a single non-wrapping flex row on desktop, so keep new labels short.
- British English throughout.
- Google Analytics (`G-12408PWDSZ`) is inlined in `<head>`.

## Deployment

Pushing to `master` deploys via GitHub Pages.
