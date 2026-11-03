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

In `index.md`, start a list item with `<span class="date">2026</span>` to show its date right-aligned.

To add a paper, copy an entry in `_data/publications.yml`. The `pdf` link's button reads "arXiv" when it points to arxiv.org and "PDF" otherwise; `page` adds a "Project Page" button. The `image` field is optional; without it the badge (`conference_short`) is hidden too. For papers with very long author lists, add `authors_short` (lead authors, you, close collaborators, last author, with `...` for gaps); the page shows it and puts the full `authors` list behind a "Show all N authors" toggle.

## Preview locally

```sh
docker run --rm -it -p 4000:4000 -v "$PWD":/srv/jekyll -w /srv/jekyll ruby:3.3 \
  sh -c "bundle install && bundle exec jekyll serve --host 0.0.0.0"
```

Then open http://localhost:4000.
