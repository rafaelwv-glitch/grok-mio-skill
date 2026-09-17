# Grok Mio Skill (`anime-oc-mio`)

**Public release of the Grok Mio / Anime OC Mio skill** — an agentic original-character designer for [Grok](https://grok.com) (Imagine Agent / Grok Skills).

**Version:** 1.7 (2026-09-14) — see [CHANGELOG.md](./CHANGELOG.md)

> Just the Grok Mio skill. No JuicyChat bible, no private archives, no bots.

## What Mio does

Mio is a lock-first anime OC designer modeled after Mio.2-style workflows:

1. **New OC** → always shows **3 looks** in the first image turn (bishoujo-moe, 2000s cel-shade, Pixiv sensual illustration), then waits for your lock.
2. **After lock** → storyboards the greeting/opening **1–2 frames per beat**, rotating camera/POV.
3. **Heat** → R-rated **2D illustration** of the beat (in-bounds craft), with separate retry ladders for SFW overflags vs heat blocks — not jailbreaks.

Every image turn starts with:

```text
Mio v1.7 · lock=YES|NO · beats=N
```

## Install for Grok Skills

### Option A — Skills folder (desktop / skills-capable Grok clients)

1. Copy this repo (or clone it) into your Grok skills directory as `anime-oc-mio/`:

   ```text
   <your-grok-skills>/anime-oc-mio/
     SKILL.md
     CHANGELOG.md
     references/
       playbook.md
       heat-in-bounds.md
       pixiv-illustration-quality.md
   ```

2. Ensure the skill frontmatter `name: anime-oc-mio` is visible to the client.
3. Restart / reload skills if your client requires it.
4. Trigger with: `Mio`, `OC`, `looks`, `face lock`, `storyboard`, `heat-pass`, etc.

### Option B — Paste / upload

- Upload or paste `SKILL.md` as a single-file skill. The skill is written to run **standalone** (no second fetch required).
- Keep `references/` beside it when possible; Mio will still run from `SKILL.md` alone.

### Option C — Git clone

```bash
git clone https://github.com/rafaelwv-glitch/grok-mio-skill.git
# point your Grok skills path at ./grok-mio-skill (or copy SKILL.md + references/)
```

## Layout

```text
SKILL.md                              # full ritual (source of truth)
CHANGELOG.md                          # version history
LICENSE                               # MIT
README.md                             # this file
references/playbook.md                # operator mirror / checklist
references/heat-in-bounds.md          # spicy in-bounds recipes
references/pixiv-illustration-quality.md  # quality / camera / lighting
```

## Hard rules (short)

- Adult presentation age **25**, head-to-body **1:7**, no underage, no real-person likeness.
- **Lock face + style before storyboard.**
- Slot 3 is always shown on a new OC (user may reject after seeing it).
- `{{user}}` in prompts = generic adult male, same animation style.
- NSFW creative guidance in this skill is for **fictional adult 2D illustration** only, within xAI / Grok allowed lanes.

## License

MIT — see [LICENSE](./LICENSE).

## Attribution

Extracted and sanitized for public release from a private skills monorepo. Personal operator details, private account ops, and unrelated projects were removed.
