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
| `_redirects` | SPA rewrite rule (`/* /index.html 200`) so client-side routes resolve on refresh |

## The site

A React single-page app with client-side routes `/` and `/about`, plus a not-found view.
Content positions Tesseract Labs as a partner across "the trio — data, web3 and security",
organised into three pillars:

- **Data** — Modern Data Design and Analytics Engineering
- **Web3** — Zero-Knowledge Applications (circom, halo2) and DApp development for EVM chains
- **Security** — Access Management, plus Identity and Authentication

Contact address shown on the site: `info@tesseractlabs.tech`.

## Making changes

Change the site in the **source** repo, rebuild there, and commit the refreshed bundle here.
Do not hand-edit files in `assets/` — they are generated and content-hashed, so edits are
overwritten by the next build and the hashed filenames will not match.

`privacy.html` and `CNAME` are maintained directly in this repo and are not produced by the
build.

## Deployment

GitHub Pages serves the default branch at the domain in `CNAME`. Pushing the built bundle to
that branch is the deploy.
