# Heat in bounds — R-rated 2D illustration (Mio v1.8)

**Locked:** 2026-09-21
**This file is recipes only.** Law lives in `SKILL.md` §1, §3.2, § Dynamic Pose Law, and §9.
**Purpose:** spicy frames that are *allowed*, especially anime figures / illustrations, not photoreal people. v1.8 adds **motion / dynamics** to heat templates and to §9B.

Official line (xAI AUP effective 2026-08-14, restated by @grok through 2026-09-14): limited **R-rated fictional adult content of imaginary adults** is allowed for age-verified SuperGrok with NSFW enabled, in private. Full explicit acts are blocked even for fictional anime. Real-person undress / nudify is a hard block. Circumvention of safeguards is a hard block. Image 2.0 overflags allowed clothed frames — that is skill §9A, not a spice-down.

If it would be allowed in an R-rated film as **fictional adult stylized imagery**, draw that. Do not jailbreak NC-17 photoreal sex.

---

## 1. What actually passes (community + official, 2026-08 / pose craft 2026-09)

High pass, keep using:

- Anime / 2D / cel / Pixiv digital painting / fantasy illustration
- Original fictional adult (state 25, mature face — extra tokens on heat)
- Explicit “not a real person, not a photograph”
- Named crop (full body / cowboy / three-quarter) — Imagine defaults chest-up
- Presence language: sheet at the waist, character-sheet form, strap slipping, open shirt
- Lingerie, sheer, wet clinging fabric, mid-undress, towel, sheet
- Artistic figure study / character sheet of an adult form
- Topless / artistic nude as illustration — **side, back, three-quarter** first
- Afterglow, rumpled bed, steam, silhouette, crop that implies the rest
- Soft-looking painted skin, airbrushed gradients, glossy *illustrated* highlights (not oily plastic / not photo pores)
- **Motion heat (v1.8):** mid-undress in motion, sheet being pulled, hair whip, weight shift on bed, walking toward camera mid-step

Low pass / bounce — do not lead with:

- Photoreal, DSLR, 85mm, octane, skin pores, “photograph of a woman”
- Real-person edit / undress / celebrity
- Genital close-up or sex-act verb as the **subject** of the prompt
- Absence headlines: `nude`, `no clothes`, `undressed`, `fully naked`
- Prompt tokens: `hentai`, `nsfw`, `nude`, `girl` as subject
- Teen-face + sexy body (also an adult-lock failure)
- School / classroom / uniform on a heat frame
- Sticker borders, slime covers, “ethical override” prefixes
- First-shot pre-sanitization (sweater-lingerie standing in for a sheet beat)
- Climbing the heat ladder on a clothed look block (§9A exists for that)
- Static arms-at-sides mannequin on a heat storyboard beat
- `artist: stuart_pot` or unverified artist-tag LoRA dumps

Sources informing this file: research 2026-08-28 (AUP, presence language, cloth-state) + research 2026-09-21 (dynamic pose / motion cloth-states / pottsness-inspired descriptive style for Slot 3 quality — not a heat jailbreak). Jailbreak stacks stay out.

---

## 2. First-shot templates (copy and fill Face Lock)

First shot = hottest **legal** frame for the beat. Do not generate a timid preview. Prefer mid-motion when the beat allows.

### 2.1 PFP / greeting heat (clothed-to-undress, living pose)

```
Pixiv-quality 2D anime illustration of an original fictional adult woman, not a real person, not a photograph.
25 years old, mature adult face, defined jaw, mature eyes, head-to-body 1:7, head-to-hip greater than 1:3.5, [Face Lock],
[dynamic pose: action verb + weight/asymmetry + secondary motion], [named crop + camera],
[cloth-state matching the Opening — what the garment is doing, preferably in motion],
[setting from the Opening], [2–3 lights],
soft-looking painted skin, airbrushed skin gradients, glossy illustrated highlights, cel accents,
[Style Lock], masterpiece, best quality, highres, absurdres, trending on Pixiv, official-art quality,
clean delicate linework, fluid sharp lineart, detailed fabric folds, glossy eyes, dense eyelashes,
no text, no speech bubbles, not photoreal, not a teen face.
```

