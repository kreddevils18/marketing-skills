# Naming and UTM

## Campaign name

`YYYY-MM · Brand · Channel · Goal · Topic`

- `YYYY-MM`: the start month, so campaigns sort by date.
- `Brand`: the brand code from the Taste Profile's frontmatter (`code`).
- `Channel`: the main channel (X, LinkedIn, Blog, Email, App Store, Multi).
- `Goal`: one of Awareness, Engagement, Signups, Sales.
- `Topic`: what the campaign does, as content form plus subject. Someone should
  understand the campaign from the name alone, without opening the file.

| Weak topic | Why it fails | Strong topic |
|---|---|---|
| How to … with AI | A slogan; says nothing about what ships | Build-in-public series: how I build and market my apps solo with AI |
| Q4 push | No form, no subject | Black Friday discount: 40% off yearly plan |
| Launch | Launch of what, where | Product Hunt launch: v2 with team workspaces |

## UTM

Lowercase, parts joined by underscores, in the same order as the name:

`yyyymm_brand_channel_goal_topic-slug`

| Goal | Code |
|---|---|
| Awareness | `aware` |
| Engagement | `engage` |
| Signups | `signup` |
| Sales | `sales` |

The topic slug is 2 to 5 lowercase words joined by hyphens. Use the UTM as
`utm_campaign`, and add `utm_source` (the channel) and `utm_medium` (social,
email, cpc) per link.

## Example

- Name: `2026-11 · jane · X · Awareness · Build-in-public series: how I build and market my apps solo with AI`
- UTM: `202611_jane_x_aware_solo-build-with-ai`
- File: `marketing/campaigns/202611_jane_x_aware_solo-build-with-ai.md`
- Link: `https://example.com/?utm_source=x&utm_medium=social&utm_campaign=202611_jane_x_aware_solo-build-with-ai`
