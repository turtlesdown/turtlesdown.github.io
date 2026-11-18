# turtlesdown.dev

Gunnar Aasen's blog. A static site built with [Hugo](https://gohugo.io/) and
published to GitHub Pages by the workflow in `.github/workflows/deploy.yml`.

## Write a post

    hugo new content posts/my-post-title.md

Fill in `title` and `description` (the one-line summary shown on the landing
page), write the post in Markdown, and remove `draft: true` when it's ready.

## Preview

    hugo server --buildDrafts

Then open http://localhost:1313/.

## Publish

Push to `main`. The site deploys in about a minute.

## Where things live

| Path                   | What it is                                     |
| ---------------------- | ---------------------------------------------- |
| `hugo.toml`            | Title, tagline, links, navigation              |
| `content/posts/`       | Posts                                          |
| `content/about.md`     | About page                                     |
| `layouts/`             | Templates (no theme; everything is in here)    |
| `assets/css/main.css`  | The whole stylesheet; colors are at the top    |
| `static/img/`          | Masthead drawing and social card               |

Built and tested with Hugo 0.169.0. The typeface is Newsreader, self-hosted
under the SIL Open Font License (`static/fonts/OFL.txt`).
