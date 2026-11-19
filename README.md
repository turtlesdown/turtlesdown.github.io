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

Push to `main`. `.github/workflows/deploy.yml` builds the site and deploys it
to GitHub Pages in about a minute. Drafts are not published. Build output is
not committed; `public/` is gitignored.

One-time repository setup:

- **Settings → Pages → Build and deployment → Source**: GitHub Actions.
- **Settings → Pages → Custom domain**: `turtlesdown.dev`, with **Enforce
  HTTPS** on. `static/CNAME` holds the same domain.
- DNS for `turtlesdown.dev`: the four GitHub Pages A records (plus AAAA for
  IPv6), and a `www` CNAME pointing to `turtlesdown.github.io`.

## Upgrading dependencies

Every build dependency is pinned in `.github/workflows/deploy.yml`:

- **Hugo**: bump `HUGO_VERSION` and replace `HUGO_SHA256` with the line for
  `hugo_<version>_linux-amd64.tar.gz` from that release's `checksums.txt`.
  Update the version below as well.
- **GitHub Actions**: each `uses:` names a full commit SHA, with its release
  tag in a comment. To upgrade, replace both:
  `gh api repos/actions/checkout/commits/<tag> -q .sha`.
- **Runner image**: `ubuntu-24.04`.

There are no other build dependencies (no theme, Hugo modules, npm, or
external scripts). The fonts are vendored in `static/fonts/`.

## Where things live

| Path                   | What it is                                     |
| ---------------------- | ---------------------------------------------- |
| `hugo.toml`            | Title, tagline, links, navigation              |
| `content/posts/`       | Posts                                          |
| `content/about.md`     | About page                                     |
| `layouts/`             | Templates (no theme; everything is in here)    |
| `assets/css/main.css`  | The whole stylesheet; colors are at the top    |
| `static/img/`          | Masthead drawing and social card               |
| `layouts/robots.txt`   | Crawler rules (template; adds sitemap URL)     |

Built and tested with Hugo 0.170.1; the standard edition is enough, since the
site uses no Sass or image processing. CI pins that version and its checksum.
The typeface is Newsreader, self-hosted under the SIL Open Font License
(`static/fonts/OFL.txt`).
