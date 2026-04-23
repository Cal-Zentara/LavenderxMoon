# LavenderxMoon — Project Index

## Quick Nav — Read First

| I'm doing... | Read only... |
|---|---|
| Continuing work / resuming | `STATUS.md` |
| Fixing a bug | `STATUS.md` + specific section of this doc |
| Adding a feature | `STATUS.md` + Website / Intake Form sections |
| Deploying / publishing | Key Decisions (GitHub account switching) + Website section |
| AI Influencer work | `ai-influencer/MASTER-PLAN.md` |
| Understanding the whole project | This CLAUDE.md in full |

**Do not explore.** If the answer isn't in the files above, ask before searching.

---

## Dev Reference — Symbol Map / Schema / Gotchas

> Keep line ranges current. If a code change shifts lines, update the table in the same edit.

### Symbol Map

| Feature | File | Lines |
|---|---|---|
| Nav (fixed, theme toggle, hamburger) — HTML | `website/index.html` | 150–204 |
| Nav — scroll handler / theme / mobile menu JS | `website/index.html` | 1110–1143, 1514–1584 |
| Hero (split, video, poster fallback) | `website/index.html` | 206–281, 1157–1182 |
| Lead Bar (free consultation + phone) | `website/index.html` | 283–309, 1187–1195 |
| Services (ruled list, angel pricing, Soul Blueprint banner) | `website/index.html` | 324–402, 1198–1251 |
| About (profile, bio, pull quote, gold highlights, cert) | `website/index.html` | 404–501, 1255–1322 |
| Testimonials carousel (arrows + dots) | `website/index.html` | 503–586, 1325–1365, 1527–1549 |
| Shop (product cards, Square links) | `website/index.html` | 588–661, 1368–1427 |
| Memberships (grid, featured + coming-soon badges) | `website/index.html` | 663–757, 1431–1472 |
| Final CTA (seal + booking) | `website/index.html` | 759–786, 1475–1492 |
| Footer | `website/index.html` | 788–820, 1497–1506 |
| All CSS (tokens, layout, animations, themes) | `website/index.html` | 18–1026 |
| JS (scroll, observer, carousel, mobile menu, theme) | `website/index.html` | 1513–1584 |
| Intake form (Formspree, multi-select services, conditional birth fields) | `intake-form/index.html` | 1–630 |
| Discovery form (6-section questionnaire) | `discovery-form/index.html` | 1–50+ |
| Service pages (tarot/reiki/mediumship/etc.) | `website/[service]/index.html` | shared nav/footer + page-specific content |

### Data Schema

**Intake form (`intake-form/index.html`):**
- Formspree POST: `https://formspree.io/f/mgorkqvz`
- Fields: `name`, `email`, `phone` (optional), `service` (multi-select checkbox), `dob` (conditional), `tob` (optional), `birth_location` (conditional), `notes`
- Hidden fields: `client_name=Dalena`, `_subject`, `_cc=Dalenanch@gmail.com`
- URL param: `?service=monthly` or `?service=weekly` pre-selects membership option
- Conditional fields: DOB + birth location required only if service includes Soul Blueprint or Astrology (`required` set/cleared via JS lines 550–558)

**Discovery form (`discovery-form/index.html`):**
- Formspree POST: `https://formspree.io/f/xvzvnkay`
- Hidden field: `client_name=Dalena`

**Main site storage:**
- localStorage key: `lm-theme` (values: `'dark'` or `'light'`)

**External links (Square + Calendar):**
- Monthly membership: `https://square.link/u/SrOGfL4X`
- Weekly membership: `https://square.link/u/gM6WUXcC`
- One Question reading: `https://square.link/u/UG1toelh`
- Three Question reading: `https://square.link/u/1RkwOVWl`
- Live session booking (Google Calendar): `https://calendar.app.google/1MGnax6DEzcqBokH6`
- Live session payment links ($44/$77/$111/$222): **PENDING** — Cal needs to create in Square

### Known Gotchas

