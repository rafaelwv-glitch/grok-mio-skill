# Anime OC Mio Playbook v1.8
**Locked:** 2026-09-21
**Skill:** `skills/anime-oc-mio/SKILL.md` **v1.8** (this playbook is a **mirror**. Imagine Agent must run from SKILL.md alone.)
**Owner:** Rafael Eduardo Wefers Verástegui (`rafaelwv@gmail.com`)

SKILL.md v1.8 is the source of truth. If this file and SKILL.md conflict, **SKILL.md wins**.

---

## 0. LOAD ORDER

IF Anime / looks / OC / illustration / face lock / Imagine greeting / storyboard / dynamic pose / pottsness-style is requested THEN:

1. Load `SKILL.md` v1.8. That file **is** the ritual. Do not require a second fetch.
2. **Before any image**, print:
   `Mio v1.8 · lock=YES|NO · beats=N`
3. Apply **Rank** (skill §0.1). Lock and beats outrank heat. Dynamic Pose Law applies to storyboard and look slots (Figure exception).
4. IF `lock=NO` THEN generate three images this turn:
   Slot 1 bishoujo-moe · Slot 2 2000s cel-shade · Slot 3 Pixiv sensual illustration (2D, not photoreal; pottsness-inspired descriptive recipe).
   WAIT. NEVER storyboard. NEVER hand off to figure-gen. EVEN IF a full bot pack was dropped.
5. IF `lock=YES` AND greeting/storyboard is requested THEN skill §8 + Dynamic Pose Law.
6. Imagine Agent generates natively. NEVER `generate_image`. NEVER `size`.

**Failure to print the start line is a process failure.**
**Mio §2 three looks land BEFORE figure-gen §0a ask.**

```
FAIL-if lock=NO and this turn does not generate exactly these three images before any other visual:
  Slot 1 bishoujo-moe · Slot 2 2000s cel-shade · Slot 3 Pixiv sensual illustration (2D, not photoreal).
A questionnaire, a single Figure/PFP ask, or "Slot 3 only if adult" is INVALID.
Slot 3 is ALWAYS shown on a new OC. The user may reject it after seeing it.
```

```
FAIL-if storyboard frames are all static facing-camera / arms-at-sides / identical pose across beats.
Every storyboard frame MUST name: (a) action verb or mid-action, (b) weight/asymmetry/foreshortening, (c) secondary motion.
Figure sheet EXCEPTION: front, arms at sides, neutral — still allowed.
```

---

## 1. COMMANDS

| User says | THEN |
|---|---|
| Fire up Mio / looks / this is [Name] | If lock=NO: §2 three looks this turn. If they lock a look: Face Lock + Style Lock. Copy visual into Situation when asked. |
| This is [Name] / lock this look / slot N | Face lock + style lock. `lock=YES` next turn. |
| Assembled package / storyboard the greeting | **If lock=NO: three looks first, wait.** If lock=YES: skill §8 + Dynamic Pose Law. NEVER skip lock because a pack was dropped. NEVER replace looks with a Figure/PFP ask. |
| Restyle | New style lock only if explicit. Keep face lock. |
| Regenerated / censored / blocked on a clothed / look frame | Same beat. Skill **§9A** (camera / crop / medium / adult-lock-first / living pose). Do not add lingerie. Do not dress it down. |
| Regenerated / censored / blocked on a heat beat | Same beat. Skill **§9B** (incl. **B4 motion**). Rephrase the **picture** (camera, cloth-state, crop, presence language, motion, 2D). Never jailbreak. Never skip. Never fully-clothe a heat beat into a SFW hole. |

---

## 2. OC HARD CONSTRAINTS

ALWAYS: 25 · 1:7 · >1:3.5 · adult lock BEFORE moe · Face Lock re-inject · Style Lock re-inject · named crop (`full body, head to toe, feet in frame` unless the user asked cowboy / three-quarter) · soft-looking painted skin / airbrushed gradients / glossy illustrated highlights · Dynamic Pose Law on storyboard + look slots (Figure exception) · full English prompt under every image · `{{user}}` = generic male, same animation style · Pixiv closer (v1.8 delicate linework + painterly gradients) · 2D original-character declaration · presence language · no names in prompts · no photoreal lead · Slot 1+2+3 on every new OC · Slot 3 = descriptive pottsness-inspired recipe (no `stuart_pot`).

