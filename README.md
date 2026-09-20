# audreyyang25.github.io

Personal website of Audrey Yang, built with [al-folio](https://github.com/alshedivat/al-folio) v1.x on Jekyll and deployed to GitHub Pages.

## Where content lives

| Content                 | Location                                                    |
| ----------------------- | ----------------------------------------------------------- |
| Bio / homepage          | `_pages/about.md`                                           |
| Profile photo           | `assets/img/prof_pic.jpg`                                   |
| Social links            | `_data/socials.yml`                                         |
| CV                      | `_data/cv.yml` (rendered at `/cv/`), PDF in `assets/pdf/`   |
| Publications            | `_bibliography/papers.bib`, previews in `assets/img/publication_preview/` |
| Projects                | `_projects/*.md`                                            |
| News                    | `_news/*.md`                                                |
| Blog posts              | `_posts/YYYY-MM-DD-title.md`                                |
| Teaching                | `_teachings/*.md`                                           |
| Site settings           | `_config.yml`                                               |

## Local development

```bash
bundle install
bundle exec jekyll serve   # http://localhost:4000/
```

See [`docs/`](docs/) for the full al-folio customization guides and [`AGENTS.md`](AGENTS.md) for the rules on what belongs in this repo versus the theme gems.
