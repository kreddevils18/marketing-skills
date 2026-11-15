# marketing-project-setup

Sets up the marketing foundation for each of your brands as Markdown files: shared writing rules, plus a Taste Profile per brand with guidelines, voice, business goals, audience, beliefs backed by proof, and a voice bank. It is the Express stage of HubSpot's Loop Marketing, so AI writes like your brand instead of like every other AI.

## Install

```sh
npx skills add https://github.com/kreddevils18/marketing-skills --skill marketing-project-setup
```

Or paste this prompt into any agent. It loads the skill for the task without installing it:

```text
Run `npx skills use "https://github.com/kreddevils18/marketing-skills" --skill "marketing-project-setup"` and follow the generated skill instructions now. Read its complete output, redirecting it to a temporary file first if necessary. Resolve relative paths from the supporting-files directory it provides.
```

Manual install for Claude Code:

```sh
git clone https://github.com/kreddevils18/marketing-skills
cp -R marketing-skills/skills/content/marketing-project-setup ~/.claude/skills/
```

## Use

The skill loads when you ask to define a brand voice, write a taste profile or style guide for AI, add a brand, or review a profile. You can also call it by name: `/marketing-project-setup` in Claude Code, `$marketing-project-setup` in Codex.

| You say | What the agent does |
| --- | --- |
| "Set up marketing for my app" | Reads your README and landing page, then interviews you one question at a time with suggested answers |
| "Add my second app as a brand" | Creates a new profile next to the existing ones, reusing the shared rules |
| "Review my taste profile" | Checks each section against what changed this quarter and proposes edits |

## What it writes

```
marketing/
  shared-rules.md             rules every brand follows
  taste-profiles/<brand>.md   one file per brand
  campaigns/                  filled by marketing-campaign-setup
```

Works with [marketing-campaign-setup](../marketing-campaign-setup) and [loop-marketing-coach](../loop-marketing-coach), which read the same files.

## Security audit

Passed 7 of 7 checks on 2026-11-15 (`ak:skill-creator` audit): no scripts, no secrets, no network calls, no dependencies. See [`audits/marketing-project-setup.json`](../../../audits/marketing-project-setup.json).
