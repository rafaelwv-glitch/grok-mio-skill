# Style Lanes A–F (Mio v1.9)

**Purpose:** Stable Style Lock vocabulary for LOOKS slots, JuicyChat card art, and Original-Art extraction.  
**Rule:** Style Lock = **one Lane letter + 4–6 English NL tokens** (line weight, shading, palette, skin, eye gloss). Re-inject every frame.  
**Never:** copy a living artist's keyed style sheet; never put `artist:` LoRA tags or `stuart_pot` as required tokens; never put `hentai` / `nsfw` / `nude` in prompts.

Research mirrors (descriptor seeds only): PixAI Tsubaki NL + style presets; Pixiv sensual painterly / game-CG / semi-gloss community recipes; Illustrious quality tags translated to NL. PixAI APIs are **not** required to run Mio.

## Lane table

| Lane | Name | NL inject (pick 4–6) | When |
|------|------|----------------------|------|
| **A** | Soft moe bishoujo | vibrant soft shading, big glossy eyes, clean bishoujo polish, pastel accents, sparkle-light highlights | Slot 1 looks; cute SFW greeting. **Never** Opening heat. |
| **B** | 2000s cel | flat cel shading, hard color holds, screencap polish, clean thick-thin lineart, limited palette holds | Slot 2; comedy / deliberate retro anime cards only |
| **C** | Pixiv sensual painterly | clean delicate linework, soft painterly airbrush gradients, glossy illustrated skin highlights, dense eyelashes, luminous soft palette, semi-realistic anime that stays 2D | **Default Figure** / JuicyChat body art; Slot 3; Opening heat OK |
| **D** | Game-CG / VN polish | game CG illustration, soft bloom, rich fabric folds, cinematic key light, polished official-art finish | **PFP** preferred; key visuals |
| **E** | Semi-gloss detail | thin sharp lineart, multi-highlight glassy eyes, glossy hair sheen, nose shine, smooth painterly skin | **PFP** alternate; Opening heat OK; high-detail faces |
| **F** | Retro shoujo fine-line | fine warm linework, parallel blush hatching, soft cel-hybrid gradients, high-key pastels, luminous bloom | Soft romance only — **not** compensation / leak / hard-friction cards |

## JuicyChat defaults (Keel)

- Default **Figure:** **C** (reads as “real bot,” not Slot-1 cute)
- **PFP:** **D** or **E** (tight face, glassy eyes). **B** only if the card is consciously 2000s/comedy
- **Opening heat:** **C** or **E** + presence language (skill §1). Never Lane **A** (A+heat → underage trip on Image 2.0)
- **Adult lock BEFORE moe** on every frame
- Original-Art: map upload → Lane letter + 4–6 NL tokens or Canvas drifts back to Slot-1/2 defaults

## Mapping from a user upload

1. Look at line weight (delicate vs thick cel)
2. Shading (flat holds vs painterly airbrush)
3. Palette (pastel / saturated / game-CG bloom)
4. Skin (illustrated gloss vs flat cel)
5. Eyes (dense lashes / multi-highlight vs simple moe)

Pick the closest Lane. Write Style Lock as:

`Style Lock: Lane C — clean delicate linework, soft painterly airbrush gradients, glossy illustrated skin highlights, dense eyelashes, luminous soft palette`
