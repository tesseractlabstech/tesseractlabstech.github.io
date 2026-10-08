# CLAUDE.md

Orientation notes for agent sessions in this repo. See `README.md` for the full summary.

## What this repo is

A GitHub Pages **deployment target**, not a source tree. It serves
[tesseractlabs.tech](https://tesseractlabs.tech) from committed build output.

## Commands

There are none. No `package.json`, so no `npm test`, `npm run lint`, or `npm run build` exists
here — do not report those as skipped or passing.

## Constraints

- **Never hand-edit `assets/`.** Those files are generated and content-hashed; edits get
  overwritten by the next build and the hashes stop matching `index.html`.
- **`index.html` is generated too.** Its asset `href`/`src` hashes come from the build.
- Site content and layout changes belong in the source repo
  [`tesseractlabstech/tesseractlabstech-website`](https://github.com/tesseractlabstech/tesseractlabstech-website),
  then the rebuilt bundle is committed here.

## Files maintained by hand

- `privacy.html` — Word-exported privacy policy, served outside the SPA. Large and
  machine-generated markup; edit narrowly.
- `CNAME` — custom domain. Removing it breaks the domain mapping.
- `_redirects` — `/* /index.html 200`. This is a Netlify/Cloudflare Pages convention and is
  **ineffective on GitHub Pages**. With no `404.html` fallback, `/about` returns HTTP 404 on a
  direct load or refresh (verified against the live site); it only works via in-app
  navigation. Do not describe this file as working SPA routing.
