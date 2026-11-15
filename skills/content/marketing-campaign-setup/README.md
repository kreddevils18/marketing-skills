# marketing-campaign-setup

Plans one marketing campaign as a Markdown brief: one goal, one target number, one audience slice, one message, one offer and a start date, with a name and UTM that follow a convention. The brief has a section for each Loop Marketing stage, including a concept test where the agent role-plays your audience before you write anything.

## Install

```sh
npx skills add https://github.com/kreddevils18/marketing-skills --skill marketing-campaign-setup
```

Or paste this prompt into any agent. It loads the skill for the task without installing it:

```text
Run `npx skills use "https://github.com/kreddevils18/marketing-skills" --skill "marketing-campaign-setup"` and follow the generated skill instructions now. Read its complete output, redirecting it to a temporary file first if necessary. Resolve relative paths from the supporting-files directory it provides.
```

Manual install for Claude Code:

```sh
git clone https://github.com/kreddevils18/marketing-skills
cp -R marketing-skills/skills/content/marketing-campaign-setup ~/.claude/skills/
```

## Use

The skill loads when you ask to start, plan or brief a campaign, a launch, a content series or a promotion. You can also call it by name: `/marketing-campaign-setup` in Claude Code, `$marketing-campaign-setup` in Codex.

| You say | What the agent does |
| --- | --- |
| "Plan a 6-week build-in-public series on X" | Asks for goal, target, audience, message, offer and dates one at a time, then writes the brief |
| "Plan the Product Hunt launch for v2" | Sets a signup target with a baseline, names the campaign and tags every link with its UTM |
| "I want followers and sales from this" | Proposes two campaigns, because one campaign gets one goal |

## What it writes

`marketing/campaigns/<utm>.md`, for example `marketing/campaigns/202611_jane_x_aware_solo-build-with-ai.md`. It reads the brand's Taste Profile from [marketing-project-setup](../marketing-project-setup) first.

## Security audit

Passed 7 of 7 checks on 2026-11-15 (`ak:skill-creator` audit): no scripts, no secrets, no network calls, no dependencies. See [`audits/marketing-campaign-setup.json`](../../../audits/marketing-campaign-setup.json).
