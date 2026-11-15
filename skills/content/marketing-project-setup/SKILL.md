---
name: marketing-project-setup
description: Set up the marketing foundation for a brand as Markdown files, shared writing rules plus one Taste Profile per brand (guidelines, voice, business goals, audience, beliefs with proof, voice bank), by interviewing the user one question at a time. Use when the user wants to define a brand voice, write a taste profile or style guide for AI, add a new brand or app to their marketing, or run a profile's quarterly review. Not for planning a single campaign (marketing-campaign-setup) or reviewing drafts and results (loop-marketing-coach).
---

# Marketing Project Setup

Produce the context an AI needs to write like this brand instead of like every
other AI: a short shared rulebook and a Taste Profile per brand, written as
Markdown files the user owns. This is the Express stage of HubSpot's Loop
Marketing: a human sets taste, tone and point of view before AI produces
anything. A profile is good when someone pasting it into a prompt gets on-voice
output without further explanation, and every claim in it is true.

## When to use

- "Set up marketing for my app", "define our brand voice", "write a style guide
  the AI can follow", "add my second app as a brand", "review my taste profile".
- One person often runs several brands: a personal brand and one or more
  products. Each gets its own profile. A community campaign uses the profile of
  whoever owns the community.
- Not for: a dated campaign with a goal and a number (marketing-campaign-setup),
  drafting or reviewing posts and checking results (loop-marketing-coach).

## Files this skill owns

```
marketing/
  shared-rules.md             rules every brand follows
  taste-profiles/<brand>.md   one file per brand
  campaigns/                  created empty; marketing-campaign-setup fills it
```

Put `marketing/` at the project root unless the user names another place or one
already exists; then use that one. Never overwrite an existing profile: update
sections in place and keep the user's wording unless they ask for a rewrite.
Write the files in the language the user talks to you in. Published content uses
the language set in the profile.

## How to work

1. **Scout before asking.** Read what already exists: `marketing/`, README,
   landing page copy, app store listing, pricing, past posts the user points to.
   Turn what you find into proposed answers, so the interview confirms rather
   than starts from blank.
2. **Shared rules first, once.** If `shared-rules.md` is missing, create it from
   `references/shared-rules-template.md` and confirm each rule with the user.
   Rules that apply to every brand live only there; a profile records only what
   differs.
3. **Interview one question at a time.** Offer 2 to 4 concrete options with your
   recommendation first, plus free text. Use the platform's question tool when
   it has one. Follow `references/interview-guide.md` for the order and the
   follow-ups that turn vague answers into usable ones.
4. **Write the profile** from `references/taste-profile-template.md`. Each core
   section opens with its italic question and holds 3 to 5 bullets short enough
   to paste into a prompt. Keep the reference material (formats, voice
   examples, voice bank) below the core sections.
5. **Show it, then mark it active.** Present the file, apply the user's edits,
   and set `status: active` only after they confirm. A brand with gaps stays
   `status: draft`.

## Constraints that matter

- **No invented facts.** Beliefs need proof the brand really has (a product, a
  number, a shipped result). Numbers come from the user or their analytics tools
  with source and date. When there is no proof yet, write the belief as a
  hypothesis or leave `[ ]`, and say so.
- **Voice bank entries are drafts.** Write them in the publishing language,
  label them as drafts, and expect the user to rewrite them.
- **Other creators' posts are skeletons, not sources to copy.** Extract hooks
  and formats into the profile with source and date; never reuse their sentences.
- Leave anything the user calls private (a product they do not want named, an
  unannounced launch) out of every file, and add it to the "never mention" rule.

## Done when

- `marketing/shared-rules.md` exists and the user confirmed it.
- `marketing/taste-profiles/<brand>.md` has every core section filled, no `[ ]`
  left in Guidelines, Voice, Business Goals, Audience or Beliefs, and each belief
  names its proof.
- Frontmatter `status` matches reality: `active` only after user confirmation.
- You told the user which brands still have draft profiles.

## Resources

- `references/interview-guide.md`: question order, options and follow-ups for
  each section; open it before the first question.
- `references/shared-rules-template.md`: starting rules for `shared-rules.md`.
- `references/taste-profile-template.md`: the profile file, with frontmatter.
- `references/channel-formats.md`: how to extract post formats from top
  performers, with a starting catalog for X; open it when filling a profile's
  format list.
