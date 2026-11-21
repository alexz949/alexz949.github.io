# alexz949.github.io

Personal academic website of Lixun (Alex) Zhang, built with [al-folio](https://github.com/alshedivat/al-folio) (MIT License).

- Edit the homepage: `_pages/about.md`
- Write a post: add a file to `_posts/` named `YYYY-MM-DD-title.md`
- Add papers: `_bibliography/papers.bib` (add `status = {preprint}` for preprints)
- Update the CV: replace `assets/pdf/Lixun_Zhang_CV.pdf` (public copy, no phone number)
- Site settings: `_config.yml`, social links: `_data/socials.yml`

Preview locally at http://localhost:4000 (needs Homebrew `ruby@3.3`):

```bash
bundle install
bundle exec jekyll serve --livereload
```

Pushing to `main` runs `.github/workflows/deploy.yml`, which builds the site into the `gh-pages` branch.
