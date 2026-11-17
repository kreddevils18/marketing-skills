---
name: google-preferred-source
description: Add a Google "Preferred source" button to a website with a plain no-JavaScript deeplink rendered by the site's own component, so readers can pick the site as a preferred source in Google Search (Top Stories, AI Mode, AI Overviews). Use when the user asks for a Google preferred source button or badge, "add us on Google", or wants more presence for their site in Top Stories or AI Overviews. Not for Google's publisher.js button, Google News publisher setup, or ranking work.
---

# Google Preferred Source

Add a "Prefer us on Google" button that links readers to Google's source
preferences tool for the site's host. The button is a plain link rendered by the
site's own component: no Google script, no request to Google on page load.

## What it does

- Readers choose sources at `https://www.google.com/preferences/source`. A chosen
  site is more likely to appear in their Top Stories and can be highlighted with
  a "preferred" label in AI Mode and AI Overviews.
- Eligible: a domain or subdomain (`example.com`, `news.example.com`). A subpath
  (`example.com/blog`) is not.
- AI Mode and AI Overviews also need the site to be included in "Search
  generative AI features" in Search Console. That is the owner's setting.

Details, sources and the approach comparison: `references/preferred-sources-facts-and-approach.md`.

## Approach

Link to `https://www.google.com/preferences/source?q=<host>` as
`<a href target="_blank" rel="noopener">` from the site's own button component.
Do not load `publisher.js`, even though Google calls it the recommended option:
it is a third-party script with a privacy and performance cost, it does not
follow the site's theme toggle, and it is harder to test. If the user insists
on it, say this trade-off once and then follow Google's docs.

## Workflow

1. **Find the canonical host.** Look for an existing site URL constant or env
   var (metadata base URL, sitemap config, `SITE_URL`). Use its host only, with
   no scheme or path (`example.com`, or `www.example.com` if that is canonical).
   If the site lives on a subpath, or no host is found, stop and ask the user.
2. **Define the URL once**, next to that constant:
   `https://www.google.com/preferences/source?q=` plus the URL-encoded host.
3. **Build one component** in the site's framework, rendered on the server:
   - variants: `default` (icon + label + short line) and `compact` (icon + label);
   - an `<a>` with `href`, `target="_blank"`, `rel="noopener"`;
   - accessible name ending in "(opens in a new tab)" (visually hidden text or
     `aria-label`), decorative icon marked `aria-hidden`;
   - the site's own design tokens and button styles, correct in light and dark,
     a visible focus ring, at least a 44px tap target, no horizontal scroll at
     375px width.
   Reuse the site's existing button or link primitive when it has one.
4. **Place it** where readers have just finished reading: end of articles or
   posts, and the footer (compact). Ask before adding it anywhere more prominent.
5. **Test it.** One focused test: `href` equals the expected URL, `target` is
   `_blank`, `rel` contains `noopener`, accessible name contains the label and
   "(opens in a new tab)". Use the repo's test runner and conventions.
6. **Verify** (below), then hand the manual checks to the user.

Generic HTML and a Next.js/React example: `references/component-examples.md`.
Keep copy short and in the site's voice, for example "Prefer us on Google" or
"Add us as a preferred source on Google". Use Google's official badge graphics
only if the user wants them (ZIP link in the facts reference).

## Verify

- Run the test and the repo's lint/type checks.
- Load a page with the button and confirm in the browser network panel, or with
  the server HTML, that nothing is requested from `google.com` or
  `news.google.com` until the button is clicked:

  ```bash
  curl -s https://example.com/some-article | grep -o 'google.com/preferences/source[^"]*'
  curl -s https://example.com/some-article | grep -c 'publisher\.js'   # expect 0
  ```

- Check the button at 375px width and in both themes; tab to it and see the
  focus ring.

## Manual checks for the site owner

Report these as pending; the agent cannot confirm them:

1. Open `https://www.google.com/preferences/source`, search for the domain and
   confirm it is listed. If it is not, the button still works but leads to an
   empty result.
2. In Search Console, confirm the site is included in Search generative AI
   features, if the owner wants the preferred label in AI Mode and AI Overviews.
