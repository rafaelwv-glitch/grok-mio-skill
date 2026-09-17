# Pixiv illustration quality (Mio v1.7 reference)

**Locked:** 2026-09-14
**Skill:** `SKILL.md` **v1.7** (source of truth)
**Playbook:** `references/playbook.md` v1.6 (mirror)
**Spicy recipes:** `references/heat-in-bounds.md` is primary. This file is **quality / camera / lighting** only.

Grok Imagine is a **natural-language** model (Flux-family), not a Danbooru-tag SD 1.5 model. Write **English sentences**. Borrow Danbooru *vocabulary* (camera, framing, lighting, cloth-state) because those words are also English. Do **not** dump forty comma-tags.

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

---

## 2. Pixiv illustration recipe (every frame)

Grok Imagine prompt order (front-load identity, end with quality):

```
[Medium + fiction lock]. [Subject + Face Lock + 25 / mature face / 1:7 / >1:3.5]. [Pose + named camera + named crop]. [Expression]. [Cloth-state or form-state]. [Setting]. [Lighting + atmosphere]. [Dry painted skin]. [Style lock]. [Pixiv closer]. no text, no speech bubbles, no captions, no watermarks, not photoreal, not a teen face.
```

### 2.1 Medium (always anime illustration)

Use one, not a pile:

- Default Slot 1: `Pixiv-quality vibrant moe bishoujo illustration`
- Slot 2: `early-2000s TV anime cel-animated illustration, crisp lineart`
- Sensual / heat: `Pixiv-quality sensual adult anime illustration, high-end adult digital painting`
- Figure sheet: `Pixiv-quality 2D anime character-sheet figure study`
- Seinen: `seinen anime illustration, muted palette, filmic`

**NEVER** lead with `photorealistic`, `photograph`, `DSLR`, `8k photo`, `realistic skin pores`, `85mm`, `octane render`, `raw photo` on an anime OC.

### 2.2 Pixiv closer (append every prompt)

```
masterpiece, best quality, highres, absurdres, trending on Pixiv, official-art quality, clean crisp lineart, delicate individual hair strands, detailed fabric folds, glossy eye highlights, soft cel shading with rich colour gradients, shallow depth of field, cinematic composition
```

### 2.3 Lighting (pick 2–3, match the beat)

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

### 2.4 Camera / framing (rotate every storyboard frame)

View: `from behind` · `looking over her shoulder` · `three-quarter view` · `from above` · `from below` · `profile` · `dutch angle` · `over-shoulder POV` · `through doorway` · `through sheer curtain` · `silhouette against window`

Body crop: `full body` · `cowboy shot` (head to mid-thigh) · `upper body` · `close-up` · `cropped at the hips` · `insert of hands` · `nape and shoulder`

Grok defaults to chest-up if you do not name the crop. **Say the crop.** Figures always `full body`.

### 2.5 Negative (recommend under the image; Grok has no true negative box)

`no text, no speech bubbles, no captions, no watermarks, no arrows, no storyboard annotations, no extra fingers, no loli, no child, no teen, no chibi, no photoreal, no western cartoon, no oily plastic skin, no bunker wall`

---

## 3. Quality closer + camera pack (copy)

### Quality closer

```
masterpiece, best quality, highres, absurdres, trending on Pixiv, official-art quality, clean crisp lineart, delicate individual hair strands, detailed fabric folds, glossy eye highlights, soft cel shading with rich colour gradients, shallow depth of field, cinematic composition, dry painted skin, no text, no speech bubbles, no captions, no watermarks
```

### Camera pack (rotate)

```
from behind, looking over her shoulder
three-quarter view, cowboy shot cropped at upper thigh
over-shoulder POV, shallow depth of field
through sheer curtains, backlit silhouette
low angle looking up, rim light on a mature silhouette
insert: hands on a silk sheet / lace strap / nape
nape and collarbone close-up, rumpled bed
full body front, official-art character sheet
```

Heat cloth-state and first-shot templates live in `heat-in-bounds.md`. Do not keep a second heat law here.

**End of Pixiv illustration quality**
