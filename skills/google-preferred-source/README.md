# google-preferred-source

Adds a "Prefer us on Google" button to your website so readers can pick it as a preferred source in Google Search, which gives your site more presence in their Top Stories and a "preferred" label in AI Mode and AI Overviews. The button is a plain deeplink to Google's source preferences tool, rendered by your site's own component: no Google script, nothing loaded from Google until a reader clicks.

## Install

```sh
npx skills add https://github.com/kreddevils18/skills --skill google-preferred-source
```

Or paste this prompt into any agent. It loads the skill for the task without installing it:

```text
Run `npx skills use "https://github.com/kreddevils18/skills" --skill "google-preferred-source"` and follow the generated skill instructions now. Read its complete output, redirecting it to a temporary file first if necessary. Resolve relative paths from the supporting-files directory it provides.
```

Manual install for Claude Code:

```sh
git clone https://github.com/kreddevils18/skills
cp -R skills/skills/google-preferred-source ~/.claude/skills/
```

## Use

The skill loads when you ask for a Google preferred source button or badge, an "add us on Google" link, or more presence in Top Stories and AI Overviews. You can also call it by name: `/google-preferred-source` in Claude Code, `$google-preferred-source` in Codex.

| You say | What the agent does |
| --- | --- |
| "Add a Google preferred source button" | Finds your canonical host, defines the deeplink once, builds one server-rendered button with default and compact variants in your design system, places it at the end of articles and in the footer, adds a test |
| "Why not Google's publisher.js button?" | Explains the trade-off: third-party script, request on page load, fixed theme, harder to test |
| "Is my site eligible?" | Checks that it is a domain or subdomain, not a subpath, and lists the Search Console setting needed for AI Mode and AI Overviews |

## What it covers

- What preferred sources does and who is eligible, from Google's Search Central docs.
- The deeplink `https://www.google.com/preferences/source?q=<host>` as an accessible `<a target="_blank" rel="noopener">` in your own component: light and dark, 44px tap target, no horizontal scroll at 375px.
- A plain HTML example, a Next.js/React server component and a focused test.
- A check that the page makes no request to Google on load, plus the manual checks only the site owner can do.

Not covered: Google's `publisher.js` button, Google News publisher setup, ranking work.

## Security audit

Passed 7 of 7 checks on 2026-11-17 (`ak:skill-creator` audit): no scripts, no secrets, no network calls, no dependencies. See [`audits/google-preferred-source.json`](../../audits/google-preferred-source.json).
