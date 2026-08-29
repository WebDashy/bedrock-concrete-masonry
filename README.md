# Bedrock Concrete & Masonry — WebDashy Template

A multi-page, SEO-structured marketing site template for a concrete and
masonry contractor, built for use as a live preview template in
[WebDashy](https://github.com/WebDashy/webdashy).

This is **Layout 4** of WebDashy's 8-layout template system — same page
structure convention as every other layout (home, services hub, one page
per service, about, projects, contact), a distinct workwear/technical
visual language (Big Shoulders Display + Public Sans + IBM Plex Mono,
mustard-yellow accent on kraft-paper cream, heavy black hairline borders,
sharp 0px corners, a numbered ledger-table services section) so it reads
as a genuinely different design choice next to the other layouts, not a
reskin.

Built with [Jekyll](https://jekyllrb.com/) using only the plugins GitHub
Pages runs natively (`jekyll-seo-tag`, `jekyll-sitemap`) — no local build
step required to deploy: push to `main` and GitHub Pages builds it for you.

## Structure

Same convention as every WebDashy layout:

```
_config.yml           site-wide settings + business info
_layouts/default.html shared page shell — head/SEO tags, header, footer
_includes/             header.html, footer.html
assets/css/styles.css  all styling — CSS custom properties at the top are
                       what change when this layout gets reskinned for a
                       different WebDashy category
assets/js/script.js    mobile nav toggle
index.html             home
services/index.html    services hub
services/<slug>/       one folder per service
about/                 company story + testimonials
projects/               project gallery
contact/                contact form + info
robots.txt              points at the auto-generated sitemap.xml
```

## Reskinning for a different category

This layout's structural CSS (grid, spacing, component shapes) is meant to
stay fixed — only these should change when adapting it to a new WebDashy
category:

- The `:root` custom properties at the top of `assets/css/styles.css`
  (`--bg`, `--ink`, `--accent`, `--font-display`, `--font-body`, etc.)
- The Google Fonts `<link>` in `_layouts/default.html` to match a new
  `--font-display`/`--font-body` pairing
- All written content (business name, services, copy, testimonials) —
  `_config.yml`'s `business:` block plus each page's text

## Local preview

```bash
bundle install
bundle exec jekyll serve
```

Then open `http://localhost:4000/bedrock-concrete-masonry/`.

## Deploying

**GitHub Pages** (this repo): Settings → Pages → Deploy from branch →
`main` / `/ (root)`. GitHub builds the Jekyll site automatically on every
push.
