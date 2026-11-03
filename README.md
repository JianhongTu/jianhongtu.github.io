# jianhongtu.github.io

Personal academic homepage built on the [Minimal Light](https://github.com/yaoyao-liu/minimal-light) Jekyll theme. GitHub Pages builds it directly from `main`.

## Where to edit

| What | File |
|---|---|
| Name, position, email, sidebar links, photo | `_config.yml` |
| About, Teaching, Service, Awards | `index.md` |
| Publications | `_data/publications.yml` |
| Paper thumbnails | `assets/img/publication_preview/` |
| CV PDF | `assets/pdf/jianhongtu_CV.pdf` |

To add a paper, copy an entry in `_data/publications.yml`. The `image` field is optional; without it the badge (`conference_short`) is hidden too.

## Preview locally

```sh
docker run --rm -it -p 4000:4000 -v "$PWD":/srv/jekyll -w /srv/jekyll ruby:3.3 \
  sh -c "bundle install && bundle exec jekyll serve --host 0.0.0.0"
```

Then open http://localhost:4000.
