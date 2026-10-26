# AGENTS.md

Guidance for agents working in/with this repository.

## What this is

The public website of the **National Recording Preservation Foundation** (recordingpreservation.org) — a static site built with the Jekyll framework and deployed on GitHub Pages. It began as the Serif theme from Zerostatic Themes, which assumed a Netlify deployment, and was substantially rewritten in 2024–2025.

**`SITE-DOCUMENTATION.md` is the canonical content guide.** It documents how to add news posts, podcast episodes, people, grants, programs, pages, and redirects, plus the branding/style reference (colors, fonts, logos, buttons, breakpoints). Read the relevant section before adding content, and update it when conventions change.

## Build & run

```bash
bundle exec jekyll serve      # local server at http://localhost:4000
bundle exec jekyll build      # output to _site/ (gitignored)
```

Python helper scripts use a pyenv virtualenv named `nrpf-env` (see `.python-version`; the directory is gitignored). pyenv activates it automatically on `cd` into the repo — no manual `source` needed.

## Layout

- `_config.yml` — collections, permalinks, per-type layout defaults, logo config
- `_data/` — YAML/JSON driving much of the site (`contact.yml`, `menus.yml`, `donate.yml`, `supporters.json`, `nrpf_grants.json`, `podcast-soundfiles.json`, …)
- `_layouts/`, `_includes/` — page templates and partials
- `_sass/` — `components/`, `pages/`, vendored `bootstrap/` and `libraries/`
- `assets/css/style.scss` — **the entry stylesheet**; brand color and font variables are declared at the top, then partials are imported
- Collections: `_posts` (features), `_news`, `_team`, `_programs`, `_grants`, `_services`, `_pages`
- `redirect-*.md` at the root — old-URL redirect stubs using the `redirect` layout

## Conventions

- Style with the Sass variables (`$primary`, `$nrpf-orange`, `$steel`, `$font-family-heading`, …) rather than raw hex or font names. Add new brand values in `assets/css/style.scss`, not in component partials.
- Internal links use `{% link path/to/file.md %}`; asset paths use `relative_url` or `site.baseurl`.
- Organization facts (EIN, address, contact, bank/UPIC details) come from `_data/contact.yml` — never hardcode them into pages or includes.
- Grant record pages in `_grants/` are **generated**. Edit the source CSV and rerun `_grants/generate_grants_pages.py <csv>`; it deletes and rewrites files matching `20??-*.md`. Don't hand-edit those.
- Team/board list helpers live in `_team/generate-people-lists.ipynb`.
- Image sizes and social-share defaults are specified in SITE-DOCUMENTATION.md → Additional Resources.

## Housekeeping

- `_site/`, `.jekyll-cache/`, `vendor/bundle`, and `images/team/original/` are gitignored — never commit them.
- Commit messages in this repo are short, lowercase, imperative ("close 2026 grants cfp").

## Communication

- Be concise. Don't restate what was done after each action; the user can read the diff and the tool output. In most cases, report only necessary information: the result, anything unexpected, decisions that need their input, or very high level summary.
- In cases where more complex or ongoing decisions are underway, propose putting the details into a plan document or other reference, which can be used by all contributors to the project.
- Skip preambles, recaps and closing summaries that repeat earlier messages.
- Direct user to high-level and significant changes (not every detail!). Users are able to read and consider the changes themselves.
