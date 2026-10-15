# eat.media

Live source for **eatmediatv.com** — the official site for Everything, All
That Media LLC (E.A.T. Media), a Los Angeles video production and
photography studio.

Pure static site: `index.html`, `about.html`, `photoshoot-packages.html`,
shared `assets/style.css` / `assets/site.js`. No build step, no framework,
no backend.

## Deploy

[`.github/workflows/pages.yml`](.github/workflows/pages.yml) deploys this
repo's root to GitHub Pages on every push to `main`, and enables Pages
automatically on first run. `CNAME` (`eatmediatv.com`) tells Pages which
custom domain to serve.

## DNS

For `eatmediatv.com` to actually resolve here, the domain's DNS (managed at
the registrar — GoDaddy) needs:

| Type | Host | Value |
|------|------|-------|
| A | `@` | `185.199.108.153` |
| A | `@` | `185.199.109.153` |
| A | `@` | `185.199.110.153` |
| A | `@` | `185.199.111.153` |
| CNAME | `www` | `dixon8303.github.io` |

Then, once DNS propagates, enable **Settings → Pages → Enforce HTTPS** in
this repo (the certificate can take up to 24h to issue the first time).

**That DNS change is done** (verified Oct 13, 2026: the four A records and
the `www` CNAME above resolve). Every push to `main` now goes live on
`eatmediatv.com` within a minute or two, so changes come in as pull
requests.

## Short links for What History Buried (Addendum A02, Oct 13, 2026)

Say-able URLs on the domain D already owns, so Shorts end cards and the ABE
podcast can name a link without buying a new domain. Each is a folder with
one `index.html` that forwards to the book site with tracking tags. Nothing
on the site links to them, and they carry `noindex`.

| Short link | Forwards to | Tags (all add `utm_campaign=whb_campaign`) |
|---|---|---|
| eatmediatv.com/book | the book site's home | `utm_source=eatmediatv`, `utm_medium=short_link`, `utm_content=book` |
| eatmediatv.com/abe | the book site's home | `utm_source=abe_podcast`, `utm_medium=audio`, `utm_content=abe` |
| eatmediatv.com/quiz | `erasure.html`, the 3-question test | `utm_source=eatmediatv`, `utm_medium=short_link`, `utm_content=quiz` |
| eatmediatv.com/challenge | `unlearn.html`, the 5-Day Unlearning Challenge | `utm_source=eatmediatv`, `utm_medium=short_link`, `utm_content=challenge` |

The book site lives at https://dixon8303.github.io/ImaginariumOzone/book/. A
visitor who arrives with their own `utm_` tags keeps them; any other query
string and the `#anchor` pass through; without JavaScript, a meta refresh
forwards with the default tags.

To add a slug (`/gift`, `/class`, `/talk` and `/founding` arrive with their
pages), copy `book/index.html` to `<slug>/index.html` and change the target URL
and the tag string everywhere they appear: the canonical link, the two script
variables, the meta refresh and the visible link. Keep the staging copy in
ImaginariumOzone's `eatmedia/` in step. If the book site moves, or
`erasure.html` or `unlearn.html` is renamed, update these targets the same day:
the URLs are already spoken in Shorts and on the podcast.

## Origin

This content is developed and kept in sync from
[`dixon8303/ImaginariumOzone`](https://github.com/dixon8303/ImaginariumOzone)'s
`eatmedia/` folder, which has the full edit history, design notes, and
open items — see that repo's `eatmedia/README.md` for details on what's
been built, what's still open (real photo captions, a working contact
form, real testimonials), and why specific decisions were made.
