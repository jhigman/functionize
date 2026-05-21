# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

Static Jekyll site for Julian Higman (senior Rails consultant), hosted on GitHub Pages at julianhigman.com. Built on the Airspace theme (Bootstrap 3, jQuery).

## Commands

```sh
# Install dependencies (first time or after Gemfile changes)
bundle install --path vendor/bundle

# Run local dev server (http://localhost:4000)
bundle exec jekyll serve

# Build static output to _site/
bundle exec jekyll build
```

## Architecture

- **`_config.yml`** — site settings (title, URL, Google Analytics ID)
- **`_layouts/`** — `default.html` wraps all pages with head/header/footer; `page.html` and `post.html` extend it
- **`_includes/`** — `head.html`, `header.html`, `footer.html`, `google-analytics.html` partials
- **`_data/`** — `funfacts.yml`, `testimonials.yml` drive data-driven sections via Liquid loops
- **`_posts/`** — Markdown blog posts (YYYY-MM-DD-title.md format)
- **`_site/`** — Jekyll build output; never edit directly, it is regenerated on each build
- **`index.html`**, **`blog.html`**, **`contact.html`**, **`work.html`** — top-level pages with `layout: page` front matter

Several sections in `index.html` (testimonials, fun facts, call-to-action) are wrapped in `<div class="hidden">` — they are template remnants kept in place but not displayed.

## Deployment

Pushing to `master` deploys via GitHub Pages. The `CNAME` file (`julianhigman.com`) must remain in the repo root — it is listed under `keep_files` in `_config.yml` to survive `jekyll build` cleanup.