- **Angel number pricing never rounded** — $5.55, $11.11, $22.22, $44.44, $77, $111, $222 are intentional brand. Never change or round.
- **Theme toggle uses `data-theme="light"` on `<html>`**, not a class on body. Light palette under `[data-theme="light"]` selector, lines 823–862.
- **Hero video shows poster image as fallback** — video won't load until `assets/NewHero.mp4` is present. No code change needed to activate.
- **Service checkboxes are multi-select, not radio** — submission checks for at least one selection (line 586–589).
- **Membership flow branches to Square, sessions branch to Google Calendar** — confirmation-screen branch key is keyword match on selected service value (`membership`, `monthly`, `weekly`) at lines 596–614.
- **Cert image fallback to nav logo** — `D2730B97` asset was never added. Intake form line 404 uses circular nav logo as substitute.
- **Formspree `_cc` hidden field** — Formspree free tier only allows one primary recipient. `_cc=Dalenanch@gmail.com` is the workaround so both Cal and Dalena receive submissions without any Gmail filter setup.
- **Mobile menu closes on link click** via `closeMenu()` (line 1569) — intentional.
- **`--text-muted` bumped to `oklch(65% 0.025 295)`** — was `oklch(50%)`, failed WCAG AA. Don't roll back.

---

Dalena's spiritual business. Tarot readings, spiritual life coaching, Reiki, mediumship, channeling, spellwork. OC-based.

---

## Table of Contents

