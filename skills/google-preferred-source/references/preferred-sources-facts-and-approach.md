# Preferred sources: facts and approach

Source: Google Search Central, "Preferred sources",
https://developers.google.com/search/docs/appearance/preferred-sources
(checked 2026-11-17). Re-read it if anything below looks out of date.

## Facts

- Readers pick sources in the source preferences tool:
  `https://www.google.com/preferences/source`. The tool has a search box; owners
  check that their site is listed by searching for it there.
- Effect for a reader who picked the site:
  - Top Stories: the site is more likely to appear, with a "preferred" label.
  - AI Mode and AI Overviews: the site can be highlighted with a "preferred"
    label.
- Eligibility: domain-level and subdomain-level sites only, such as
  `https://www.example.com/` or `https://code.example.com/`. Subdirectories such
  as `https://www.example.com/blog` do not qualify.
- For AI Mode and AI Overviews, the site must be included in Search generative AI
  features in Search Console.
- Google offers three ways to promote it; none is required to be chosen as a
  preferred source:
  1. A JavaScript button: `publisher.js` from `news.google.com` plus a
     `google-add-preferred-source-btn` element, with `data-theme` and
     `data-lang`. Google labels this the recommended option. It translates the
     label and returns the reader to the page after adding the site.
  2. Advanced JavaScript (`publisher.mjs` or a manual callback queue) to bind the
     flow to custom triggers.
  3. A deeplink for when JavaScript is not possible:
     `https://www.google.com/preferences/source?q=example.com`. It also works in
     newsletters and social posts.
- Official translated badge graphics (optional) are a ZIP:
  `https://services.google.com/fh/files/helpcenter/google_preferred_source_badge_all_languages.zip`.

## Why this skill uses the deeplink

| Concern | `publisher.js` | Deeplink in the site's component |
| --- | --- | --- |
| Third-party code | Loads and runs Google script on every page with the button | None |
| Privacy | Request to Google on page load, before any click | Google sees the reader only after they click |
| Performance | Extra script and render work | A plain link |
| Theme | `data-theme` is fixed at render; does not follow a live light/dark toggle | Uses the site's tokens, follows its theme |
| Design | Google-styled button | Matches the site's buttons |
| Testability | Rendered by external script; needs network or mocks | Static markup; one unit test covers it |
| Works without JS | No | Yes, including server-rendered and static pages |

What the deeplink gives up: Google's automatic label translation and the return
to the page after the reader adds the site. Translate the label with the site's
own i18n if it has one. The new tab keeps the article open, which covers the
return.

## Host rules

- Use the canonical host the site already declares (metadata base URL, sitemap,
  canonical tags), without scheme, path or trailing slash.
- Pick the variant readers will recognise and that Google lists: usually the bare
  domain; use `www.` or a subdomain only if that is the canonical host.
- URL-encode the value (`encodeURIComponent`) even though plain hosts need no
  escaping, so a later change cannot break the query string.
- A site that is only a subpath of a larger domain is not eligible. Tell the user
  instead of adding a button.
