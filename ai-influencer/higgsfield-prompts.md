# Higgsfield Image Prompts — Mira Reyes

This file has the **canonical reference prompt** that locks Mira's face forever. Every future image and video of Mira must reference the best output from this first batch.

---

## Settings (set these BEFORE pasting the prompt)

| Setting | Value |
|---|---|
| Tool | Higgsfield → Image → **Nano Banana Pro** |
| Aspect ratio | **9:16 (vertical)** — Instagram Reels format |
| Quality | **4K** |
| Batch size | **4** (gives you 4 variations to pick the best face) |

---

## The Canonical Prompt (copy/paste this exactly)

Paste this as JSON into Higgsfield's prompt box:

```json
{
  "subject": "31-year-old Mexican-American woman named Mira. Medium-deep olive skin with warm undertones and visible natural skin texture including light freckles across the nose bridge. Long dark brown wavy hair parted in the middle, slightly undone, falling past her shoulders. Dark brown eyes with a faint amber ring around the iris. Soft heart-shaped face. Subtle beauty mark on the right side of her jawline, one inch below her earlobe. Full lips, slight natural gap between front teeth when mouth is relaxed. Left eyebrow slightly higher than right. Minimal makeup — just a touch of mascara and tinted lip balm. No filter look. No AI smoothness. Wearing a simple oversized cream linen button-up shirt, top two buttons undone, collar slightly wrinkled.",
  "environment": "Inside a small sun-drenched Long Beach studio apartment. Warm white walls with a soft shadow pattern from nearby window blinds. A small monstera plant slightly out of focus in the background. Late morning natural light filtering through a sheer linen curtain on the left side of the frame. A wooden shelf with a few stacked books and a brass candle holder visible but blurred.",
  "style": "Editorial portrait photography. Shot on 35mm film, Kodak Portra 400. Natural film grain visible. Muted warm color palette — cream, beige, soft brown, faded terracotta. Slight chromatic softness around the edges. No HDR, no saturation boost, no digital sharpening. The image should feel like it was scanned from a film negative.",
  "mood": "Quiet, reflective, grounded. Not smiling, not sad — neutral present. Looking slightly off-camera to the right, like she just caught herself thinking about something. Calm but not posed.",
  "camera": "Medium close-up framing, chest up. Eye-level angle, slightly off-center so her face is positioned on the left third of the frame. Shallow depth of field (f/2.0 feel). No tilt, no fisheye, no dramatic perspective. Natural window light is the only light source — soft, directional from frame-left."
}
```

---

## What to Do When You Get the 4 Images Back

1. **Pick the best one.** Look for: realistic skin texture, no "AI mannequin" plastic look, believable eyes (AI often gets eyes wrong first try), and the face matches the description above.
2. **Save it as `mira-canonical.png`** inside `LavenderMoon/ai-influencer/reference-images/` — this is now the master reference.
3. **Screenshot her face and save as `mira-face-only.png`** — cropped tight, just the head and shoulders. This is what you'll feed into every future generation as a "character reference" to keep consistency.
4. **If none of the 4 look right:** don't edit the prompt yet. Just click Generate again for another batch of 4. Nano Banana Pro gets closer each time you re-roll.

---

## How to Generate the Next 9 Images (Once Canonical Is Locked)

Once you pick the best Mira, you'll need 9 more images for variety in her feed. Use this pattern:

1. Open Higgsfield → Nano Banana Pro
2. **Upload `mira-face-only.png` as a character reference** (this is how you lock her face across all generations)
3. Paste the same JSON prompt but change only the `environment`, `mood`, and `camera` fields
4. Keep the `subject` field IDENTICAL every time — this is the glue

---

## 3 Environment Variations Ready to Test

### Variation A — Bedroom floor at 3 AM (for Reel 4 "rock bottom") ✅ USED

**Lesson learned:** The original "kitchen at 2 AM with wine glass + tissues" prompt came back looking staged and AI-generated — too cinematic, too movie-set. Swapped to the bedroom floor version below. Strip theatrical props, get closer, softer light. This one worked.

Full JSON (replace entire prompt):

```json
{
  "subject": "31-year-old Mexican-American woman named Mira. Medium-deep olive skin with warm undertones and visible natural skin texture including light freckles across the nose bridge. Long dark brown wavy hair parted in the middle, slightly undone, falling past her shoulders. Dark brown eyes with a faint amber ring around the iris. Soft heart-shaped face. Subtle beauty mark on the right side of her jawline, one inch below her earlobe. Full lips, slight natural gap between front teeth when mouth is relaxed. Left eyebrow slightly higher than right. No makeup. Eyes slightly puffy and red from crying earlier, not currently crying. Wearing an old oversized grey hoodie.",
  "environment": "Sitting on the floor of a dim apartment bedroom, back against the bed frame. 3 AM. The only light is a warm bedside lamp barely visible to the right. Phone face-down on the floor beside her. No props. No staging. Just her and the floor.",
  "style": "Shot on 35mm film, Kodak Portra 400. Heavy grain. Very low light, underexposed slightly. Muted — dark greys, muted skin tones, no warmth. Feels like a photo someone accidentally took, not one that was composed.",
  "mood": "Empty, not sad. Past the point of crying. Just sitting there because she doesn't know what else to do. Eyes open, not looking at anything. She forgot the camera was there.",
  "camera": "Medium close-up, chest up. Slightly low angle, like the camera is sitting on the floor with her. Slightly off-center. No dramatic framing — just honest."
}
```

