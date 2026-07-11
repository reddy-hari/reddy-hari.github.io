# reddy-hari.github.io

Source for my personal site, live at **<https://reddy-hari.github.io>**.

Built with [Jekyll](https://jekyllrb.com/) and the [Minima](https://github.com/jekyll/minima)
theme. All site content lives in the [`docs/`](docs/) folder.

## Prerequisites

- **Ruby** (with development headers) and **Bundler** — `gem install bundler`
- On Windows, run everything inside **WSL**; the Ruby/Jekyll toolchain is set up
  there, not in native Windows.

## Setup

```bash
cd docs
bundle install   # installs Jekyll + gems from docs/Gemfile
```

## Run locally

```bash
cd docs
bundle exec jekyll serve
```

Then open <http://localhost:4000>. Jekyll rebuilds on save and live-reloads —
except for `_config.yml`, which requires restarting the server.

## Project layout

```text
docs/
├── _config.yml       # site settings (title, nav, plugins)
├── _data/            # structured content (cv.yml, activities.yml)
├── _includes/        # head/header/footer partials
├── _layouts/         # page templates (cv, research, activities, …)
├── assets/main.scss  # styles (Minima + dark theme + overrides)
├── *.markdown        # the pages themselves (about, research, cv, …)
└── Gemfile           # Ruby dependencies
```

## How it deploys

This repo is a **GitHub Pages user site**. GitHub treats a repository named
`<username>.github.io` specially: it is published at `https://<username>.github.io`.
Because this repo is `reddy-hari/reddy-hari.github.io`, it serves at
<https://reddy-hari.github.io>.

Deployment is fully automatic — there is no CI workflow to run:

1. Push to the `master` branch.
2. GitHub Pages is configured (in **Settings → Pages**) to deploy from a branch:
   `master` / `/docs`.
3. GitHub builds the site server-side with the `github-pages` gem (pinned in
   `docs/Gemfile`) and publishes the result to the live URL within a minute or two.

There is no build step to run or artifact to commit — just push the source.

## Notes

- A `node_modules/` folder may appear at the repo root; it is a cache created by
  the markdownlint VS Code extension. It is gitignored and irrelevant to the
  build — safe to ignore or delete.