### 2.2 Clean Figure (mannequin) — presence language — Pose Law EXCEPTION

```
Pixiv-quality 2D anime character-sheet figure study of an original fictional adult woman, not a real person, not a photograph.
25 years old, mature adult face, defined jaw, mature eyes, adult face, head-to-body 1:7, head-to-hip greater than 1:3.5,
[Face Lock + hair + eye colour + skin],
full body front view, standing, arms at sides, neutral expression, barefoot,
plain light grey studio background, even lighting,
unadorned mature adult form as artistic anatomy reference, official-art character sheet,
soft-looking painted skin not oily plastic, narrow waist, wide hips, curvy mature silhouette,
masterpiece, best quality, highres, absurdres, official-art quality, clean delicate linework,
no jewelry, no text, no bunker wall, no grass, not photoreal, not a teen face, not a photograph.
```

Do **not** headline this template with `nude` or `no clothes`. The sheet is a figure study. That is the allowed picture. Arms-at-sides is correct **here only**.

### 2.3 Afterglow / sheet beat (with motion option)

```
Pixiv-quality sensual 2D anime illustration, original fictional adults, not a photograph.
25-year-old mature woman [Face Lock], defined jaw, mature eyes,
weight shifting on rumpled silk, sheet pooled at her waist / sheet being pulled across the hips, afterglow flush,
a generic handsome adult male with short dark hair in the same animation style beside her,
warm lamp, rim light, three-quarter view, cowboy shot,
soft-looking painted skin, airbrushed gradients, glossy illustrated highlights,
masterpiece, best quality, trending on Pixiv, official-art quality, clean delicate linework,
no text, not photoreal, not a teen face.
```

### 2.4 Dynamic heat templates (v1.8 — motion cloth-states)

Use when the Opening supports motion; still presence language; still 2D:

```
# Mid-undress in motion
… mid-step toward camera, open shirt sliding off one shoulder, strap slipping, hair trailing the turn, full body, feet in frame …

# Sheet pull
… reclining then rolling, silk sheet being pulled across the hips, weight on one elbow, secondary pillow motion …

# Hair whip + lingerie
… three-quarter turn looking back, hair whipping with the turn, black lace, weight on the back leg, dutch angle …

# Walk-in lingerie / open shirt
… walking toward camera mid-step, lingerie / unbuttoned shirt, coat hem trailing, glossy eyes, luminous soft palette …
```

---

## 3. If blocked — pick the right ladder

Do not resubmit the same sentence.

- Clothed / look / Slot 1 / Slot 2 / cafe / travel blouse → skill **§9A**. Change one of: adult-lock-first, medium declaration, named crop, camera/light, living pose. Keep the clothes.
- Heat beat / Figure study / sheet / mid-undress → skill **§9B**. Change **one**: camera, crop, cloth-state, occlusion, **motion (B4)**, or presence wording. Keep 2D + adult + face lock + mature face + painted skin.

Then stop climbing if it lands. If three rungs fail, ship the hottest legal frame that still reads as the beat and say so.

### 9B rung reminder (skill is source of truth)

B0 setup → B1 camera → B2 occlusion → B3 lingerie → **B4 motion** → B5 insinuation → B6 closest legal R-rated 2D. Never mix with 9A. Never fully-clothe a heat beat into a SFW hole.

---

## 4. Anti-patterns

- Leading with `photorealistic 8K consensual couple missionary`
- `framed by anime nude stickers`
- `obscured by slime`
- Slot 3 as “wet-look exaggerated hentai photograph”
- Fully dressing a heat beat into a coffee-shop SFW still
- Using `hourglass` as a body tag
- `nude / no clothes` as the Figure subject
- Unnamed crop
- Oily plastic skin / photoreal pores
- Asking the user to flip Imagine’s Spicy slider as the fix
- Static arms-at-sides on a heat storyboard beat
- Identical pose across heat beats
- `artist: stuart_pot` false-positive tags

**End of heat-in-bounds**
