---
name: marketing-campaign-setup
description: Plan one marketing campaign as a Markdown brief, one goal, one audience slice, one offer, one target number and a start date, named by convention with a matching UTM and structured by the Loop Marketing stages, including a concept test against the brand's audience. Use when the user wants to start, plan or brief a campaign, a launch, a content series or a promotion for a brand. Not for defining the brand voice (marketing-project-setup) or drafting posts and reviewing results of a running campaign (loop-marketing-coach).
---

# Marketing Campaign Setup

Turn "let's do some marketing for X" into a brief a human or an AI can execute
without guessing: a single Markdown file with the campaign's goal, audience,
offer, target, dates, naming and UTM, plus one section per Loop Marketing stage.
A campaign is time-bound and has one goal and one number; ongoing positioning
belongs in the brand's Taste Profile, not here.

## When to use

- "Plan a campaign for my launch", "brief a build-in-public series on X",
  "set up next month's promotion", "what should this campaign's target be?".
- Not for: defining voice, audience and beliefs (marketing-project-setup);
  drafting posts, reviewing drafts or checking a live campaign's numbers
  (loop-marketing-coach).

## Inputs

The brief builds on files from marketing-project-setup:

```
marketing/
  shared-rules.md
  taste-profiles/<brand>.md
  campaigns/<utm>.md          this skill writes one file per campaign
```

Read `shared-rules.md` and the brand's profile first. If the profile is missing
or `status: draft`, say what is missing and offer to run marketing-project-setup
first; a brief written without a profile defaults to generic AI copy. Write the
brief in the language the user talks to you in.

## How to work

1. **Pin the essentials, one question at a time,** with options and your
   recommendation first: brand, channel, goal, target, audience slice, message,
   offer, start date, optional end date. Draw options from the profile (business
   goals, audience pains, beliefs, formats) instead of generic ones.
2. **Keep goal, offer and message apart.** They are the terms most often mixed
   up; `references/campaign-brief-template.md` defines them with examples.
   - **Goal:** the business result the campaign exists to move (awareness,
     engagement, signups or sales), serving a Business Goal in the profile. The
     **target** makes it measurable: metric, number, time window, baseline
     ("+500 followers on X in 8 weeks, from 1,200").
   - **Offer:** what the audience gets in exchange for the action the goal
     needs: a free template, an open-source repo, a trial, a discount, a
     newsletter, a series worth following. It is not the slogan.
   - **Message:** the one idea every piece repeats, built on one belief from
     the profile.
3. **Hold the line on one of each.** One goal, one target, one audience slice,
   one message, one offer. When the user names two goals, propose splitting
   them into two campaigns. A start date is required, the end date is optional.
4. **Name it and tag it** with `references/naming-and-utm.md`. The file name is
   the UTM, so names and links stay in sync.
5. **Write the brief** from `references/campaign-brief-template.md`.
6. **Test the concept before any content exists** (Express). Role-play 2 or 3
   members of the profile's audience, have each react honestly to the message
   and the offer (would they take it?), then record the main objections and a
   decision: keep, revise or drop. Label it as simulated feedback; it is a
   hypothesis to check, not data.
7. **Fill Tailor, Amplify and Evolve** with the formats and hooks to test, the
   channels, cadence and dates, and the metrics and check-in rhythm. Leave
   "Lessons" empty until the campaign ends.

## Constraints that matter

- Targets and baselines are real numbers from the user or their analytics,
  with source and date. Without a baseline, say so and propose a target the user
  confirms rather than inventing one.
- Every link in the campaign carries the campaign's UTM.
- Do not add channels the user did not choose to make the plan look bigger; the
  profile's `channels` field says where the brand is today.

## Done when

- `marketing/campaigns/<utm>.md` exists, its name follows the convention and its
  file name equals the UTM.
- Frontmatter has brand, channel, goal, target (metric, number, window), start
  date, status `planning`, message and offer, and the offer is something the
  audience receives, not a slogan; the brief links the profile it uses.
- The concept test is recorded with a decision.
- No `[ ]` remains outside Evolve's lessons, or you listed what is still open.

## Resources

- `references/naming-and-utm.md`: name and UTM convention with goal codes and
  examples; open it before naming.
- `references/campaign-brief-template.md`: the brief file with frontmatter and
  the Loop Marketing sections.
