# STATUS — Lavender Moon

*Last updated: 2026-04-23*

## What this is
Dalena's spiritual business — tarot, spiritual life coaching, Reiki, mediumship, spellwork. Main site + intake form + (paused) AI influencer side project.

## What's live
- Main site — https://lavendermoontarot.com/ (v1.7)
- Intake form — https://lavendermoontarot.com/intake-form/ (multi-select services, conditional birth fields, CC to Dalena via Formspree `_cc`)
- 10 service pages indexed, sitemap + GSC verified
- Shop Square links: One Question $22.22, Three Question $44.44
- Membership Square links: Monthly $150/mo, Weekly $500/mo (pay-first → Dalena contacts within 24h)
- Google Calendar booking for regular sessions

## What's broken / blocked
- **Live session payment not built** — need 4 Square links from Cal ($44, $77, $111, $222), then add pay-first flow same as membership
- Chat widget still `<!-- REPLACE -->` — provider not chosen (Tidio, Crisp, etc.)
- Google Business Profile not claimed yet — Dalena needs instructions
- AI Influencer (Mira) side project — paused April 21, 2026. Resume via `ai-influencer/MASTER-PLAN.md`

## What's next
1. Cal creates 4 Square payment links for live sessions, wire into intake form confirmation
2. Pick a chat widget, swap placeholder
3. Send Dalena GBP claim instructions
4. (Optional pitch Friday) ManyChat lead magnet — keyword MOON, Notion guide already built

## Key files
- `website/index.html` — main site
- `intake-form/index.html` — intake form
- `discovery-form/index.html` — original discovery form (Cal-Zentara/dalena-discovery)
- `CLAUDE.md` — brand, services, decisions, Square links, AI influencer plan
- `ai-influencer/MASTER-PLAN.md` — resume point for Mira project

## Deploy notes
- GitHub: `Cal-Zentara/LavenderxMoon` (main site + intake form in same repo)
- **Switch GH account before pushing:** `gh auth switch --user Cal-Zentara` (AutoBuildCharlie does NOT have access). Do NOT switch back.
- Domain: lavendermoontarot.com (lavendermoon.com is taken — owned by Kathy Randall since 1998)
- Formspree: `mgorkqvz` (intake), `xvzvnkay` (discovery)
- **Never round angel number prices** — $22.22, $44.44, $77, $111, $222 are intentional brand.

## Open questions (AI Influencer)
- Revenue split with Dalena if Mira funnels real clients
- Tell Dalena about Mira before any funnel reel goes live (brand risk)
- Handle `@mirasmoondays` availability unverified
