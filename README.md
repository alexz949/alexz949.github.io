# alexz949.github.io

Personal academic website of Lixun (Alex) Zhang, built with [al-folio](https://github.com/alshedivat/al-folio) (MIT License).

- Edit the homepage: `_pages/about.md`
- Write a post: add a file to `_posts/` named `YYYY-MM-DD-title.md`
- Add papers: `_bibliography/papers.bib`, then set `nav: true` in `_pages/publications.md`
- Site settings: `_config.yml`, social links: `_data/socials.yml`

Pushing to `main` runs `.github/workflows/deploy.yml`, which builds the site into the `gh-pages` branch.
