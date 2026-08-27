# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is an academic personal website for Jing Liu (刘晶), Ph.D. student at SPST, BUPT. It's built using Jekyll with the Minimal Light theme and is deployed as a GitHub Pages site at `bnuliujing.github.io`.

## Technology Stack

- **Jekyll**: Static site generator (Ruby-based)
- **Minimal Light Theme**: Academic theme by yaoyao-liu
- **GitHub Pages**: Hosting platform
- **SCSS**: Styling with support for light/dark modes
- **YAML**: Data storage for publications and group news

## Directory Structure

- `_config.yml`: Main Jekyll configuration and site settings
- `_data/publications.yml`: Publication data (title, authors, conference, links)
- `_data/news.yml`: Group news items (date, en, zh)
- `_includes/`: Reusable components (publications.md)
- `_layouts/`: HTML templates (homepage.html)
- `_sass/`: SCSS source files
- `assets/`: Static assets (CSS, JS, images, files)
- `index.md`: Main site content (English)
- `zh.md`: Chinese version of site content
- `_site/`: Generated Jekyll output (do not edit)
- `Gemfile`: Ruby dependencies

## Common Development Commands

### Local Development
```bash
# Install dependencies
bundle install

# Serve locally at http://localhost:4000
bundle exec jekyll serve

# Build site to _site directory
bundle exec jekyll build
```

### Content Updates

#### Adding/Updating Publications
Edit `_data/publications.yml`:
```yaml
- title: "Paper Title"
  authors: "Author Names"
  conference: "Venue"
  pdf: "https://..."
  code: "https://..."
  image: "/assets/img/image.jpg"
```

#### Updating Site Content
- Edit `index.md` for English content
- Edit `zh.md` for Chinese content
- Update `_config.yml` for basic info (name, email, affiliation, links)

#### Adding Images/Figures
- Add new images to `assets/img/`
- Reference using relative paths in publications.yml or markdown files
- Supported formats: jpg, png, existing images include research figures

## Architecture Notes

### Theme Configuration
- Uses `minimal-light` remote theme via GitHub Pages
- Dark/light mode support with automatic detection
- Serif or Sans Serif font choice in config
- Responsive design with Bootstrap-style grid system

### Publication System
- Publications defined in YAML with multiple link types (PDF, code, bibtex)
- Template renders publications in chronological order
- Automatic image thumbnail generation with crop and styling
- Author highlighting using `<strong>` tags
- Author role convention: always bold the site owner's name (`<strong>Jing Liu</strong>`), and annotate their role only when they are NOT the first author:
  - First author: no extra annotation, even if also corresponding author. Do not add `†`/`*` markers to the entry in this case
  - Not first author: mark the site owner's role — co-first with `*` (e.g. `(* contributed equally)`), corresponding author with `†` (e.g. `(† corresponding authors)`)

### Group News System
- News defined in `_data/news.yml`, newest first; each item has `date` (displayed as-is, e.g. `YYYY-MM`), `en`, and `zh` text fields (HTML links allowed in both)
- One data file serves both languages: `_includes/news.md` renders the `en` field, `_includes/news_zh.md` renders the `zh` field
- Add news (paper accepted/published, arXiv posting, talks, awards) by prepending an entry to `main:` in `_data/news.yml`
- Wording convention: start with `Our paper on <short topic>` (a 3-6 word topic phrase — NOT the full paper title, NOT "New paper"), then a standard news verb:
  - arXiv posting: "Our paper on X is now on arXiv:NNNN.NNNNN" / 我们关于 X 的论文已上传至 arXiv
  - Accepted: "Our paper on X is accepted by/to *Journal*" / 我们关于 X 的论文被 *Journal* 接收
  - Published: "Our paper on X is published in / appeared in *Journal*" / 我们关于 X 的论文发表于 *Journal*
  - Talks: "I gave an invited talk on X at *Conference*" / 我在 *Conference* 作了关于 X 的邀请报告
  - Awards: "Our paper on X won the *Award*" / 我们关于 X 的论文获得 *Award*

### Multi-language Support
- Separate markdown files for different languages
- Chinese version: `zh.md`
- Navigation between language versions via HTML links

### Deployment
- Configured for GitHub Pages deployment
- CNAME file points to custom domain if set
- Files excluded from build listed in `_config.yml`
- Automatic rebuild on push to main branch

## File Naming Conventions

- Publication images: descriptive names (e.g., `tnmcmc.jpg`, `batchtnmc.jpg`)
- CV files: `CV.pdf` and `curriculum_vitae.pdf`
- Profile images: `avatar.png`, `favicon.png`, `favicon_dark.png`
- Backup files: `.bak` extension for temporary backups

## Important Notes

- Do not edit files in `_site/` directory (auto-generated)
- Keep `_config.yml` exclude list up to date
- Image paths should be relative to site root (starting with `/`)
- YAML files require proper indentation (2 spaces)
- Markdown files use standard formatting with Jekyll/Liquid templating support