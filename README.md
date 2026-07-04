# ethanbudge.github.io

Personal site and blog: academic research, personal research, downloadable
datasets, and an about page. Built with Jekyll so it deploys on GitHub Pages
with no build step of your own.

**Not published yet.** This branch (`task/3-website-setup`) is scaffolding
for review -- GitHub Pages hasn't been enabled for this repo, so nothing here
is live. Enable it (Settings &rarr; Pages) once you're happy with the result.

## Structure

```
_config.yml           Site title, nav plugins, collection/permalink config
_data/navigation.yml   Top nav links -- edit to add/remove/reorder sections
_data/datasets.yml     Dataset catalog (see "Adding a dataset" below)
_sass/_variables.scss  Colors, fonts, spacing -- edit this first to retheme
_sass/_base.scss       Element-level typography/reset
_sass/_layout.scss     Site chrome + per-section component styles
_layouts/              default (chrome) / home / page / post / section
_includes/             head, header, footer, sidebar (recent-posts widget)
_academic_research/    Collection backing the Academic Research section
_personal_research/    Collection backing the Personal Research section
academic-research/     Section index page (lists the collection above)
personal-research/     Section index page (lists the collection above)
datasets/               Datasets landing + academic/ + commercial/ subsections
about/                  About page (bio, photo, CV, links)
assets/                 Sass entry point, images, CV
```

## Adding a blog post

Academic Research and Personal Research are each a Jekyll collection.

1. Copy the relevant `_TEMPLATE.md` (`_academic_research/_TEMPLATE.md` or
   `_personal_research/_TEMPLATE.md`) to a new file in the same folder --
   the filename doesn't matter, only the `date` front matter field does.
2. Fill in `title`, `date`, `excerpt`, and the body.
3. Set `published: true` (or delete that line).

Delete the `2026-01-01-example-*.md` placeholder post in each collection
once you've published a real one.

## Adding a dataset

Add an entry to `_data/datasets.yml` under `academic:` or `commercial:` --
no template or page edits required. See that file's comments for the
expected fields, and `datasets/commercial/index.md` for the paywall
recommendation (Gumroad/Payhip) for commercial entries.

## Filling in personal details

- **Photo:** replace `assets/images/profile-placeholder.svg` with a real
  image and update the `src` in `about/index.md`.
- **CV:** drop a PDF at `assets/cv/cv.pdf` (see `assets/cv/README.md`) --
  the About page already links there.
- **Bio, academic homepage link:** edit the placeholders directly in
  `about/index.md`.

## Local preview

Requires Ruby + Bundler (already on macOS; on Linux, `apt install ruby-full
build-essential zlib1g-dev`).

```bash
bundle install
bundle exec jekyll serve
# -> http://localhost:4000
```

`bundle exec jekyll serve --livereload` will auto-refresh on file changes.
