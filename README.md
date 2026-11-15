# marketing-skills

Marketing agent skills by [Kien Hoang](https://kien-hoang.vercel.app/skills): brand voice, campaigns, content and app store growth for solo builders. Each skill is a folder with a `SKILL.md`, the open skill format, so it works in Claude Code, Codex, Cursor, OpenCode and any other agent that reads skills.

Browse them with install commands and the full instructions at [kien-hoang.vercel.app/skills](https://kien-hoang.vercel.app/skills).

## Skills

### Content

Three skills that share one folder of Markdown files (`marketing/`) and follow HubSpot's Loop Marketing: Express, Tailor, Amplify, Evolve.

| Skill | What it does |
| --- | --- |
| [marketing-project-setup](skills/content/marketing-project-setup) | Interviews you to write shared rules and a Taste Profile per brand: voice, audience, beliefs with proof, voice bank. |
| [marketing-campaign-setup](skills/content/marketing-campaign-setup) | Plans one campaign as a brief: one goal, target, message and offer, a naming and UTM convention, and a concept test. |
| [loop-marketing-coach](skills/content/loop-marketing-coach) | Explains the loop, finds where a campaign is stuck, drafts and reviews posts in your voice, runs check-ins with real numbers. |

### ASO

| Skill | What it does |
| --- | --- |
| [smart-app-banner](skills/aso/smart-app-banner) | Adds, fixes or checks Apple's Smart App Banner (`apple-itunes-app` meta tag) so a website promotes its iOS app in Safari. |

## Install

With the [skills CLI](https://github.com/vercel-labs/skills), install one skill:

```sh
npx skills add https://github.com/kreddevils18/marketing-skills --skill marketing-project-setup
```

Or every skill in this repository:

```sh
npx skills add https://github.com/kreddevils18/marketing-skills
```

The CLI asks which agents to install for. To skip the questions, name the agents and install for every project (`-g`):

```sh
npx skills add https://github.com/kreddevils18/marketing-skills --skill marketing-project-setup -g -a claude-code -a codex
```

List the skills without installing anything:

```sh
npx skills add https://github.com/kreddevils18/marketing-skills --list
```

### Copy it yourself

```sh
git clone https://github.com/kreddevils18/marketing-skills
cp -R marketing-skills/skills/<group>/<skill> ~/.claude/skills/
```

| Agent | Every project | One repository |
| --- | --- | --- |
| Claude Code | `~/.claude/skills/<skill>` | `.claude/skills/<skill>` |
| Codex | `~/.agents/skills/<skill>` | `.agents/skills/<skill>` |
| Other agents | the agent's skills folder | the agent's project skills folder |

Keep one copy per agent, or the agent sees the skill twice. Restart the agent after installing.

## Security audits

Every skill is audited before it is published, with the `audit` mode of the `ak:skill-creator` skill: structure and frontmatter validation, prompt lint, and a manual review for executable code, secrets, network access and data exfiltration, instruction overrides and dependencies.

Results live in [`audits/`](audits), one JSON file per skill. Each records the SHA-256 of the `SKILL.md` it covers, so a changed skill shows as not yet audited until it is audited again.

| Skill | Result | Audited |
| --- | --- | --- |
| marketing-project-setup | Pass, 7 of 7 checks | 2026-11-15 |
| marketing-campaign-setup | Pass, 7 of 7 checks | 2026-11-15 |
| loop-marketing-coach | Pass, 7 of 7 checks | 2026-11-15 |
| smart-app-banner | Pass, 7 of 7 checks | 2026-10-14 |

## Layout

```
skills/
  <group>/            content, aso, and seo once it has a skill
    <skill-name>/
      SKILL.md        instructions the agent loads
      README.md       what the skill does and how to install it
      references/     details the skill opens when needed
audits/
  <skill-name>.json   latest security audit
```

Skill names are unique across groups, because agents install skills into one flat folder.

## License

MIT
