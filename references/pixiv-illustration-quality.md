# Pixiv illustration quality (Mio v1.8 reference)

**Locked:** 2026-09-21
**Skill:** `skills/anime-oc-mio/SKILL.md` **v1.8** (source of truth)
**Playbook:** `references/playbook.md` v1.8 (mirror)
**Spicy recipes:** `references/heat-in-bounds.md` is primary. This file is **quality / camera / lighting / dynamic pose packs** + Slot-3 style descriptors.

Grok Imagine is a **natural-language** model (Flux-family), not a Danbooru-tag SD 1.5 model. Write **English sentences**. Borrow Danbooru *vocabulary* (camera, framing, lighting, cloth-state) because those words are also English. Do **not** dump forty comma-tags. Do **not** depend on `artist:` LoRA tags.

Adult OCs only. 25. 1:7. >1:3.5. Never real people. Never anyone who could read underage.

---

## 1. Why Pixiv-quality frames fail

Most failed Mio frames are not "the model is bad". They are:

1. **Photoreal mixed into anime** — Grok then renders skin like a camera, which both tanks the Pixiv look *and* trips NSFW harder. Anime/stylized/fantasy is the high-pass lane; photoreal nudes are the low-pass lane.
2. **No lighting, no named crop, no fabric.** A body floating on white is amateur and easy to moderate. Imagine defaults chest-up if crop is unsaid.
3. **Heat beats skipped, fully clothed, or pre-sanitized** after one censor. The storyboard then lies.
4. **Absence / act vocabulary** as the subject (`nude photograph of…`, `no clothes`, genital nouns, sex-act verbs) instead of **illustration + camera + cloth-state + presence**.
5. **OC names in the prompt** — model associates them with other characters and drifts the face.
6. **Oily plastic skin** — reads as photoreal-adjacent cheap porn, not as illustration.
7. **Teen-face under heat** — spicy frames regress to neotenous faces unless mature-face tokens are repeated.
8. **Static mannequin poses** — arms-at-sides / facing-camera / identical pose across beats kills liveliness (v1.8 Dynamic Pose Law).
9. **Raw artist-tag dumps** — `artist: stuart_pot` is a false-positive; Grok Imagine prefers descriptive NL recipes.

---

## 2. Pixiv illustration recipe (every frame)

Grok Imagine prompt order (front-load identity, end with quality):

```
[Medium + fiction lock]. [Subject + Face Lock + 25 / mature face / 1:7 / >1:3.5]. [Dynamic pose + named camera + named crop]. [Expression]. [Cloth-state or form-state]. [Setting]. [Lighting + atmosphere]. [Soft-looking painted skin]. [Style lock]. [Pixiv closer]. no text, no speech bubbles, no captions, no watermarks, not photoreal, not a teen face.
```

### 2.1 Medium (always anime illustration)

Use one, not a pile:

- Default Slot 1: `Pixiv-quality vibrant moe bishoujo illustration`
- Slot 2: `early-2000s TV anime cel-animated illustration, crisp lineart`
- Sensual / heat / Slot 3: `Pixiv-quality sensual adult anime illustration, clean delicate linework, soft painterly shading, semi-realistic anime that stays 2D`
- Figure sheet: `Pixiv-quality 2D anime character-sheet figure study`
- Seinen: `seinen anime illustration, muted palette, filmic`

**NEVER** lead with `photorealistic`, `photograph`, `DSLR`, `8k photo`, `realistic skin pores`, `85mm`, `octane render`, `raw photo` on an anime OC.

### 2.2 Pottsness-inspired style block (Slot 3 / sensual lock — descriptors only)

Research note 2026-09-21: pottsness is a real Pixiv illustrator (ID 59336265). Style traits used as **inspiration descriptors** for NL prompts (not as copy instructions, not as required LoRA tags): clean/delicate + fluid-sharp lineart; soft luminous palette; glossy eyes + dense eyelashes; soft-looking painted skin; semi-realistic anime that stays illustration; vivid saturated colour; lively character design.

User style intent as **English sentences** for Grok Imagine:

```
clean delicate linework, fluid and sharp lineart, soft painterly shading with airbrushed skin gradients, glossy illustrated skin highlights (not photo pores), vivid saturated colours, glossy eyes, dense eyelashes, luminous soft palette, soft-looking painted skin, semi-realistic anime illustration that stays 2D (not photoreal)
```

**`stuart_pot` excluded:** web search (2026-09-21) does not verify `stuart_pot` as a Pixiv/Danbooru alias of pottsness; hits map to Gorillaz “Stuart Pot/2-D”. Do not put `artist: stuart_pot` in prompts. Do not claim it is pottsness. Prefer the descriptive recipe above. Optional speech: “pottsness-inspired look” — prompt stays descriptor-based. Never instruct copy/train-on of copyrighted works.

### 2.3 Pixiv closer (append every prompt) — v1.8 upgrade

```
masterpiece, best quality, highres, absurdres, trending on Pixiv, official-art quality, clean delicate linework, fluid sharp lineart, soft painterly shading with airbrushed colour gradients, glossy illustrated skin highlights, vivid saturated colours, delicate individual hair strands, detailed fabric folds, glossy eyes, dense eyelashes, luminous soft palette, shallow depth of field, cinematic composition
```

