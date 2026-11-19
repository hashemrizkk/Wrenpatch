# Wrenpatch

Wrenpatch finds the security advisories (CVEs) that actually reach your code and opens the fix as a pull request, with your tests already run.

Most dependency scanners flag every vulnerable package in a lockfile, whether or not your code ever calls the affected function. Wrenpatch traces the call path first, so teams patch what matters and skip the noise.

![Wrenpatch landing page](share.jpg)

## Status

Early development. This repository holds the marketing site; the product itself is in progress.

## How it works

1. **Reads lockfiles.** New advisories from the GitHub Advisory Database and OSV are matched against the exact versions each repository installs.
2. **Traces the call path.** Imports are followed from your entry points to the vulnerable function. Advisories your code never reaches are listed, not patched.
3. **Opens a tested pull request.** The version bump goes on its own branch, the test suite runs, and the pull request names the advisory and the call site.

Planned integrations: GitHub, GitLab, Slack and Jira, with npm, PyPI, Go and Maven lockfiles.

## Running the site locally

Requires [Node.js](https://nodejs.org/) 18 or newer.

```bash
npm install
npm start
```

The site is served at http://localhost:3000. It is static HTML, CSS and JavaScript with no build step. Opening `index.html` straight from disk won't work, because browsers block the page's JavaScript modules on `file://`.

## Project structure

```
index.html          landing page
privacy.html        privacy policy (draft)
terms.html          terms of service (draft)
assets/             styles, scripts, UI components, icons and fonts
assets/fonts/       Sreda, the headline font
favicon.svg         site icon
share.jpg           preview image for shared links
package.json        npm start script
```

## Roadmap for the site

- [ ] Connect "Start free" to the sign-up flow (it currently opens an email)
- [ ] Confirm the response-time figure in the hero
- [ ] Final privacy policy and terms
- [ ] Pricing section
- [ ] Canonical URL and domain
- [ ] Confirm the license for the Sreda font

## Credits

- Headline font: **Sreda** by Glenjan (Elena Kowalski). The font file states "Copyright (c) 2011-2012 by Glenjan. All rights reserved."; commercial use is being confirmed with the author.
- Body and code fonts: Instrument Sans and JetBrains Mono, via Google Fonts.
- Integration logos: SVG Logos and Simple Icons. Product names and logos are trademarks of their owners.
- CVE identifiers and fixed versions shown on the site are real, public advisories.

## License

The code in this repository is released under the [MIT License](LICENSE). The Sreda font is not covered by it.
