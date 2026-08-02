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

Until that DNS change happens, `eatmediatv.com` keeps serving whatever it
currently points at — pushing here is safe and has zero effect on the live
domain by itself.

## Origin

This content is developed and kept in sync from
[`dixon8303/ImaginariumOzone`](https://github.com/dixon8303/ImaginariumOzone)'s
`eatmedia/` folder, which has the full edit history, design notes, and
open items — see that repo's `eatmedia/README.md` for details on what's
been built, what's still open (real photo captions, a working contact
form, real testimonials), and why specific decisions were made.
