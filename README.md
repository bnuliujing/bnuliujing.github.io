# Jing Liu's Homepage

Personal academic homepage of [Jing Liu (刘晶)](https://bnuliujing.github.io/), Ph.D. student at SPST, BUPT. Research on tensor networks, Markov chain Monte Carlo, statistical physics, and machine learning.

Built with [Jekyll](https://jekyllrb.com/) and the [Minimal Light](https://github.com/yaoyao-liu/minimal-light) theme, deployed via GitHub Pages.

## Local Development

```bash
# Install dependencies
bundle install

# Serve locally at http://localhost:4000
bundle exec jekyll serve

# Build site to _site directory
bundle exec jekyll build
```

## Updating Content

- `_config.yml`: basic info (name, email, affiliation, links)
- `_data/publications.yml`: publications
- `_data/news.yml`: group news (each item has `en` and `zh` text)
- `index.md` / `zh.md`: English / Chinese page content
