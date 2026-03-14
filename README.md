# Session Notation — Song Prompting

A structured prompting methodology for AI music generators (Suno, Udio, and similar platforms) that gives you **precise control** over production, arrangement, and performance — not just lyrics.

## The Problem

AI music generators accept text prompts, but most people either write bare lyrics (no production control) or dump unstructured notes that the model can't parse reliably. There's no standard way to say "bring in the Rhodes on bar 5" or "drop the kick one bar before the hook."

## The Solution: Session Notation

Session Notation separates **direction** from **lyrics** using a simple convention:

- `[brackets]` = production/arrangement/performance direction
- Plain text = lyrics and sung/spoken words

Combined with **bar/beat-level timing** (`Bars 1–4`, `bar 8 hit`, `on word: "spiral"`), this gives you micro-level control over every section of a song.

### Quick Example

```text
[Title: "Stay Awhile"]
[Style: late-night soul / minimal jazz-pop | Tempo: 86 BPM | Key: Am]
[Drums: soft snare + light kick pulse; hats minimal]
[Bass: upright 2-bar ostinato; constant anchor]
[Space/Texture: small room | tape hiss low | close mic lead]

[Verse 1 — restrained pocket]
[Bars 1–4: bass + soft snare + kick only]
When the night gets heavy and the streetlights blur,
I'm holding my breath like a quiet rumor.

[Bars 5–8: add gentle Rhodes chords | same groove]
I don't need a miracle, I don't need a sign,
Just sit in the silence and let it unwind.

[Hook — mantra hook | tight + serious]
[Harmonies: low harmony on last word each line]
[On word: "spiral" (Hook line 2): drop hats for 1 beat]
Stay a while, stay a while,
When the walls close in, don't let me spiral.
```

## What You Control

- **Mix & texture**: room, tape hiss, width, stereo spread
- **Instrument entrances**: what plays when, at which bar
- **Arrangement coherence**: layering, motifs that repeat across hooks
- **Vocal delivery**: close mic, spoken/sung/rap, harmony stacks
- **Transitions**: risers, tape-stops, filter sweeps, drops
- **Hit points**: FX or instrument changes synced to exact beats or words

## Contents

| File | Purpose |
|------|---------|
| `SKILL.md` | Full methodology — rules, workflow, templates |
| `references/LIBRARY.md` | Copy-paste building blocks for every element (drums, bass, vocals, FX, mixing basics) |
| `references/EXAMPLES.md` | Two complete worked examples (intimate soul + modern hip-hop) |

## Usage

### As a Claude Code / Cursor Skill

Drop this folder into your skills directory. The skill triggers automatically when you ask for song prompts, Suno prompts, music production prompts, or anything involving lyrics + arrangement.

### Manual Use

Read `SKILL.md` for the methodology, grab blocks from `references/LIBRARY.md`, and follow the workflow:

1. Define song DNA in header tags
2. Build sections with bar-level timing
3. Add vocal direction + transitions
4. Define recurring motifs
5. Write lyrics as plain text
6. Sanity check (no contradictions, max 3–5 priorities per section)

## Prompt Density Levels

| Level | Best For |
|-------|----------|
| **Minimal** (6–10 header tags, 1–3 per section) | Quick ideas, short songs |
| **Mid** (10–16 header tags, 3–6 per section) | Sweet spot for most songs |
| **Full** (16–25 header tags, 5–10 per section) | Maximum control, complex arrangements |

## License

CC0-1.0 — Public domain. Use freely, no attribution required.
