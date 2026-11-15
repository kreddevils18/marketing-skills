# Taste Profile template

Save as `marketing/taste-profiles/<brand>.md`, where `<brand>` is the lowercase
brand code. The code also appears in campaign names and UTMs, so keep it short
and stable (`jane`, `acme`).

The shape follows HubSpot's brand context example (Guidelines, Voice, Business
Goals) plus the Express-stage pieces of Loop Marketing (audience, contrarian
beliefs, voice bank). Each core section starts with an italic question and holds
3 to 5 bullets.

```markdown
---
brand: [Display name]
code: [brand-code]
type: personal | product
status: draft | active
language: [publishing language]
channels: [main channel first, e.g. X, then blog]
reviewed: YYYY-MM-DD
---

# [Display name]

_Use together with `../shared-rules.md` and the campaign brief. Review every quarter._

## Guidelines

_Rules for this brand, on top of the shared rules, and what it never says._

- [Tone boundary, e.g. "No guru voice. If it sounds like an ad, it is wrong."]
- [Opening habit, e.g. "Open with what I tried, not what you should do."]
- [Topic or claim boundary]

## Voice

_How the brand sounds, with sample lines._

- [Person and register: I / we / product name; calm, direct, plain English]
- [Who is speaking: practitioner, team, product]
- Samples: "[line]" / "[line]"

## Business Goals

_What is this brand, and what does it really want?_

- [What it is and who it serves, one line]
- [The goal content serves: authority, signups, sales; where it starts]
- [Offer and price, or "no paid offer yet"; what serves as proof]

## Audience

_Who are we talking to, and where are they stuck?_

- [Who, specifically, and where they spend time]
- Stuck on: [2 to 4 pains in their words]
- Want: [2 to 4 outcomes]

## Beliefs

_What do we believe that many others do not? Each belief names its proof._

1. [Belief]. Proof: [product, number or shipped result].
2. [Belief]. Proof: [ ].
3. [Belief]. Proof: [ ].

## References

### Formats that work on [channel]
[From channel-formats.md: common traits and 5 to 12 formats, with source and date.]

### Right and wrong voice
- Wrong: "[generic AI line]"
- Right: "[on-voice line with [N] placeholders for real numbers]"

### Voice bank
_Drafts in [language]. Rewrite in your own words; delete what you would not say._
1. **Q:** [question the audience really asks]
   - [answer in the brand's voice, built on one belief]

### Measuring Express
- Time from idea to approved post.
- Number of edits per post caused by off-voice wording.
```
