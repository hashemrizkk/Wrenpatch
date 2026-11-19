# Wrenpatch landing page

A one-page landing site for **Wrenpatch**, a fictional developer tool that tracks security advisories (CVEs) in a team's dependencies, checks whether the vulnerable code is actually called, and opens the fix as a tested pull request.

The design is dark and minimal: a warm near-black background, off-white text, headlines in the Sreda display face, mono type for code, square buttons, thin dividing lines, and white for every button, link and focus outline.

![Hero of the Wrenpatch landing page](share.jpg)

## Sections

1. **Hero:** headline, short description, "Start free" and "See the workflow" buttons, and an app window showing a list of advisories beside a `package.json` patch.
2. **Workflow:** three steps (read lockfiles, trace the call path, open a tested pull request) that hold on screen while you scroll.
3. **Features:** Slack alerts to the owning team, and per-repository merge rules.
4. **Questions:** a short FAQ.
5. **Integrations:** a diagram with GitHub, GitLab, npm, PyPI, Slack and Jira.
6. **Footer:** a closing call to action and links.

## Run it locally

The site is plain HTML, CSS and JavaScript with no build step. It needs [Node.js](https://nodejs.org/) 18 or newer.

```bash
npm install
npm start
```

`npm start` serves the site with [serve](https://www.npmjs.com/package/serve) on port 3000 and prints the address to open. Opening `index.html` directly from disk will not work, because browsers block the page's JavaScript modules on `file://`.

## Files

| Path | What it is |
| --- | --- |
| `index.html` | The landing page |
| `package.json` | The `npm start` script and its one dev dependency |
| `privacy.html`, `terms.html` | Short placeholder legal pages |
| `assets/` | Design system: styles, scripts, UI fragments, motion, diagrams and icons |
| `assets/fonts/Sreda.otf` | The headline font |
| `favicon.svg` | Site icon |
| `share.jpg` | Preview image for shared links |
| `names.json` | Record of the search that checked the name "Wrenpatch" was free |

## Before going live

- The "Start free" buttons open an email to `hello@wrenpatch.example`. Replace them with the real sign-up link.
- "Within 15 minutes of disclosure" in the hero is a placeholder claim; confirm or change it.
- `privacy.html` and `terms.html` are stand-ins.
- Add the canonical link in `<head>` once the domain is known.
- There is no pricing section yet.
- Confirm the Sreda font license (see Fonts and icons).

The CVE numbers and fixed versions in the app mock-up are real, public advisories.

## Fonts and icons

Headlines use **Sreda** by Glenjan (Elena Kowalski), served from `assets/fonts/Sreda.otf`. Its file says "Copyright (c) 2011-2012 by Glenjan. All rights reserved." and download sites disagree on whether commercial use is free, so confirm the license with Glenjan before going live. Body text (Instrument Sans) and code (JetBrains Mono) load from Google Fonts. Product logos come from SVG Logos and Simple Icons; product names and logos are trademarks of their owners.

## License

[MIT](LICENSE)
