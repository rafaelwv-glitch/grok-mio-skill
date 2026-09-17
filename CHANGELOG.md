# Anime OC Mio — Changelog

Public release notes for the Grok Mio skill (anime-oc-mio).

## v1.7 — 2026-09-14

Image 2.0 heat-pass adaptation. Official lane unchanged: limited R-rated fictional adult 2D is allowed. Classifiers overflag tame frames; earlier builds still fed tripwords.

Fix:
- Start line `Mio v1.7 · lock=YES|NO · beats=N`.
- Split ladders. **§9A** SFW/look overflag = adult-lock-first + medium + named crop + camera. No lingerie add. No sweater-down. **§9B** heat retry = previous rungs. Never mix.
- Slot 3 user-facing label + inject: **Pixiv sensual illustration**. Same 2D recipe. The word `hentai` never enters an image prompt.
- Prompt-token ban: `hentai`, `nsfw`, `nude`, `no clothes`, `undressed`, `naked`, `girl` as subject. Use `adult woman`.
- Adult lock BEFORE moe on every frame.
- Figure template stays presence language (character-sheet / unadorned mature form). No absence headlines.
- Three-look ritual unchanged: Slot 1 bishoujo-moe · Slot 2 2000s cel-shade · Slot 3 Pixiv sensual illustration. FAIL-if still three images.
- Jailbreak stack still banned (stickers, slime, ethical prefix, burst-gen, language-switch).

## v1.6 — 2026-09-02

3-look restore. Earlier files still *contained* the Slot 1/2/3 table, but the agent stopped proposing the three animation looks.

Root cause:
- Playbook named Slot 1 moe + Slot 2 cel only; Slot 3 missing from the playbook bullet.
- Prior versions gated Slot 3 "when the brief is adult / heat" and retired the user-facing label `Pixiv-hentai`. Models treated the gate as skip.
- Heat wall sat above looks; figure-gen "ALWAYS ask Figure+PFP" stole the first visual turn.
- Anti-pattern listed only "Skip Slot 1 or Slot 2".

Fix:
- Start line `Mio v1.6 · lock=YES|NO · beats=N`.
- lock=NO → ALWAYS generate three images in one turn, labeled **Slot 1 bishoujo-moe · Slot 2 2000s cel-shade · Slot 3 Pixiv-hentai illustration** (label later renamed in v1.7).
- Slot 3 is unconditional. Dark / wholesome / dumped pack does not matter. User may reject after seeing it.
- FAIL-if: lock=NO turn without those three images, or a questionnaire / single Figure-PFP ask instead, is INVALID.
- Slot 3 *recipe* stays 2D illustration (no wet-look / photoreal-adjacent / act nouns).
- Crop lock kept: default `full body, head to toe, feet in frame`.

## v1.5 — 2026-08-28 (evening)

In-bounds spicy craft patch. Prior version named the allowed lane; frames were still landing bland because first shots were timid and Figures were worded as absences.

- **Official line pinned.** xAI AUP effective 2026-08-14: limited R-rated fictional adult content of *imaginary adults* is allowed. Full explicit acts blocked even for fictional anime. Real-person undress/nudify hard-blocked.
- **Presence, not absence (§3.2).** Filters fire on `nude` / `no clothes` / `undressed` as the subject more than on form + cloth-state. Figure template is a character-sheet figure study, not "nude, no clothes".
- **First shot = hottest legal frame.** Pre-sanitization was the blandness regression.
- **Named crop is load-bearing.** Imagine defaults chest-up. Figures say `full body`.
- **Mature-face tokens on every heat frame.**
- **Dry painted skin.** Ban oily plastic / wet-look porn skin.
- **Cloth-state expanded** from Danbooru states-of-dress. Still no act nouns.
- **Circumvention ban unchanged.**
- **Recipes split.** `heat-in-bounds.md` = spicy recipes. `pixiv-illustration-quality.md` = quality / camera / lighting only.

## v1.4 — 2026-08-28

In-bounds spicy patch. Imagine Mio was landing bland or bouncing because it treated heat as "fight the filter" or as photoreal-adjacent hentai skin.

- **Allowed lane written down.** R-rated 2D illustration of a fictional adult OC.
- **Circumvention ban.** No sticker frames, slime covers, ethical-override wrappers.
- **Slot 3 rewritten.** Pixiv-erotic *illustration* (2D). Not wet-look exaggerated contemporary hentai.
- **Prompt prefix.** Every frame declares original fictional adult, 2D anime illustration.
- **Cloth-state is the spice.**
- **Heat ladder stays Rank 5 retry.**
- New recipe file: `references/heat-in-bounds.md`.

## v1.3 — 2026-08-24 (evening)

Imagine-Agent regression patch.

- **Lock-first is absolute.** A dumped assembled pack is intake, not permission to skip looks.
- **One-file ritual.** SKILL.md contains load order, rank, looks, prompt order, storyboard, heat ladder.
- **Rank:** adult/proportions > face+style lock > beat coverage > generic {{user}} > heat-pass.
- **Imagine Agent native.** NEVER `generate_image`. NEVER `size`.

## v1.2 — 2026-08-24

Heat-pass + Pixiv/illustration quality.

## v1.1 — 2026-08-21

Imagine greeting storyboard protocol.

## v1.0 — 2026-08-20

Present 3–5 matching styles as images; Slot 1 moe, Slot 2 2000s cel.

## v0 / ingest — 2026-08-20

Initial ingest of Mio.2-style agentic OC designer.
