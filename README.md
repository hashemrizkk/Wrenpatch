# Wrenpatch

A landing page for Wrenpatch, a project I'm working on: a tool idea that finds the security advisories (CVEs) that actually reach your code and opens the fix as a pull request.

![Wrenpatch landing page](share.jpg)

## The idea

Dependency scanners usually flag every vulnerable package in a lockfile, even when your code never calls the affected function. Wrenpatch would trace the call path first and only patch what your code reaches:

1. Read the lockfiles and match new advisories (GitHub Advisory Database, OSV) against the installed versions.
2. Follow the imports to see whether the vulnerable function is ever called.
3. Open a pull request with the version bump and run the tests on it.

Right now the repo is just the landing page. The tool itself doesn't exist yet.

## What's on the page

- Hero with a mock app window: a list of advisories next to a `package.json` patch
- A workflow section that walks through the three steps as you scroll
- Feature cards (Slack alerts, merge rules)
- FAQ
- An integrations diagram (GitHub, GitLab, npm, PyPI, Slack, Jira)

Plain HTML, CSS and JavaScript, no framework and no build step.

## Run it

Needs [Node.js](https://nodejs.org/) 18+.

```bash
npm install
npm start
```

Then open http://localhost:3000.

Opening `index.html` directly from disk won't work, because browsers block JavaScript modules on `file://`.

## Files

```
index.html          the page
privacy.html        privacy page (draft)
terms.html          terms page (draft)
assets/             styles, scripts, UI pieces, icons, fonts
assets/fonts/       Sreda, the headline font
favicon.svg         site icon
share.jpg           screenshot / link preview
package.json        npm start script
```

## To do

- [ ] Hook "Start free" up to something real (it opens an email for now)
- [ ] Double-check the "15 minutes" line in the hero
- [ ] Write proper privacy and terms pages
- [ ] Maybe a pricing section
- [ ] Check the Sreda font license before putting this online

## Credits

- Headline font: **Sreda** by Glenjan (Elena Kowalski). The font file says "Copyright (c) 2011-2012 by Glenjan. All rights reserved.", and download sites disagree on whether it's free for commercial use.
- Body and code fonts: Instrument Sans and JetBrains Mono, from Google Fonts.
- Integration logos: SVG Logos and Simple Icons. Product names and logos belong to their owners.
- The CVE numbers and versions in the mock-up are real, public advisories.

## License

My code is [MIT](LICENSE). The Sreda font isn't covered by that license.
