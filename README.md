# tesseractlabstech.github.io

Production build of the Tesseract Labs company website, served via GitHub Pages at **https://tesseractlabs.tech**.

This repository contains **compiled static output only** (a Vite + React + Tailwind single-page app). There is no source code, package manifest or build tooling here — content changes are made in the source project, rebuilt, and the generated files are committed to this repository.

## What the site covers

Tesseract Labs — *"Your ultimate partner of the trio - data, web3 and security"*. The site presents three service pillars:

| Pillar | Services |
| --- | --- |
| Data | Modern cloud data stack migration; data preparation and modelling for analytics |
| Web3 | Zero-knowledge application development (circom, halo2); full-stack dApps for EVM-based blockchains |
| Security | Identity and access governance (access request, provisioning, review); identity and authentication solutions |

Pages:

- `/` — home (hero, pillars, contact)
- `/about` — about the company and team
- `/privacy.html` — privacy statement (standalone static page)
- `*` — not-found page

Contact: info@tesseractlabs.tech

## Repository layout

| Path | Purpose |
| --- | --- |
| `index.html` | SPA entry point; loads the hashed JS and CSS bundles from `assets/` |
| `assets/` | Build output: hashed JS/CSS bundles, images, logos and favicon |
| `privacy.html` | Self-contained privacy statement page |
| `CNAME` | Custom domain for GitHub Pages (`tesseractlabs.tech`) |
| `_redirects` | SPA fallback rule rewriting all paths to `index.html` (for hosts that honour `_redirects`) |

## Deploying

1. Build the site in the source project.
2. Replace `index.html` and `assets/` with the new build output. Remove stale hashed bundles so only the files referenced by `index.html` remain.
3. Keep `CNAME`, `_redirects` and `privacy.html` unless they are intentionally changed.
4. Commit and push to `main`; GitHub Pages publishes the update.

## Previewing locally

Serve the repository root with any static file server, for example:

```bash
npx serve .
```

Then open the printed URL. Asset paths are absolute (`/assets/...`), so the site must be served from the root rather than opened directly as a file.