1. [Project Overview](#project-overview)
2. [Brand Intelligence](#brand-intelligence)
3. [Services & Pricing](#services--pricing)
4. [Testimonials](#testimonials)
5. [Discovery Form](#discovery-form)
6. [Website](#website) ← live
7. [Intake Form](#intake-form) ← live
8. [Square Payment Links](#square-payment-links)
9. [Key Decisions](#key-decisions)
10. [Current Status](#current-status)
11. [Next Steps](#next-steps)
12. [Hero Video Prompt](#hero-video-prompt-kie-api--seedance-10)
13. [AI Influencer — Mira](#ai-influencer--mira) ← paused April 21

---

## Project Overview

| Field | Value |
|---|---|
| Client | Dalena |
| Business | Lavender x Moon (lavenderxmoon.org) |
| Type | Spiritual life coaching, tarot, Reiki, mediumship, channeling, spellwork |
| Folder | `SSP/LavenderMoon/` |
| Relationship | Client (friend of Cal) |
| Started | April 11, 2026 |

---

## Brand Intelligence

Scraped from lavenderxmoon.org — April 2026. Use this when building the site.

**Tagline:** "Spellwork • Life Guidance • Intuitive Insight"

**Hero headline:** "Intuitive Spiritual Guidance Tailored To You"

**Hero body copy:**
> "At Lavender Moon, each session is deeply personalized and intuitively guided to bring clarity, healing, and alignment. Through Soul Blueprint readings, tarot, astrology, energy work, and ritual guidance, I help you uncover your soul's patterns, release energetic blocks, and step confidently into your highest path."

**Brand voice:** Casual, direct, confident. Not overly woo-woo. Example: *"Tell me what's going on — I'll let you know what I'm picking up and what's aligned for you."*

**Angel number pricing:** She prices everything using angel numbers ($22.22, $44.44, $77, $111, $222) — this is intentional and part of her brand. Never change or round these.

**Lead magnet:** Free text consultation for spellwork, life direction, and intuitive guidance. Phone: **(714) 519-7650**

**Existing site color:** Light lavender/purple — her brand palette. Our build uses a richer/deeper `#8B6DB5` version.

**Testimonial display style:** She shows client feedback as iMessage-style text bubbles — carry this into the new site.

**About / Origin story (use verbatim on the site):**
> "Hello, I'm the Intuitive Behind Lavender Moon
>
> My name is Dalena and I have been doing readings for over 5 years. I am a certified Spiritual Life Coach, certified in channeling, a Reiki practitioner, and a practicing medium. My spiritual awakening started when I was a child and gradually became louder as I got older. I began fully awakening through a near-death experience that was followed by spontaneous spirit communication, heightened sensitivity to energy, and deep intuition. What started as intuitive guidance for close friends and family naturally evolved as I continued to receive clear, accurate insights that consistently resonated on a soul level. Over time, I honed these gifts through study, lived experience, and intentional spiritual practice, allowing me to channel messages with clarity, compassion, and integrity. My work blends intuitive tarot, soul-level insight, and energetic awareness to help you gain clarity, healing, and direction—especially during times of uncertainty or transition. I mix both eastern and western practices in my sessions, both learned through my ancestral lineage. Each session is approached with intention, integrity, and care, allowing messages to come through exactly as they're meant for you. Whether you're seeking reassurance, deeper understanding, or alignment with your higher path, my goal is to help you feel seen, supported, and empowered long after our session ends."

**Key bio details to carry into the site:**
- 5+ years of readings
- Certified Spiritual Life Coach, certified in channeling, Reiki practitioner, practicing medium
- Awakening started in childhood, triggered by a near-death experience
- Blends eastern + western practices from ancestral lineage
- Core promise: "feel seen, supported, and empowered long after our session ends"

**Two revenue streams:**
1. Live sessions — booked via calendar (Zoom/phone)
2. Async shop readings — delivered by email in 24–48 hrs

---

## Services & Pricing

### Live Sessions (booked via calendar)
| Service | Price | Duration |
|---|---|---|
| 1:1 Virtual Intuitive Tarot & Spiritual Guidance | $44 | 30 min |
| 1:1 Virtual Intuitive Tarot & Spiritual Guidance | $77 | 1 hr |
| Mini Soul Blueprint Reading | $111 | 45 min |
| Full Soul Blueprint Reading | $222 | 1 hr 15 min |

### Shop / Async Readings (delivered 24–48 hrs)
| Product | Regular | Sale | Categories |
|---|---|---|---|
| One Question Intuitive Tarot Reading | $22.22 | $5.55 | Love, Career, Life/General |
| Three Question Intuitive Tarot Reading | $44.44 | $11.11 | Love, Career, Life/General |

### All Services Offered
Tarot, oracle readings, mediumship, channeling, Reiki/energy work, spiritual life coaching, spellwork, astrology, Soul Blueprint readings, ritual guidance

---

## Testimonials

Displayed on her site as iMessage-style text bubbles. Use this format when building.

- *"Wow, I feel so inspired and uplifted after our session. Everything resonated deeply. Thank you for your incredible insight and guidance. ✦"*
- *"I came with so much heaviness, but your reading brought me peace and clarity. You have a truly magical gift."*
- *"This reading was exactly what I needed. I am feeling hopeful, and your guidance felt so comforting and accurate."*
- *"Your readings are always powerful and spot-on. I can't thank you enough for the light and clarity"*
- *"Wow the soul blueprint reading was about 85% accurate. I will let you know about the 15% once the timeline comes for it"*

---

## Discovery Form

| Item | Detail |
|---|---|
| File | `LavenderMoon/discovery-form/index.html` |
| Live URL | https://cal-zentara.github.io/dalena-discovery/ |
| GitHub repo | Cal-Zentara/dalena-discovery |
| Formspree endpoint | `https://formspree.io/f/xvzvnkay` |
| Hidden field | `client_name = Dalena` |
| Sections | 6 sections, ~32 questions |
| Built | April 11, 2026 |

**Sections:**
1. About You & Your Business (business name, years, modalities, fulltime status, referral, differentiator)
2. Services & Offers (services, booking method, free entry points, top service, sell online, membership)
3. Ideal Client (description, situation, where they find her, experience level, transformation)
4. Brand & Online Presence (vibe, assets, social activity, platforms, current site)
5. Website Vision (CTA, pages, copy readiness, photos, inspo, must-haves)
6. Timeline & Next Steps (timeline, budget, anything else)

**Color theme:** Deep violet-lavender `#8B6DB5` with rose-gold accent `#C9A0B4` — premium and feminine. Matches lavenderxmoon.org palette but richer.

**Why built this way:** Dalena already had a site (lavenderxmoon.org) — discovery form built first to understand what she wants before touching anything. Same process used for Nail'd It! Spa — collect info first, then build.

---

## Website

| Item | Detail |
|---|---|
| File | `LavenderMoon/website/index.html` |
| Status | **Live** — https://cal-zentara.github.io/LavenderxMoon/ |
| GitHub repo | Cal-Zentara/LavenderxMoon |
| Design context | `LavenderMoon/.impeccable.md` |
| Built | April 16, 2026 |
| Deployed | April 17, 2026 |

**Stack:** Single HTML file — vanilla HTML/CSS/JS, no framework. GitHub Pages deployment planned.

**Fonts:** Cinzel (headlines) + Josefin Sans (body)

**Color palette:** Near-black `oklch(11% 0.022 295)` bg, deep purple surfaces, warm gold `oklch(73% 0.08 57)` accent

**Sections built:**
1. Nav — fixed, scrolled state, circular logo + brand text
2. Hero — split layout (text left, video/photo right). Video element with poster fallback. **Drop `hero.mp4` into `assets/` to activate.**
3. Lead magnet bar — free consultation + phone
4. Services — ruled list layout, angel number pricing
5. Soul Blueprint banner — `A51B6781` image with caption overlay
6. About — profile photo + bio with pull quote + gold highlights + cert frame below
7. Testimonials — carousel with left/right arrows + dot nav (replaced iMessage bubbles)
8. Shop — product image cards with sale pricing
9. Final CTA — logo seal + booking button
10. Footer

**Assets used:**
| File | Where Used |
|---|---|
| `0D5C05C4...png` | Hero poster (until video ready) |
| `profile about me.jpeg` | About section photo |
| `IMG_5705...jpeg` | Cert frame in About section |
| `A51B6781...png` | Soul Blueprint banner |
| `9F92D20F...png` | Shop — One Question card image |
| `3434465C...png` | Shop — Three Question card image |
| `7384E367...png` | Nav logo (circular) |
| `7384E367...png` | CTA logo seal (D2730B97 was missing — swapped to circular logo) |
| `NewHero.mp4` | Hero video — new video deployed April 17, 2026 |

**Remaining placeholders in HTML:**
- Chat widget script — marked `<!-- REPLACE -->` (Tidio, Crisp, etc. — not yet decided)
- Membership signup links — marked `<!-- REPLACE: add membership signup/booking link -->` (Square subscriptions not set up yet)

---

## Key Decisions

| Decision | Reason |
|---|---|
| Folder named `LavenderMoon`, project named `LavenderxMoon` | Cal confirmed the name; folder kept clean (no special chars) |
| Color: `#8B6DB5` not `#b8a7d6` | Site's original lavender is too pastel — went richer/deeper to feel premium |
| Built discovery form before website | Same process as Nail'd It! — collect answers first, don't guess |
| Repo: `dalena-discovery` (not `lavenderxmoon-discovery`) | Cal uses client first name for discovery repos |
| Fonts: Cinzel + Josefin Sans | Cinzel = sacred/Roman inscription energy. Josefin Sans = clean, slightly art deco. Both off the banned reflex list. |
| Dark theme | TikTok traffic = night browsing, reflective headspace. Dark feels sacred, not clinical. |
| Services as ruled list, not cards | More editorial and premium than card grid. |
| Angel number prices never rounded | Intentional brand choice — never change $5.55, $11.11, $22.22, $44.44, $77, $111, $222. |
| Hero as video element with image poster | Poster shows until `hero.mp4` is dropped into assets — no code change needed. |
| Cert shown full-width below About photo | Small badge was pixelated and unreadable. Full-width framed is legible and builds trust. |
| Pull quote + gold highlights in bio | Plain paragraphs felt boring. Pull quote breaks scroll, gold highlights make it scannable. |
| Testimonials as carousel not iMessage bubbles | Cal didn't like chat-bubble style — carousel is compact and more editorial. |
| Cert has gold gradient border | Adds premium feel. `padding: 6px` + linear-gradient background on `.cert-frame`. |
| Shop images use `object-fit: contain` | Cards were cropping the product images — contain shows the full graphic. |
| CTA seal uses circular nav logo | Original `D2730B97` asset was never added to assets — circular logo used as fallback. |
| Testimonials font-size `1.25rem` | Default was too small — Cal flagged it, bumped up for readability. |
| Light/dark toggle added to nav | Dalena said site felt too dark — logo is light lavender, she's used to lighter colors. Toggle uses `data-theme="light"` on `<html>`, saved to localStorage. Light palette pulled from logo (soft lavender bg, deep purple accent). Moon ☽ / Sun ☀ icon swaps on click. |
| Display name is "Lavender Moon" not "Lavender x Moon" | She only used "Lavender x Moon" because lavenderxmoon.org was available — actual brand name is Lavender Moon. Updated in nav, footer, title, alt text. |
| GitHub pushes use Cal-Zentara account | AutoBuildCharlie doesn't have access to LavenderxMoon repo. Switch with `gh auth switch --user Cal-Zentara` before pushing. Do NOT switch back to AutoBuildCharlie after. |
| Intake form submissions go to Cal's email | Formspree free plan = 1 linked email. Cal forwards to Dalena manually or via Gmail auto-filter. |
| Domain stuck on Square Online | lavenderxmoon.org registered through Square — no direct DNS control. Transfer to Namecheap/Cloudflare to point to GitHub Pages. |
| Hero video cards updated to The Sun, The Star, The Moon | Original prompt used The Lovers, The Star, The World — Dalena flagged AI hallucination fake cards. Updated April 17. |
| Intake form CC via Formspree `_cc` field, not Gmail filter | Gmail filter requires recipient to click a verification email — Dalena never received it. `_cc` hidden field works immediately, zero setup. Use this pattern for all future client forms. |
| No satisfaction guarantee near Book button | Considered adding "not happy? Dalena will make it right" — removed because it plants doubt right before purchase. Trust is built earlier in the page (About/NDE story), not at the CTA. |
| LavenderMoon.com is taken | Owned by Kathy Randall since 1998, actively used, not for sale. Cal sent Dalena a list of alternatives April 19. Best bet: LavenderMoonTarot.com or TheLavenderMoon.com. Register on Cloudflare ($11-12/yr flat). |
| `--text-muted` bumped to `oklch(65% 0.025 295)` | Was `oklch(50%)` — failed WCAG AA contrast on all backgrounds (3.4:1 on --bg). Now passes at ~6.6:1. Light theme also adjusted to `oklch(38% 0.09 295)`. |

---

## Intake Form

| Item | Detail |
|---|---|
| File | `LavenderMoon/intake-form/index.html` |
| Live URL | https://lavendermoontarot.com/intake-form/ |
| GitHub repo | Cal-Zentara/LavenderxMoon (inside main site repo, not separate) |
| Formspree endpoint | `https://formspree.io/f/mgorkqvz` |
| Submissions go to | `cal.zentara@gmail.com` + CC `Dalenanch@gmail.com` via Formspree `_cc` hidden field |
| Built | April 17, 2026 — moved to main repo April 20, 2026 |

**Current flow (as of April 20, 2026):**
- All "Book a Session" buttons → `/intake-form/`
- Membership buttons → `/intake-form/?service=monthly` or `?service=weekly` (pre-checks the right option)
- Service selection: multi-select checkboxes (not dropdown) — clients can pick multiple services
- Birth details (DOB, time, city): conditional — only shown when Soul Blueprint or Astrology is selected
- Phone: optional
- **Regular sessions** → confirmation shows calendar button + membership upsell
- **Membership** → confirmation shows Square payment link (pay first), then note "Dalena will contact within 24hrs to book"
- **Live session payment** (PENDING) — no payment step yet for $44/$77/$111/$222 sessions. Need Square links + add pay-first flow same as memberships.

**Email delivery:** Formspree `_cc` hidden field — submissions go to cal.zentara@gmail.com AND Dalenanch@gmail.com automatically.

**Soul Blueprint timing note:** Dalena needs prep time before Blueprint sessions. Intake form arrives immediately on submission — she's aware, but may want a buffer built into booking (e.g. no same-day Blueprint bookings).

**Why separate form instead of Google Calendar intake:** Google Calendar intake questions require Google Workspace ($6/mo). This is free.

---

## Square Payment Links

| Item | Square Link |
|---|---|
| One Question Intuitive Tarot Reading (shop) | https://square.link/u/UG1toelh |
| Three Question Intuitive Tarot Reading (shop) | https://square.link/u/1RkwOVWl |
| Monthly Membership — $150/mo | https://square.link/u/SrOGfL4X |
| Weekly Membership — $500/mo | https://square.link/u/gM6WUXcC |
| Google Calendar booking | https://calendar.app.google/1MGnax6DEzcqBokH6 |
| Live session $44 | PENDING — need Cal to create in Square |
| Live session $77 | PENDING — need Cal to create in Square |
| Live session $111 | PENDING — need Cal to create in Square |
| Live session $222 | PENDING — need Cal to create in Square |

---

## Current Status

**v1.7 — Intake form moved to main domain, membership flow + service selector rebuilt.**

- Website: live at https://lavendermoontarot.com/
- Intake form: moved into main repo, now live at https://lavendermoontarot.com/intake-form/
- 10 service pages live and in sitemap
- Membership buttons pre-select service on intake form via URL param
- Service selector: multi-select checkboxes with Sessions / Memberships groups
- Birth details: conditional — only shows for Soul Blueprint / Astrology
- Membership flow: pay first (Square) → Dalena contacts to book
- Regular session payment: **NOT YET BUILT** — waiting on 4 Square links from Cal ($44/$77/$111/$222)
- Chat widget: still placeholder `<!-- REPLACE -->` in index.html

---

## Next Steps

- [x] ~~Google Search Console~~ — verified + sitemap submitted. 10 pages indexed.
- [x] ~~Service pages~~ — all 9 service pages live and indexed
- [x] ~~Domain~~ — lavendermoontarot.com live, DNS → GitHub Pages
- [x] ~~Membership tiers~~ — $150/mo and $500/mo Square links wired, intake form pre-selects membership
- [x] ~~Intake form~~ — moved to lavendermoontarot.com/intake-form/, multi-select services, conditional birth fields
- [ ] **Live session payment** — Cal needs to create 4 Square links ($44, $77, $111, $222), then add pay-first flow to confirmation screen (same as membership)
- [ ] Chat widget — decide on provider (Tidio, Crisp, etc.) → swap `<!-- REPLACE -->` in HTML
- [ ] Google Business Profile — send Dalena instructions to claim at business.google.com

### Future Offers to Pitch Dalena (not yet discussed)

**These are ideas — not committed work. Pitch only if she asks about growing traffic.**

- **ManyChat lead magnet system** (one-time setup, ~$300) — READY TO PITCH FRIDAY
  - Keyword: **MOON**
  - Notion doc (already built): https://www.notion.so/34b2117d14478107a79ce6d522716501
  - Dalena posts a reel ending with "comment MOON for my free guide"
  - ManyChat auto-DMs the commenter the Notion guide link
  - 23 hours later: automated follow-up DM → intake form (lavendermoontarot.com/intake-form/)
  - She only creates the reel — everything after the comment is automatic
  - ManyChat free plan covers this exact flow. No monthly cost.
  - **Comment replies (randomized):** "Check your DMs 🌙" / "Sent you something ✨" / "On its way to your DMs 🔮" / "Just sent it over 💜"
  - **First DM:** "Hey! Here's the free guide I mentioned — it'll help you get way more out of your reading before we even start. 👉 [Notion link] Read it when you get a chance. Talk soon 🌙"
  - **Second DM (23hrs later):** "Hope the guide was helpful! If you're curious and want to try a real reading, I do one-question sessions for $22.22 — full written response within 24 hours. 👉 https://lavendermoontarot.com/intake-form/ No pressure — just here if you're ready. 💜"
  - Dalena needs to: share the Notion doc publicly, connect ManyChat to Instagram, build the automation
  - **Reel ideas (all end with "comment MOON for my free guide"):**
    - "3 signs your tarot reading is going to hit different"
    - "What your first tarot card ever pulled says about you"
    - "Why I pulled The Tower for the third client in a row this week"
    - "The one question that changes every tarot reading"
    - "You don't need to believe in energy work for it to work — here's why"
    - "What I actually feel during a Reiki session"
    - "Signs someone who passed is trying to get your attention"
    - "What happens in the first 5 minutes of a mediumship session"
    - "POV: you came in skeptical and left crying in the best way"
    - "The most common thing people say after their first reading with me"
    - "Stop asking yes/no questions in readings — ask this instead"
    - "Why the cards don't just tell you what you want to hear"
- **Content orchestration system** ($300–500/mo retainer)
  - Dalena records a 20–30 min voice memo weekly (WhatsApp)
  - Cal runs it through a pipeline: transcribe → extract topics → generate blog posts in her voice → push to GitHub
  - 1 memo = 1 long blog post + 2–3 short posts + TikTok scripts
  - Goal: 20–50 indexed pages in her voice over 6 months. Drives national SEO.
- **Teach offer** ($150–250 one-time)
  - Show Dalena how to use Claude herself to generate content from her voice memos
  - Good if she wants to own the process, not outsource it
- **More service pages** (/reiki/, /channeling/, /spellwork/, /astrology-reading/, /oracle-reading/)
  - 5 more templates. Gets her to 10 service pages. Decent for local, limited for national.
  - Honest note: national SEO needs 30–50+ pages minimum. Pure service pages won't get her there alone — blog content + voice-driven orchestration would.
- [x] ~~Gmail filter~~ — fixed via Formspree `_cc` field. Submissions auto-forward to Dalena.
- [x] ~~/polish → /audit → /critique~~ — completed April 19. Score 15/20 → all P1/P2 issues resolved.
- [x] ~~Local SEO foundation~~ — meta tags, schema, robots.txt, sitemap live April 19
- [x] ~~Hero image~~ — new hero video `NewHero.mp4` deployed April 17
- [x] ~~Booking link~~ — Google Calendar link wired to intake form
- [x] ~~Shop product links~~ — both Square payment links live
- [x] ~~Intake form~~ — built and live at lavender-moon-intake

---

## Hero Video Prompt (KIE API — Seedance 1.0)

**Settings:** 16:9 · 720p · 10 sec · text-to-video · seamless loop

**Current prompt (approved April 17, 2026):**
> Extreme close-up of three tarot cards — The Sun, The Star, and The Moon — laid side by side on crushed black velvet, facing the viewer, upright and fully legible to the camera. Raw amethyst crystals and a small clear quartz cluster rest beside the cards, catching the dim candlelight. Warm amber candlelight at 2200K, very low and barely visible. Deep violet shadows dominate 95% of the frame. Cards emit only the faintest inner glow. No hands. Nothing moving. Static, brooding, sacred. Shot on 35mm film, heavy grain. Violet shadows, warm amber highlights, rich blacks. Dark, occult, luxury spiritual. Seamless loop. Cinematic. No text overlays.

---

## AI Influencer — Mira

**Status:** Paused April 21, 2026. Resume when Cal is ready.

Side project to drive traffic to Dalena's intake form + a $27 digital product (still to be built in Manus). Separate Instagram account under a fake persona named Mira Reyes — 31yo Mexican-American woman sharing her post-divorce spiritual awakening. Key rule: Mira is NEVER a reader. She's a seeker. Protects Dalena's real brand.

| Item | Detail |
|---|---|
| Folder | `LavenderMoon/ai-influencer/` |
| **Master plan** | **`ai-influencer/MASTER-PLAN.md` — READ THIS FIRST when resuming. Full context, every detail, every decision, step-by-step next actions.** |
| Persona doc | `ai-influencer/persona.md` (Mira's full backstory + 10 reel concepts) |
| Prompts | `ai-influencer/higgsfield-prompts.md` (canonical JSON + build order) |
| Reference images | Currently on Cal's desktop — `mira-canonical.png`, `mira-editorial.png`, `mira-before.png`, `mira-face-only.png` |
| Tool | Higgsfield Plus ($47/mo monthly, NOT annual — cancelable) |
| Funnel plan | Mira → Instagram → link in bio → Stan Store ($27 journal) OR Dalena's intake form |

**Progress:**
- [x] Persona locked (Mira Reyes — backstory, voice rules, 10 reel concepts written)
- [x] Higgsfield Plus subscription active
- [x] Canonical face locked + 2 environment variations (apartment morning, bedroom floor 3 AM)
- [ ] 7 remaining base images (Phase 1 continues)
- [ ] Video animation (Phase 2 — Kling 3.0)
- [ ] $27 journal built in Manus
- [ ] Stan Store live
- [ ] Instagram account created
- [ ] 10 reels batched + launch

**Open questions for Cal/Dalena:**
1. Revenue split — does Dalena get a cut when Mira's funnel sends her real clients, or is it a free traffic gift?
2. Need to tell Dalena about Mira before any funnel reel goes live (her brand reputation is at stake if this is ever traced back).
3. Handle pick — `@mirasmoondays` is current favorite but availability not verified.
