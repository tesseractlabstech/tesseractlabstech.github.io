# tesseractlabstech.github.io

GitHub Pages hosting repo for the Tesseract Labs marketing site at
**[tesseractlabs.tech](https://tesseractlabs.tech)**.

This repo holds **build output only** — there is no source code, no `package.json`, and no
build step here. The site is built in the sibling repo
[`tesseractlabstech/tesseractlabstech-website`](https://github.com/tesseractlabstech/tesseractlabstech-website)
and the resulting bundle is committed here to be served.

## Contents

| Path | Purpose |
| --- | --- |
| `index.html` | SPA entry point; references the hashed JS/CSS bundles in `assets/` |
| `assets/` | Generated bundles (`index.<hash>.js`, `index.<hash>.css`), favicon, logos, and imagery |
| `privacy.html` | Standalone privacy policy page, exported from Microsoft Word (outside the SPA) |
| `CNAME` | Custom domain for GitHub Pages: `tesseractlabs.tech` |
| `_redirects` | Netlify/Cloudflare-style SPA rewrite rule (`/* /index.html 200`) — **not honoured by GitHub Pages**; see below |

## The site

A React single-page app with client-side routes `/` and `/about`, plus a catch-all not-found
view. Content positions Tesseract Labs as a partner across "the trio - data, web3 and
security", with six service cards:

- Modern Data Design
- Analytics Engineering
- Zero-Knowledge Application (circom, halo2)
- DApp Development (full stack, web UI to smart contract, EVM-based blockchains)
- Access Management
- Identity and Authentication

Contact address shown on the site: `info@tesseractlabs.tech`.

### Known issue: `/about` 404s on direct load

`_redirects` is a Netlify/Cloudflare Pages file. GitHub Pages ignores it, and there is no
`404.html` fallback in this repo, so only `/` resolves on a direct request —
`https://tesseractlabs.tech/about` returns HTTP 404. The route works only via in-app
navigation from `/`. Fixing it means adding a `404.html` that serves the SPA shell (the
standard GitHub Pages workaround), which belongs in the source repo's build.

## Making changes

Change the site in the **source** repo, rebuild there, and commit the refreshed bundle here.
Do not hand-edit files in `assets/` — they are generated and content-hashed, so edits are
overwritten by the next build and the hashed filenames will not match.

`privacy.html` and `CNAME` are maintained directly in this repo and are not produced by the
build.

## Deployment

GitHub Pages serves the default branch at the domain in `CNAME`. Pushing the built bundle to
that branch is the deploy.
