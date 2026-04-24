# STATUS — Lavender Moon

*Last updated: 2026-04-24*

## What this is
Dalena's spiritual business — tarot, spiritual life coaching, Reiki, mediumship, spellwork. Main site + intake form + (paused) AI influencer side project.

## What's live
- Main site — https://lavendermoontarot.com/ (v1.8)
- Intake form — https://lavendermoontarot.com/intake-form/ (radio service selection, pay-first for all sessions)
- 10 service pages indexed, sitemap + GSC verified
- Shop Square links: One Question $5.55 sale / $22.22 reg, Three Question $11.11 sale / $44.44 reg (sale links PENDING — Dalena needs to create $5.55 and $11.11 Square links)
- Membership Square links: Monthly $150/mo, Weekly $500/mo (pay-first → Square redirects to calendar)
- Live session Square links wired: $44, $77, $111, $222 (pay-first → Square redirects to Google Calendar)
- Service cards on main site route through intake form (no bypass to Square)
- Customer-facing descriptions added to all 4 live session Square items

## What changed 2026-04-24
- Services section redesigned: 3-column card grid + $222 Full Soul Blueprint as full-width featured card with cinematic overlay
- Live session Square links created ($44/$77/$111/$222) and wired to intake form confirmation
- Intake form: service selection switched from checkboxes to radio buttons (one pick only)
- Intake form: pay-first flow added for live sessions — confirmation shows Square link, Square redirects to Google Calendar
- Service cards now route to intake form instead of direct Square links
- Hero video poster image removed (was showing old woman-with-cards photo)
- Square item descriptions written and saved for all 4 live session items
- Chat widget pitch added to Dalena Notion page

## What's broken / blocked
- **Shop sale links not built** — Dalena needs to create $5.55 and $11.11 Square payment links. Current shop buttons link to full-price items.
- Chat widget still `<!-- REPLACE -->` — Crisp recommended, waiting on Dalena's go-ahead
- Google Business Profile not claimed yet — Dalena needs instructions
- AI Influencer (Mira) side project — paused April 21, 2026. Resume via `ai-influencer/MASTER-PLAN.md`

## What's next
1. Dalena creates $5.55 and $11.11 Square links → Cal swaps into shop section (2 min job)
2. Dalena approves Crisp chat widget → Cal drops in (10 min job)
3. Send Dalena GBP claim instructions
4. ManyChat pitch — Notion doc ready at https://www.notion.so/34b2117d144781738269dfc1dd748b93

## Key files
- `index.html` — main site (was website/index.html, now at root of repo)
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
