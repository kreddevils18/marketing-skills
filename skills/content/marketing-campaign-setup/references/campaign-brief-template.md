# Campaign brief template

Save as `marketing/campaigns/<utm>.md`. Each section opens with an italic
question, following HubSpot's brand context example, and the four stage sections
follow Loop Marketing: Express (concept), Tailor (format), Amplify (channels and
schedule), Evolve (measure and learn).

```markdown
---
name: "YYYY-MM · brand · Channel · Goal · Topic"
brand: [brand-code]
business_goal: "[the Business Goal from the profile this campaign serves]"
channel: [main channel]
goal: awareness | engagement | signups | sales
target: "[metric] [number] in [time window]"
baseline: "[current value, source, date]"
start: YYYY-MM-DD
end:                      # optional
status: planning | live | done
utm: yyyymm_brand_channel_goal_topic-slug
message: "[the one idea every piece repeats]"
offer: "[what the audience gets for taking the action]"
audience: "[one slice of the profile's audience]"
landing_page: [URL or empty]
---

# [Campaign name]

_Use with `../shared-rules.md` and `../taste-profiles/[brand-code].md`._

## Campaign concept

_What is the idea, and what is it for?_

- **For:** [one audience slice and where they are stuck]
- **Business goal:** [the Business Goal from the profile this campaign serves, quoted]
- **Goal:** [awareness | engagement | signups | sales, the result that moves the business goal]
- **Target:** [metric, number, time window, and the baseline]
- **Message:** [one idea, built on one belief from the profile]
- **Offer:** [what they get, and the action that gets it]

## Express: concept test

_Does the concept hold up in front of the audience?_

- **Simulated audience:** [2 or 3 personas from the profile]
- **Main objections:** [ ]
- **Decision:** keep | revise | drop, because [ ]

## Tailor: format

_In what form do we talk to this slice?_

- **Formats:** [from the profile's format list]
- **Hooks to test:** [2 or 3 hook styles]
- **Call to action:** [the one action that moves the target]

## Amplify: channels and schedule

_Where, when and how often?_

- **Channels:** [main channel; others only if the user chose them]
- **Dates:** [start] to [end or "open"]
- **Cadence:** [e.g. one post a day, one thread a week]
- **Links:** every link carries `utm_campaign=[utm]`

## Evolve: measure and learn

_Is it working, and what changes next time?_

- **Metrics:** [primary metric for the goal, plus 2 or 3 supporting ones]
- **Check-in:** [e.g. every 2 weeks]

| Date | Metric values (source) | What we learned | Change |
|---|---|---|---|

- **Lessons for the next campaign:** [fill at the end]
```

## Business goal, goal, target, message and offer

| Term | What it is | Test | Example (build-in-public series on X) |
|---|---|---|---|
| Business goal | What the brand wants long term, from the Taste Profile | Is it quoted from the profile, not invented for this campaign? | Authority with founders, builders and indie hackers |
| Goal | The result this campaign moves toward the business goal | Is it one of awareness, engagement, signups, sales? | Awareness |
| Target | The goal as a number | Metric, number, time window, baseline? | +500 followers on X in 8 weeks, from 1,200 (X analytics, 2026-11-15) |
| Message | The idea every piece repeats | Could every post in the campaign carry it? | People and AI build together; real numbers show how |
| Offer | What the audience gets for taking the action | Would someone take it, and is it what they receive rather than what we say? | Follow for a weekly breakdown with real revenue, costs and the prompts behind it; or a free open-source skill pack |

Common mistakes: writing the message or a slogan in the offer field; a goal
with no number; a target with no time window; two offers competing for one
action.

## Metric hints by goal

| Goal | Primary metric | Supporting |
|---|---|---|
| Awareness | Followers or reach | Impressions, profile visits, bookmarks |
| Engagement | Replies and shares per post | Bookmarks, saves, watch time |
| Signups | Signups from the UTM | Click-through rate, landing page conversion |
| Sales | Revenue or paid conversions from the UTM | Trial starts, checkout conversion |
