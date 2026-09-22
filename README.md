# Guanghua Li — Academic Website

Personal academic website for Guanghua Li, featuring research in GPU-accelerated data systems, graph query processing, and multi-vector retrieval, along with publications and a CV.

## Edit content

| Content                             | Location                                                   |
| ----------------------------------- | ---------------------------------------------------------- |
| Biography and profile settings      | [`_pages/about.md`](_pages/about.md)                       |
| Profile photo                       | [`assets/img/profile_pic.jpg`](assets/img/profile_pic.jpg) |
| Research projects                   | [`_projects/`](_projects/)                                 |
| Publication records and paper links | [`_bibliography/papers.bib`](_bibliography/papers.bib)     |
| Website CV                          | [`_data/cv.yml`](_data/cv.yml)                             |
| CV page and download setting        | [`_pages/cv.md`](_pages/cv.md)                             |
| Papers and slides                   | [`assets/pdf/`](assets/pdf/)                               |
| Social and contact links            | [`_data/socials.yml`](_data/socials.yml)                   |
| Site configuration                  | [`_config.yml`](_config.yml)                               |

Navigation labels, visibility, and order are set with `title`, `nav`, and `nav_order` in each page's front matter under `_pages/`.

## Local preview

With Docker running, execute from the repository root:

```bash
docker compose up -d
docker compose logs --tail=80 jekyll
```

Open [http://localhost:8080/](http://localhost:8080/). The site uses an empty `baseurl` for `gh8li.github.io`.

Stop the preview with:

```bash
docker compose down
```

To check Markdown and YAML formatting:

```bash
npm ci
npm run lint:prettier
```

The `url` and `baseurl` settings in `_config.yml` target `https://gh8li.github.io/`.

## Local layout overrides

- [`_layouts/about.liquid`](_layouts/about.liquid) places the social icons below the profile information and centers the profile text.
- [`_includes/footer.liquid`](_includes/footer.liquid) hides the default footer.

Review these overrides when upgrading the theme gems. See the [override guide](docs/ARCHITECTURE.md#local-overrides-your-site-vs-this-repo) and [`.al-folio-overrides.yml`](.al-folio-overrides.yml).

## Credits

Built with [Jekyll](https://jekyllrb.com/) and the [al-folio](https://github.com/alshedivat/al-folio) starter. Layouts and runtime features are supplied by versioned plugin gems. Template documentation remains in [`docs/`](docs/README.md), and the original [MIT license](LICENSE) is retained.
