# loop-marketing-coach

Coaches you through HubSpot's Loop Marketing (Express, Tailor, Amplify, Evolve) using your Markdown marketing files. It explains the stages with your own brand as the example, finds where a campaign is stuck, drafts or reviews posts against your Taste Profile, and runs check-ins with real numbers. Each answer ends with one next step.

## Install

```sh
npx skills add https://github.com/kreddevils18/marketing-skills --skill loop-marketing-coach
```

Or paste this prompt into any agent. It loads the skill for the task without installing it:

```text
Run `npx skills use "https://github.com/kreddevils18/marketing-skills" --skill "loop-marketing-coach"` and follow the generated skill instructions now. Read its complete output, redirecting it to a temporary file first if necessary. Resolve relative paths from the supporting-files directory it provides.
```

Manual install for Claude Code:

```sh
git clone https://github.com/kreddevils18/marketing-skills
cp -R marketing-skills/skills/content/loop-marketing-coach ~/.claude/skills/
```

## Use

The skill loads when you ask about Loop Marketing, what to do next with a campaign, to write or review a campaign post, or how a campaign is doing. You can also call it by name: `/loop-marketing-coach` in Claude Code, `$loop-marketing-coach` in Codex.

| You say | What the agent does |
| --- | --- |
| "What is Loop Marketing and where do I start?" | Explains the four stages and picks the one with the biggest gap in your files |
| "Write today's post for the launch campaign" | Drafts in your voice from the brief's message, offer and hooks, for you to approve |
| "How is the campaign doing?" | Pulls numbers from your analytics tools, compares them with the target pace and proposes a log entry |

## What it covers

- Explain, diagnose, draft, review and check-in modes.
- A review checklist built from your shared rules, Taste Profile and campaign brief.
- Check-in decision rules: keep, change, revisit the offer, or close the campaign.

It never publishes or schedules anything, and only writes to your files after you approve.

## Security audit

Passed 7 of 7 checks on 2026-11-15 (`ak:skill-creator` audit): no scripts, no secrets, no data sent anywhere, no dependencies. See [`audits/loop-marketing-coach.json`](../../../audits/loop-marketing-coach.json).