Still **no photoreal pores**. Skin gloss is illustrated, not camera SSS.

These tokens pull toward **high-end Pixiv illustration** rather than generic "AI anime girl". `absurdres` / `highres` are Pixiv meta; `official-art quality` and `trending on Pixiv` are aesthetic magnets.

### 2.4 Lighting (pick 2–3, match the beat)

| Mood | Say this |
|---|---|
| Soft / morning | `soft morning window light, warm bounce fill, gentle skin highlights` |
| Intimate / bedroom | `warm lamp glow, candlelit rim, volumetric dusk in the corners` |
| Dramatic | `dramatic rim light, chiaroscuro, hair-backlight halo` |
| Night | `moonlight through sheer curtains, cool rim, warm interior practicals` |
| Wet / bath | `steamy bathroom light, specular highlights on painted skin and tile, soft fog` |
| Golden | `golden hour backlight, rim on hair and shoulders, shallow depth of field` |
| Neon / night city | `neon rim in magenta and teal, wet-street bounce` |
| Figure studio | `even studio lighting, soft fill, no harsh flash, plain grey cyclorama` |

Danbooru-useful English: `rim lighting`, `backlighting`, `sidelighting`, `underlighting`, `volumetric light`, `depth of field`. Use `bokeh` only as illustrated depth, never as a photography token stacked with DSLR.

### 2.5 Camera / framing (rotate every storyboard frame)

View: `from behind` · `looking over her shoulder` · `three-quarter view` · `from above` · `from below` · `profile` · `dutch angle` · `over-shoulder POV` · `through doorway` · `through sheer curtain` · `silhouette against window` · `push in` · `low angle looking up`

Body crop: `full body` · `cowboy shot` (head to mid-thigh) · `upper body` · `close-up` · `cropped at the hips` · `insert of hands` · `nape and shoulder`

Grok defaults to chest-up if you do not name the crop. **Say the crop.** Figures always `full body`.

### 2.6 Dynamic pose pack (v1.8 — rotate; English sentences)

Every storyboard frame needs: (a) action / mid-action, (b) weight / asymmetry / foreshortening, (c) secondary motion. Figure sheet exempt (front, arms at sides).

```
mid-stride walk toward camera, weight on the front foot, coat hem trailing
three-quarter turn looking back over the shoulder, hair swinging with the turn
reaching upward, foreshortened arm toward camera
leaning into a doorframe, hip cocked, ankle crossed
sit-to-stand from the bed edge, weight shifting forward
wind-blown coat and hair, one hand pinning the lapel
kneeling then rising, fabric pooling, upward glance
mid-spin pause, skirt flared, arms asymmetric, dutch angle
crouch-to-sprint start, weight on the balls of the feet
sitting sideways on a windowsill, one leg drawn up
pulling a sheet across the body mid-motion, weight on one hip
walking past in profile, mid-step, glance toward the lens
brushing hair aside while turning, secondary cloth motion
stepping down stairs, foreshortened descending foot, hand on the rail
```

Look slots: calmer life (contrapposto, glance, soft step) — not mannequin-stiff.

### 2.7 Negative (recommend under the image; Grok has no true negative box)

`no text, no speech bubbles, no captions, no watermarks, no arrows, no storyboard annotations, no extra fingers, no loli, no child, no teen, no chibi, no photoreal, no western cartoon, no oily plastic skin, no bunker wall, no static T-pose, no arms-at-sides mannequin (except figure sheet)`

---

## 3. Quality closer + camera pack (copy)

### Quality closer (v1.8)

```
masterpiece, best quality, highres, absurdres, trending on Pixiv, official-art quality, clean delicate linework, fluid sharp lineart, soft painterly shading with airbrushed colour gradients, glossy illustrated skin highlights, vivid saturated colours, delicate individual hair strands, detailed fabric folds, glossy eyes, dense eyelashes, luminous soft palette, shallow depth of field, cinematic composition, soft-looking painted skin, no text, no speech bubbles, no captions, no watermarks
```

### Camera pack (rotate)

```
from behind, looking over her shoulder, hair swinging
three-quarter view, cowboy shot cropped at upper thigh, weight on one hip
over-shoulder POV, shallow depth of field, mid-turn
through sheer curtains, backlit silhouette
low angle looking up, push in, rim light on a mature silhouette
dutch angle mid-spin, coat flared
insert: hands on a silk sheet / lace strap / nape
nape and collarbone close-up, rumpled bed, weight shift
full body front, official-art character sheet (Figure only — arms at sides OK)
walking toward camera mid-step, full body, feet in frame
```

Heat cloth-state and first-shot templates live in `heat-in-bounds.md`. Dynamic Pose Law lives in `SKILL.md`. Do not keep a second heat law here.

**Sources (2026-09-21):** pottsness Pixiv ID 59336265 / public style notes (~600k X followers); PixAI LoRA trigger vocabulary (Glossy eyes, Dense Eyelashes, Soft-looking skin, Semi-Realistic, Fluid and Sharp Lineart, Luminous Quality, Soft Palette) used as *descriptor seeds* only; user style string translated to English sentences; stuart_pot false-positive clarification; dynamic pose prompting research (motion verbs, foreshortening, weight shift, secondary motion, camera verbs). No invented artists. No jailbreak material.

**End of Pixiv illustration quality**