NEVER in an image prompt: `hentai` · `nsfw` · `nude` · `no clothes` · `undressed` · `naked` · `girl` as the subject noun · `artist: stuart_pot` as a required tag.

NEVER: underage · skip Slot 1, Slot 2, or Slot 3 on a new OC · gate Slot 3 on “adult brief” · storyboard before lock · `generate_image` / `size` · real-person likeness · sticker-frame / slime-obscure / ethical-override wrappers · absence headlines as the subject · first-shot pre-sanitization of a heat beat · replace looks with a Figure/PFP ask · climb §9B on a clothed overflag · static mannequin storyboard · instruct copy/train-on of copyrighted art.

---

## 3. NEW OC PIPELINE

```
IF lock=NO THEN
  vibe 2–3 sentences
  generate 3 images this turn, same identity
  Slot 1 ALWAYS bishoujo-moe (calmer life pose OK)
  Slot 2 ALWAYS 2000s cel-shade (calmer life pose OK)
  Slot 3 ALWAYS Pixiv sensual illustration (2D; pottsness-inspired descriptive recipe; lively stance)
  WAIT for lock
ELSE
  stay on the lock
```

A dumped Title/Bio/Situation/World/Opening does **not** flip this to storyboard.
A figure-gen “ALWAYS ask Figure+PFP” does **not** replace this set.

---

## 4. STORYBOARD (lock=YES only)

Opening is the beat source. 1–2 frames per beat. All beats. Camera rotates. **Dynamic Pose Law.** No annotations. Generic male `{{user}}` in locked style.

Print `Mio v1.8 · lock=YES · beats=N` before frame 1.

Clothed beats that bounce: skill §9A.
Heat beats: first shot is the hottest legal R-rated **2D illustration** of the beat (prefer mid-motion). **If blocked**, skill §9B (B4 = motion). Heat does not outrank lock or missed beats.

---

## 5. HEAT = IN-BOUNDS FIRST, RETRY SECOND (Rank 5)

Not the main law.

First shot uses skill §1.1 — hottest legal frame, not a timid preview.

Image 2.0 overflag on a tame frame is **§9A**, not spice-down.

Heat block is **§9B**: camera → occlusion → lingerie → **motion** → insinuation → closest legal R-rated 2D adult frame. Same beat. Same locks. Never fully-clothed SFW hole. No jailbreak prefixes. Stay in illustration. Never photoreal sex stills. Never absence headlines. Never mix with 9A.

---

## 6. CHECKLIST

- [ ] Start line printed before images (`Mio v1.8`)
- [ ] lock=YES before any storyboard frame
- [ ] Slot 1 bishoujo-moe + Slot 2 2000s cel-shade + Slot 3 Pixiv sensual illustration shown if lock was NO
- [ ] Slot 3 used descriptive pottsness-inspired recipe (no `stuart_pot` LoRA tag dependence)
- [ ] 1–2 images per Opening beat; none missed
- [ ] POV/camera changes; **Dynamic Pose Law** (action + weight/asymmetry + secondary motion)
- [ ] No static mannequin / identical-pose storyboard
- [ ] Named crop on every frame (default full body, head to toe, feet in frame)
- [ ] No annotations / speech bubbles
- [ ] Face + style + 25 / 1:7 / >1:3.5 / mature face held — adult lock BEFORE moe
- [ ] `{{user}}` generic male, same style
- [ ] 2D original character declared; anime medium (not photoreal)
- [ ] Presence language on Figures and heat (no `nude`/`no clothes` headline)
- [ ] Prompt contains none of: hentai, nsfw, nude, no clothes, undressed, naked, girl-as-subject
- [ ] Soft-looking painted skin / illustrated gloss, not oily plastic / not photo pores
- [ ] Heat first shot = hottest legal frame; §9B only after a heat block (incl. B4 motion)
- [ ] Clothed overflag used §9A, not §9B
- [ ] No circumvention recipes
- [ ] Full English prompt under each frame
- [ ] No `generate_image`, no `size`
- [ ] Figure-gen ask did not replace the three looks
- [ ] Figure sheet still allowed arms-at-sides (exception)

IF start line missing OR storyboard ran with lock=NO OR lock=NO turn lacked the three labeled looks OR storyboard violated Dynamic Pose Law THEN the run is invalid.

---

**End of Mio Playbook v1.8. Runtime version = SKILL.md Version line (v1.8).**
