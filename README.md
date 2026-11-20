# tesseractlabstech.github.io

Published static site for [tesseractlabs.tech](https://tesseractlabs.tech), served by GitHub Pages.

This repository holds **built output only**. The source code is in
[`tesseractlabstech-website`](https://github.com/tesseractlabstech/tesseractlabstech-website),
a Vite/React app. Don't edit files under `assets/` or `index.html` by hand. Change the
source repository, rebuild, and publish the output here.

## Contents

| Path           | Purpose                                                                  |
| -------------- | ------------------------------------------------------------------------ |
| `index.html`   | Entry point of the built single-page app                                 |
| `assets/`      | Hashed JS, CSS and image bundles produced by the build                   |
| `privacy.html` | Standalone privacy statement (not part of the React build)               |
| `CNAME`        | Custom domain for GitHub Pages (`tesseractlabs.tech`)                    |
| `_redirects`   | SPA fallback rule (`/* /index.html 200`) for hosts that support it       |

## Publishing

1. Make and test changes in `tesseractlabstech-website`.
2. Build it there with its build script.
3. Replace `index.html` and `assets/` here with the new build output. Keep `CNAME`,
   `_redirects` and `privacy.html`.
4. Commit and push to the default branch. GitHub Pages serves the new version.
