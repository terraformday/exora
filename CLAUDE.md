# Exora Magazine — working notes for Claude

This repository is the **exoramagazine.com** website. The magazine itself (Issue 01, Winter 2027)
lives mostly in the shared Google Drive; this repo is only the public site.

## Who decides

**Morgane** is the founder and the person to ask about anything editorial, brand, print or
partner-facing. **Anton** owns the repo and the tooling. If a question is about wording, money,
dates or who's in the magazine, it's Morgane's. If it's about hosting, deploys or access, it's
Anton's.

## Deploying is live

Hosted on **Cloudflare Workers**. Workers Builds runs `npx wrangler deploy` on every push to
`main`, so **a push to `main` is a live deploy, within a minute or two. There is no staging.**
Work on a branch and show the change before merging, unless told otherwise for that change.

Preview locally with the `exora` dev server (`.claude/launch.json`, port 8787) — it's a plain
static server on the repo root, same as production.

## Standing rules (Morgane's, carried from the project handoff)

1. **Name:** always "Exora Magazine" or "Exora Mag" in copy, **never "Exora" alone**. The one
   exception is the big wordmark logo, which stays "Exora". The URL is written exoramagazine.com.
2. **Filing:** every visual goes into the Exora Magazine Google Drive folder. Keep only the
   latest version in place and move earlier ones into an "Old versions" subfolder beside it.
   *(Settled 27 Nov 2026: for Issue 01, Drive stays the home — the global "Dextr replaces Google
   Drive" rule is deliberately not applied to this project. Don't propose moving it mid-issue.)*
3. **Contributor pay:** never write "contributors get paid". The approved line is "We can't pay
   contributors yet, but if Exora Mag makes money, they'll be the first to be paid."
4. **Founding partner prices stay off** the website and social posts — shared on request only.
5. **Explain in plain English.** Small steps, show the result, say what changed. No jargon.
6. **Don't re-argue settled decisions** — see the table below.
7. **Ask before** spending money, deleting anything, publishing or posting on her behalf, or
   changing payment links.

## Voice

Exora Magazine sounds like **a host pulling out a chair for you**: warm, plain, a little funny,
never glossy or salesy.

- Written by the people who live it, not *about* them. Never a trend piece.
- Warm, not gushing — one warm touch per piece is enough.
- Plain words, short sentences. No "curated", no "elevated living", no property-speak.
- Honest about money, including about not paying contributors yet.
- Questions invite people in; social posts end by asking readers something.
- Humour from real house life, never at anyone's expense, and **no nomad or "hippie" stereotypes**.
- "I, Morgane" for personal posts; "we" for the magazine.
- Lower the bar to contribute: "You don't need to be a writer."
- Inclusive of every way of living together, not just twenty-something nomads.

**Style sheet**

- Audience phrase: "people who choose to live together"; "coliving, cohousing, eco-villages,
  shared homes and communities".
- UK English (colour, organise, favourite).
- **coliving / coliver**: lower case, one word, no hyphen — except proper names.
- Issue numbers: "Issue 01". Dates: "20 December", "Saturday 20 February 2027".
- Prices: £14, £48, £4, £12 — no pence.
- Instagram: at most one emoji per caption; hashtags at the end or first comment; posts ~6pm UK.

## Settled decisions — don't bring the old version back

| Topic | Was | Now |
|---|---|---|
| Audience | Colivers, digital nomads, hosts | People who *choose* to live together; nomads are one angle |
| Name in copy | "Exora" | "Exora Magazine" / "Exora Mag"; wordmark stays "Exora" |
| Contributor pay | "Contributors get paid" | Not paid now; first to be paid if it makes money |
| Format | Pocket journal, then A4 | A5 |
| Pricing | Pay-what-you-can, then £9 print | £14/£48 print, £4/£12 online, optional pay-more |
| Launch | 31 Jan 2027, then 13 March | Dinners Sat 20 Feb 2027; site says "Winter 2027" |
| Advertising | "Advertise with Exora", 4 ads; insurance/banking/travel gear a fit | **Partners**, not ads: grassroots products and community spaces. **No insurance, banks or furniture** |
| Partner prices | On the website | Private, on request |
| Partner offer | 2 copies of Issue 01 | 2 copies of every issue for a year + shout-outs + a voice in shaping it, still £200 |
| Partner count | "1 spot left", then 2 of 4 | 3 of 4 signed, 1 left (27 Nov 2026) |
| "In this issue" | Section list with empty pieces | Removed until there are real stories |
| Hero line | "… Kettle's on." | "… Be in it." |
| Contributor platform | Members' platform or WhatsApp group | Neither — a public progress strip |
| Stickers | Teapot/house die-cuts, "Exora Mag" | All three round, "Exora Magazine" spelled out |
| LinkedIn banner | Toucan as main image | Logo only, no toucan |

**Older files still show the old versions** — the launch plan PDF of 13 Nov, early Instagram
captions, the design canvas. Never copy wording from them without checking this table.

## Brand

| Name | Hex | Use |
|---|---|---|
| Cream (paper) | `#FFF4E0` | Backgrounds |
| Navy (ink) | `#1D3557` | Text, outlines |
| Coral | `#EF7B67` | The "ra", highlights |
| Coral text | `#D9573F` | Coral as text on cream |
| Brick red | `#C2412D` | Handwritten accents |
| Butter yellow | `#F4B63F` | The sun dot, stickers |
| Sky blue | `#A9D3E6` | Secondary fills |
| Soft navy | `#4F6482` | Small print |

Type: **Fraunces** bold (soft + wonky axes on) for headlines, **DM Sans** for body, **Caveat**
semibold for handwritten notes, used sparingly and slightly tilted. All loaded from Google Fonts.

Wordmark: "Exo" navy, "ra" coral italic, with a butter-yellow sun dot just above the horizon.

## Repo map

- `index.html` — landing page (the long one; partner section near the bottom)
- `about.html` — the story
- `policies.html` — privacy, pre-orders, refunds
- `gift/` — one page per downloadable gift card, so downloads show in analytics
- `social/` — Instagram tiles
- `wrangler.jsonc`, `.assetsignore` — Cloudflare config

No build step. Edits are hand-written HTML; styles are inline in each page's `<style>` block.

## Things that are easy to get wrong here

- The partner section used to be the "advertise" section. Check for stray "ad"/"advertise"
  wording across **all** pages, including `policies.html`, not just `index.html`.
- The site moved from Render to Cloudflare on 26 Nov 2026. Stale "hosted on Render" lines have
  turned up in the README and the privacy policy.
- `.spots` in `index.html` is a small inline-flex badge sized for about six words. Long sentences
  put in it overflow its parent — measure it after changing it, don't just screenshot.
