# rogeriolino.com

Portfolio + blog, built with Jekyll and served by GitHub Pages from `master`.

- Portfolio content: `_data/profile.yml` (rendered by `_layouts/home.html`)
- Blog posts: `_posts/` → `/blog/:year/:month/:day/:slug/`
- Old Octopress URLs (`/:year/:month/:day/:slug/`, `/categorias/*`, `/page/N/`, `/archives/`, `/about/`, `/projetos/`) redirect via `jekyll-redirect-from`.
- Migrated from Octopress 2 (2015); the old Octopress source branch was removed after migration.

## Run locally

```sh
export PATH="/opt/homebrew/opt/ruby@3.3/bin:$PATH"
bundle config set --local path vendor/bundle
bundle install
bundle exec jekyll serve --livereload
```
