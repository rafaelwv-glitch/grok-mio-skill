# Original-Art + Canvas Contract (Mio v1.9)

**Runtime:** Grok Imagine Agent / Canvas (native). Edit path supports up to **3** reference images.  
**Companion:** skill §2b + §5.1. This file is the prompt/templates mirror.

## When

User uploads or drops art and wants Mio to match it (style + figure), isolate the character, and keep later gens constant.

## Hard rules (Arthur)

1. **Ref1 = ISO** (or original if no ISO yet) as **subject + style ALWAYS**.
2. **Ref2** = pose / outfit / board only.
3. **Ref3** = setting / lighting **geometry + mood only**. Every Ref3 prompt MUST state:  
   `From reference 3 take background and light direction only. Do not take line language, shading, palette, or face from reference 3.`  
   Missing that line = process failure (Setting steals Style Lock).
4. After Original-Art lock: **never auto-fire Slot 1/2/3**. Variants only on explicit ask.
5. Prefer **ISO as Ref1** for later gens (cleaner subject). Keep original art on the canvas as source-of-truth, not as a competing style ref.
6. Identity drift → regenerate from ISO; do not invent a fourth face.
7. Seed: use if the runtime exposes it; do not invent a fake seed API.
8. Pin Face Lock + Style Lock (Lane + 4–6 NL tokens) into the **same** prompt as the Ref3 line.

## Start line

`Mio v1.9 · lock=YES|NO · beats=N · mode=ORIGINAL-ART`

## Step B — Isolation template

Attach Reference 1 = user's original art.

```
Reference 1 = the user's original art (SUBJECT + STYLE).
Isolate the single adult fictional character from reference 1.
Remove background, other people, watermarks, speech bubbles, captions.
Plain seamless studio backdrop, soft even light, soft gray or pure white.
Keep exact face, hair, body proportions, clothing, and rendering style from reference 1.
25 years old, mature adult woman, defined jaw, mature eyes, head-to-body 1:7, head-to-hip greater than 1:3.5.
Full body, head to toe, feet in frame.
Character-sheet clarity; front or mild contrapposto; arms may be at sides (Figure exception).
2D anime illustration, original fictional adult, not a real person, not a photograph.
[Face Lock if already drafted]. [Style Lock: Lane X — …].
Soft-looking painted skin matching reference 1. No text, no speech bubbles, no watermarks.
```

Label outputs **ISO-1** / **ISO-2**.

## Later frame template (storyboard / heat / restyle pose)

Attach: Ref1 = approved ISO; optional Ref2 = pose board; optional Ref3 = setting mood board.

```
From reference 1 take the SUBJECT and the STYLE (face, hair, body, line language, shading, palette).
[If Ref2] From reference 2 take pose and outfit arrangement only.
[If Ref3] From reference 3 take background and light direction only. Do not take line language, shading, palette, or face from reference 3.
Preserve: [Face Lock], [Style Lock: Lane X — …], body proportions 1:7, mature adult 25.
Change only: [pose / camera / cloth-state / setting as asked].
Named camera. Named crop (default full body, head to toe, feet in frame unless user asked otherwise).
Dynamic pose: [action], [weight/asymmetry/foreshortening], [secondary motion] — unless Figure sheet.
2D anime illustration, original fictional adult, not a photograph, not a real person.
Presence language for any heat beat (skill §1). Soft-looking painted skin.
No text, no speech bubbles, no watermarks.
```

## FAIL-if

- Auto Slot 1/2/3 during Original-Art intake/lock without variants ask
- Ref3 without no-style-steal sentence
- Dropping Face Lock or Style Lock (Lane + NL) from the prompt
- Using a new face after drift instead of regenerating from ISO
- Real-person likeness / photoreal undress path