### Variation B — Golden hour on her patio (for Reel 1 "after" state)

```json
"environment": "Small apartment patio at golden hour. Warm amber sunlight hitting her face from the right. A single white candle and a tarot deck on a small wooden side table. Distant palm tree silhouettes, blurred ocean haze in the deep background (Long Beach).",
"mood": "Quietly confident. Small closed-lip smile, shoulders down, breathing slow. Holding a single tarot card (The Star) casually in her left hand, not staged. She looks grounded, not ecstatic.",
"camera": "Three-quarter angle, chest up, golden hour backlight creating a soft halo around her hair. Lens flare barely visible. Shot on film."
```

### Variation C — Journaling at the kitchen table (for Reel 7 "shadow work")

```json
"environment": "Same kitchen from variation A, but daytime. Soft overcast light through the window. A linen-bound journal open on the table, pen resting in the crease of the pages. A mug of tea steaming beside it. One page of handwriting visible but not legible.",
"mood": "Mid-cry but not sobbing. One tear has fallen onto the page. Head slightly bowed, hand resting on her forehead. She's processing, not performing.",
"camera": "Overhead 45-degree angle, capturing her hand on her forehead and the open journal in the same frame. Natural soft light. Shot on film."
```

---

## Consistency Rules (critical — read before every session)

1. **Never change the `subject` field.** Not one word. The beauty mark, the amber eye ring, the eyebrow asymmetry — these are the anchors that keep her face consistent across 100+ images.
2. **Always upload `mira-face-only.png` as a character reference** when generating. This is the #1 thing that prevents "different person every post."
3. **Keep the style consistent.** Kodak Portra 400, 35mm film, muted warm palette. If you switch to "cinematic HDR" or "vibrant editorial," she'll stop looking like the same person aesthetically even if her face matches.
4. **Re-roll, don't re-prompt.** If a batch looks off, hit Generate again with the same prompt before tweaking anything. Nano Banana Pro varies its output — sometimes batch #3 nails it when batch #1 didn't.

---

## Build Order (proper way — images first, video second)

Video eats ~10x more credits than images. Generate every still image first, then animate only the winners. Otherwise you burn through the $47 plan in 3 days on bad videos from weak source images.

### Phase 1 — Image Library (current phase)
Build all 10 still images BEFORE touching video:

- [x] `mira-canonical.png` — Reel payoff/base (grounded, apartment, morning light) ✅ April 21, 2026
- [x] `mira-editorial.png` — secondary reference (same shoot, editorial mood) ✅ April 21, 2026
- [x] `mira-before.png` — Reel 4 "rock bottom" (bedroom floor, 3 AM, grey hoodie) ✅ April 21, 2026
- [ ] `mira-golden-hour.png` — Reel 1 payoff (patio, tarot card, confident)
- [ ] `mira-journaling.png` — Reel 7 (shadow work at kitchen table)
- [ ] `mira-morning-routine.png` — Reel 6 (water glass, window light)
- [ ] `mira-tarot-deck.png` — Reel 5 (unwrapping deck, confused face)
- [ ] `mira-on-couch.png` — Reel 2 (casual thinking pose)
- [ ] `mira-outside-walking.png` — Reel 3 (wide b-roll shot)
- [ ] `mira-looking-at-phone.png` — Reel 8 (vulnerable moment)
- [ ] `mira-zoom-call.png` — Reel 9 (after-Dalena-reading — funnel)

### Phase 2 — Video Animation (next)
Upload each still as start frame in Higgsfield Video → Kling 3.0. Simple motion prompt (e.g., "She takes a slow breath and looks down"). 3-5 sec clips, static camera. 10 reels × 2 clips = ~20 video clips.

### Phase 3 — Edit + Assemble
CapCut (free). Import clips, viral audio, hook text, payoff text. 10 finished reels.

### Phase 4 — Launch
Stan Store live with $27 journal. Instagram account live. Upload all 10 as drafts. Post 2-3/day with AI label toggled ON every time.

---

## When Resuming — Do This Next

1. Open Higgsfield → Image → Nano Banana Pro
2. Settings: 9:16, 4K, batch of 4
3. **Upload `mira-face-only.png` as character reference** (the + button in the prompt box)
4. Paste **Variation B** (golden hour on patio) from above
5. Generate → pick the best → save as `mira-golden-hour.png`
6. Continue down the Phase 1 checklist until all 10 are locked
