---
name: session-notation-song-prompting
description: >
  Generate structured, copy-paste-ready prompts for AI music generators (Suno, Udio, etc.)
  using Session Notation — a prompting methodology that separates production direction [in brackets]
  from lyrics as plain text, with bar/beat-level timing control.
  Use this skill whenever someone asks to write a song prompt, music prompt, Suno prompt,
  lyrics with production notes, arrangement instructions, or mentions bars, beats, hooks,
  verses, mixing, or any music generation workflow. Also trigger when the user wants more
  control over drops, transitions, vocal delivery, instrument layering, or song structure
  in an AI music context — even if they don't say "Session Notation" by name.
license: CC0-1.0
---

# Session Notation — Song Prompting

Session Notation combines **lyrics + production/arrangement + performance direction** into a single prompt by separating **direction tags** `[...]` from **lyrics** (plain text). The core idea: use **bar/beat-level timing** (e.g. "Bars 1–4", "bar 8 hit") to precisely control entrances, pockets, drops, fills, and FX.

For copy-paste building blocks and mixing basics, see `references/LIBRARY.md`.
For full worked examples, see `references/EXAMPLES.md`.

## Quick Start

1. Produce a **copy-paste prompt** (Header → Timeline → Motifs). Keep explanations brief.
2. Keep **priorities small** per section: pocket + layer + transition + maybe one hit point.
3. Use bars/beats/words as **timing anchors** so beat and lyrics lock together.

## When to Use

- User wants **control** over: mix/texture/width, instrument entries/FX, arrangement coherence via layering + motifs, hook/lyrics delivery
- User mentions: "Suno prompt", "music gen prompt", "lyrics + production notes", "arrangement instructions", "bars 1–4", song sections, drops, risers, vocal stacking

## Core Rules

### Separation
- **Direction** goes in `[...]`
- **Lyrics/spoken text** goes as plain lines — never inside brackets

### Vocal Direction vs Lyrics
- Good: `[Vocal: lead, spoken, close mic, intimate]` followed by a lyrics line
- Bad: `[Lead (spoken...)] ("Lyric text here...")` — lyrics hidden in brackets

### Bars Are the Backbone
- Use 1–2 bar phases per section (e.g. `Bars 1–4`, `Bars 5–8`)
- Place targeted hits: `bar 8 tape-stop`
- Default is **4/4**; bars count **per section** unless marked "Song bars …"

### Hit Points (Exact Sync)
For precise synchronization (instrument starts *exactly* on a beat / FX hits *exactly* on a word):
- **Beat anchors**: "downbeat 1", "& of 3", "beat 4", "bar 8"
- **Word anchors**: "on word: ..." (the word appears in lyrics, not in `[...]`)

### Priorities Over Overload
Per section, aim for:
- 1 pocket/drum rule
- 1 layer change
- 1 transition/FX accent
- (optional) 1 hit point

## User Inputs to Gather

If not provided, ask briefly:
- **Style direction**: 1–2 lines — subgenre, vibe, references, instrument colors
- **Lyrics**: complete lyrics or at least hook + themes/keywords
- **Target platform** (Suno / Udio / other) and desired **prompt density** (minimal / mid / full)
- **Genre, tempo (BPM)**, optional key, meter, swing/groove
- **Song structure**: Intro / Verse / Pre / Hook / Bridge / Outro + repeat counts
- **Vocal**: language, persona/voice, proximity, delivery (spoken/sung/rap), harmony plan
- **Sound world**: room/texture, width, energy curve
- **Motifs**: 1–3 recurring signatures (reverse vox tail, 808 glide, fill pattern)
- **Content boundaries**: clean/explicit, themes, no-gos

## Output Format (Always the Same)

Produce a **copy-paste-ready prompt**:

1. **Header** (Song DNA) as `[...]` tags
2. **Timeline**: per section 2–6 tag lines + lyrics
3. **Motifs** block (optional but recommended)

One tag per line for stability. Use `|` for parallel info.

## Accuracy Note

Numbers like `−12 dB`, `120% width`, `retune 15 ms` express **intention/feeling**, not guaranteed engine precision. When unsure, prompt relatively: "very quiet", "wider", "subtle pump".

## Prompt Length Budget

| Level | Header Tags | Tags/Section | Details |
|-------|-------------|-------------|---------|
| **Minimal** | 6–10 | 1–3 | Few numbers, 0–1 hit points |
| **Mid** | 10–16 | 3–6 | Bar phases + 1–2 hit points |
| **Full** | 16–25 | 5–10 | Micro-rules + motifs block |

## Intensity Vocabulary

Instead of measurements, use this scale:
- **subtle**: barely audible, "just a feeling"
- **medium**: clearly audible but not dominant
- **hard**: obvious effect/move

## Workflow

1. Define **core DNA** in 8–15 header tags (genre, BPM, drums, bass, instruments, vocal, space/texture, feel)
2. Create **sections** (Intro / Verse / Pre / Hook / Bridge / Outro)
3. Per section:
   - Pocket/drums rule + bar phases
   - Layer change (e.g. Rhodes in, hats out)
   - Transition/FX (e.g. riser, tape-stop, reverse tail)
   - Vocal direction (e.g. close mic, mantra hook, harmony stack)
   - Hit points (optional): "on-the-beat" events via beat/word anchors
4. Define **motifs** (what recurs each hook)
5. Write/format **lyrics**: clear hook phrasing, intentional repetition, never in `[...]`
6. **Sanity check**: no contradictory mix instructions, bar refs make sense per section, max 3–5 priorities per section

## Common Mistakes

- **Lyrics in `[...]`** → interpreted as direction. Always write lyrics as plain text.
- **Unclear bar counting** → mark "Bars 7–8 (of this section)" when ambiguous.
- **Too many simultaneous goals** → stick to 1–2 dominant moves per section.

## Templates

### Minimal (fast but controlled)

```text
[Title: "..."]
[Style: ... | Tempo: ... BPM | Key: ...]
[Drums: ...]
[Bass: ...]
[Vocal: ...]
[Space/Texture: ...]
[Motif: ...]

[Intro — set tone]
[Bars 1–4: ...]

[Verse 1 — restrained]
[Bars 1–4: ...]
[Bars 5–8: ...]
<LYRICS>

[Hook — mantra]
[small lift | harmony note]
<LYRICS>

[Bridge — breakdown]
[4 bars: ...]
<LYRICS>

[Final Hook — lift]
[fuller stack | subtle fills]
<LYRICS>

[Outro — fade]
[drums mute last 2 bars | tail]
```

### Mid-Detail (Sweet Spot)
- 2–4 tag lines + 1 vocal line + 1 FX/transition line per section
- Bar phases: typically `Bars 1–4` / `Bars 5–8`

### Full-Detail (Maximum Direction)
- Precise header (BPM, swing, kit character, atmosphere level)
- Hooks with repeatable micro-rules (kick busy bars, ghost notes, bar-8 hit)
- Dedicated motifs block at the end

## Building Blocks

For concrete copy-paste blocks, see `references/LIBRARY.md` — covers drums, bass, instruments, vocals, mix, FX, automation, negative space, hit points, mixing basics, and ready-made recipe blocks.
