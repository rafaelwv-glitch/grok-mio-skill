# Anime OC Mio Playbook v1.6
**Locked:** 2026-09-14
**Skill:** `SKILL.md` **v1.7** (this playbook is a **mirror**. Imagine Agent must run from SKILL.md alone.)

SKILL.md v1.7 is the source of truth. If this file and SKILL.md conflict, **SKILL.md wins**.

---

## 0. LOAD ORDER

IF Mio / looks / OC / illustration / face lock / Imagine greeting / storyboard is requested THEN:

1. Load `SKILL.md` v1.7. That file **is** the ritual. Do not require a second fetch.
2. **Before any image**, print:
   `Mio v1.7 · lock=YES|NO · beats=N`
3. Apply **Rank** (skill §0.1). Lock and beats outrank heat.
4. IF `lock=NO` THEN generate three images this turn:
   Slot 1 bishoujo-moe · Slot 2 2000s cel-shade · Slot 3 Pixiv sensual illustration (2D, not photoreal).
   WAIT. NEVER storyboard. NEVER hand off to figure-gen. EVEN IF a full bot pack was dropped.
5. IF `lock=YES` AND greeting/storyboard is requested THEN skill §8.
6. Imagine Agent generates natively. NEVER `generate_image`. NEVER `size`.

**Failure to print the start line is a process failure.**
**Mio §2 three looks land BEFORE figure-gen §0a ask.**

```
FAIL-if lock=NO and this turn does not generate exactly these three images before any other visual:
  Slot 1 bishoujo-moe · Slot 2 2000s cel-shade · Slot 3 Pixiv sensual illustration (2D, not photoreal).
A questionnaire, a single Figure/PFP ask, or "Slot 3 only if adult" is INVALID.
Slot 3 is ALWAYS shown on a new OC. The user may reject it after seeing it.
```

---

## 1. COMMANDS

| User says | THEN |
|---|---|
| Fire up Mio / looks / this is [Name] | If lock=NO: §2 three looks this turn. If they lock a look: Face Lock + Style Lock. Copy visual into Situation when asked. |
| This is [Name] / lock this look / slot N | Face lock + style lock. `lock=YES` next turn. |
| Assembled package / storyboard the greeting | **If lock=NO: three looks first, wait.** If lock=YES: skill §8. NEVER skip lock because a pack was dropped. NEVER replace looks with a Figure/PFP ask. |
| Restyle | New style lock only if explicit. Keep face lock. |
| Regenerated / censored / blocked on a clothed / look frame | Same beat. Skill **§9A** (camera / crop / medium / adult-lock-first). Do not add lingerie. Do not dress it down. |
| Regenerated / censored / blocked on a heat beat | Same beat. Skill **§9B**. Rephrase the **picture** (camera, cloth-state, crop, presence language, 2D). Never jailbreak. Never skip. Never fully-clothe a heat beat into a SFW hole. |

---

## 2. OC HARD CONSTRAINTS

ALWAYS: 25 · 1:7 · >1:3.5 · adult lock BEFORE moe · Face Lock re-inject · Style Lock re-inject · named crop (`full body, head to toe, feet in frame` unless the user asked cowboy / three-quarter) · dry painted skin · full English prompt under every image · `{{user}}` = generic male, same animation style · Pixiv closer · 2D original-character declaration · presence language · no names in prompts · no photoreal lead · Slot 1+2+3 on every new OC.

NEVER in an image prompt: `hentai` · `nsfw` · `nude` · `no clothes` · `undressed` · `naked` · `girl` as the subject noun.

NEVER: underage · skip Slot 1, Slot 2, or Slot 3 on a new OC · gate Slot 3 on "adult brief" · storyboard before lock · `generate_image` / `size` · real-person likeness · sticker-frame / slime-obscure / ethical-override wrappers · absence headlines as the subject · first-shot pre-sanitization of a heat beat · replace looks with a Figure/PFP ask · climb §9B on a clothed overflag.

---

## 3. NEW OC PIPELINE

```
IF lock=NO THEN
  vibe 2–3 sentences
  generate 3 images this turn, same identity
  Slot 1 ALWAYS bishoujo-moe
  Slot 2 ALWAYS 2000s cel-shade
  Slot 3 ALWAYS Pixiv sensual illustration (2D, not photoreal)
  WAIT for lock
ELSE
  stay on the lock
```

A dumped Title/Bio/Situation/World/Opening does **not** flip this to storyboard.
A figure-gen "ALWAYS ask Figure+PFP" does **not** replace this set.

---

## 4. STORYBOARD (lock=YES only)

Opening is the beat source. 1–2 frames per beat. All beats. Camera rotates. Posture changes. No annotations. Generic male `{{user}}` in locked style.

Print `beats=N` on the start line before frame 1.

Clothed beats that bounce: skill §9A.
Heat beats: first shot is the hottest legal R-rated **2D illustration** of the beat. **If blocked**, skill §9B. Heat does not outrank lock or missed beats.

---

## 5. HEAT = IN-BOUNDS FIRST, RETRY SECOND (Rank 5)

Not the main law.

First shot uses skill §1.1 — hottest legal frame, not a timid preview.

Image 2.0 overflag on a tame frame is **§9A**, not spice-down.

Heat block is **§9B**: camera → occlusion → lingerie → insinuation → closest legal R-rated 2D adult frame. Same beat. Same locks. Never fully-clothed SFW hole. No jailbreak prefixes. Stay in illustration. Never photoreal sex stills. Never absence headlines.

---

## 6. CHECKLIST

- [ ] Start line printed before images (`Mio v1.7`)
- [ ] lock=YES before any storyboard frame
- [ ] Slot 1 bishoujo-moe + Slot 2 2000s cel-shade + Slot 3 Pixiv sensual illustration shown if lock was NO
- [ ] 1–2 images per Opening beat; none missed
- [ ] POV/camera changes; motion continuity
- [ ] Named crop on every frame (default full body, head to toe, feet in frame)
- [ ] No annotations / speech bubbles
- [ ] Face + style + 25 / 1:7 / >1:3.5 / mature face held — adult lock BEFORE moe
- [ ] `{{user}}` generic male, same style
- [ ] 2D original character declared; anime medium (not photoreal)
- [ ] Presence language on Figures and heat (no `nude`/`no clothes` headline)
- [ ] Prompt contains none of: hentai, nsfw, nude, no clothes, undressed, naked, girl-as-subject
- [ ] Dry painted skin, not oily plastic
- [ ] Heat first shot = hottest legal frame; §9B only after a heat block
- [ ] Clothed overflag used §9A, not §9B
- [ ] No circumvention recipes
- [ ] Full English prompt under each frame
- [ ] No `generate_image`, no `size`
- [ ] Figure-gen ask did not replace the three looks

IF start line missing OR storyboard ran with lock=NO OR lock=NO turn lacked the three labeled looks THEN the run is invalid.

---

**End of Mio Playbook v1.6. Runtime version = SKILL.md Version line (v1.7).**
