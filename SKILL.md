---
name: session-notation-song-prompting
description: Erzeugt kontrollierbare Music-Gen-Prompts mit „Session-Notation“ (Regie-Tags in eckigen Klammern), inkl. Bar-/Takt-Mikrosteuerung, Arrangement-Layering, Vocal-Regie, FX/Automation, Motifs und wiederverwendbaren Templates.
license: CC0-1.0
---

# Session-Notation Song Prompting

Dieser Skill hilft dabei, **Lyrics + Produktion/Arrangement + Performance-Regie** in einem Prompt zu kombinieren, indem du **Regie-Anweisungen** in `[...]` (Tags) und **Lyrics** als normalen Text trennst. Kern ist die **Mikrosteuerung über Bars/Takte** (z. B. „Bars 1–4“, „bar 8 hit“), um Einstiege, Pocket, Drops, Fills und FX gezielt zu dirigieren.

Referenz-Library (Bausteine/Beispiele): `references/LIBRARY.md` (inkl. **Grundeffekte & Mixing-Basics** für Einsteiger)

## Schnellstart (für den Agent)

- Erzeuge zuerst einen **copy/paste‑Prompt** (Header → Timeline → Motifs). Erklärungen nur kurz darunter, falls gewünscht.
- Halte pro Abschnitt die **Prioritäten** klein (Pocket + Layer + Transition + ggf. Hit Point).
- Nutze Bars/Beats/Words als **Timing-Anker**, damit Beat und Lyrics „einrasten“.

## Wann verwenden

- Wenn der User mehr **Kontrolle** will über:
  - **Mix/Klangbild/Welt** (Raum, Texture, Width, Noise)
  - **Einsatz/Art/Effekt** von Drums/Bass/Instrumenten/Vocals
  - **Arrangement-Kohärenz** durch Layering + wiederholbare Motifs
  - **Hook- und Lyrics-Kontrolle** (Mantra-Hook, Call/Response, Harmony-Stacks)
- Wenn der User Prompts à la „Suno prompt“, „music gen prompt“, „lyrics + production notes“, „arrangement instructions“, „bars 1–4“ erwähnt.

## Grundregeln (wichtig)

- **Trennung**:
  - **Regie** gehört in `[...]`
  - **Lyrics/gesprochener Text** steht **ohne** `[...]` als normale Zeilen
- **Vocal-Regie in Tags, nicht Lyrics in Tags**:
  - Gut: `[Vocal: lead, spoken, close mic, intimate]` gefolgt von Lyrics-Zeile
  - Schlecht: `[Lead (spoken...)] ("Lyric...")` (Lyrics in Klammern versteckt)
- **Bars/Takte sind Kern**: Verwende pro Abschnitt 1–2 Bar-Phasen (z. B. `Bars 1–4`, `Bars 5–8`) und setze gezielte Hits (`bar 8 tape-stop`).
- **Hit Points / „auf den Schlag“**: Für exakte Synchronität (Instrument startet *genau* auf einem Schlag / FX trifft *genau* auf ein Wort) nutze:
  - **Beat-Anker**: „downbeat 1“, „& of 3“, „beat 4“, „bar 8“
  - **Word-Anker**: „on word: ...“ (das Wort steht in den Lyrics, nicht in `[...]`)
- **Konvention (Timing)**:
  - Standard ist **4/4**, wenn nicht anders angegeben.
  - **Bars** sind standardmäßig **abschnitts‑lokal** (Verse‑Bars, Hook‑Bars). Wenn du globale Zählung willst, schreibe explizit „Song bars …“.
- **Prioritäten statt Überladung**: Pro Abschnitt ideal:
  - 1 „Pocket/Drum“-Regel
  - 1 „Layer“-Änderung
  - 1 „Transition/FX“-Akzent

## Inputs, die du beim User abfragen solltest (kurz)

Falls nicht gegeben, stelle wenige, gezielte Rückfragen:

- **Style-Direction**: 1–2 Zeilen „wohin soll der Song?“ (Subgenre, Vibe, Referenzen, Instrument-Farben)
- **Lyrics**: entweder komplette Lyrics oder zumindest Hook + Themen/Stichwörter
- **Zielmodell/Plattform** (Suno / anderes) und gewünschte **Prompt-Länge** (minimal/mid/full)
- **Genre/Referenz-Vibe**, **Tempo (BPM)**, optional **Key**, **Meter (z. B. 4/4)** und **Swing/Groove**
- **Songstruktur** (Intro / Verse / Pre / Hook / Bridge / Outro) + Anzahl Wiederholungen
- **Vocal**: Sprache, Persona/Stimme (z. B. „calm baritone“), Nähe (close mic), Delivery (spoken/sung/rap), Harmony-Plan
- **Klangwelt**: Raum/Texture (tape/vinyl/room tone), Breite (mono→wide), Energie-Kurve (restrained → lift → breakdown → final lift)
- **Motifs**: 1–3 wiederkehrende Signaturen (reverse vox tail, 808 glide, drum fill pattern)
- **Content-Grenzen**: clean/explicit, Themen, No-Gos

## Output-Format (immer gleich)

Gib dem User einen **copy/paste-fertigen Prompt** in dieser Form:

1) **Header** (Song-DNA) als `[...]` Tags  
2) **Timeline**: pro Abschnitt 2–6 Tag-Zeilen + dann Lyrics  
3) **Motifs** Block (optional, aber empfohlen)

Nutze **ein Tag pro Zeile** für Stabilität. Verwende `|` für parallele Infos.

## Hinweise zur Genauigkeit (realistisch bleiben)

- Zahlen wie `−12 dB`, `120% width`, `retune 15 ms` sind **Intention/Feeling**, nicht garantiert „engine‑genau“.
- Wenn der User unsicher ist: lieber **sprachlich/relativ** prompten („sehr leise“, „breiter“, „subtiler Pump“) statt Messwerte.

## Prompt-Längenbudget (damit es nicht „überpromptet“)

- **Minimal**: Header 6–10 Tags, pro Abschnitt 1–3 Tags, kaum Zahlen, 0–1 Hit Point.
- **Mid**: Header 10–16 Tags, pro Abschnitt 3–6 Tags, gezielte Bar-Phasen + 1–2 Hit Points.
- **Full**: Header 16–25 Tags, pro Abschnitt 5–10 Tags, wiederholbare Mikroregeln + Motifs-Block.

## Intensity-Vokabular (einheitliche Sprache)

Wenn du keine Messwerte verwenden willst, nutze diese Skala:

- **subtle**: kaum hörbar, „nur Gefühl“
- **medium**: klar hörbar, aber nicht dominant
- **hard**: offensichtlicher Effekt/Move

## Workflow (Schritt-für-Schritt)

1) **Kern-DNA** in 8–15 Header-Tags definieren (Genre, BPM, Drums, Bass, Instruments, Vocal, Space/Texture, Feel).
2) **Abschnitte** erstellen (Intro/Verse/Pre/Hook/Bridge/Outro).
3) Pro Abschnitt:
   - Pocket/Drums-Regel + Bar-Phasen (z. B. `Bars 1–4`, `Bars 5–8`)
   - Layer-Change (z. B. Rhodes rein, Hats raus)
   - Transition/FX (z. B. riser, tape-stop, reverse tail)
   - Vocal-Regie (z. B. close mic, mantra hook, harmony stack)
   - Hit Points (optional, aber stark): „auf den Schlag“-Ereignisse über Beat-/Word-Anker
4) **Motifs** definieren (was pro Hook wiederkehrt).
5) **Lyrics** schreiben/formatieren:
   - klare Hook-Formulierung (Mantra/Anker-Sätze)
   - Wiederholungen bewusst setzen
   - keine Lyrics in `[...]`
6) **Sanity-Check**:
   - keine widersprüchlichen Mix-Anweisungen (dry lead vs huge hall)
   - Bar-Referenzen sind pro Abschnitt verständlich
   - pro Abschnitt nicht mehr als 3–5 Prioritäten

## Häufige Fehler (kurz)

- **Lyrics in `[...]`** → werden als Regie interpretiert. Lyrics immer normal schreiben.
- **Unklare Bar-Zählung** → „Bars 7–8“ immer als „(of this section)“ kennzeichnen, wenn missverständlich.
- **Zu viele gleichzeitige Ziele** → lieber 1–2 dominante Moves pro Abschnitt.

## Templates (auswählen je nach gewünschter Dichte)

### Minimal (schnell, aber kontrolliert)

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

- Pro Abschnitt 2–4 Tag-Zeilen + 1 Vocal-Zeile + 1 FX/Transition-Zeile.
- Bar-Phasen: i. d. R. `Bars 1–4` / `Bars 5–8`.

### Full-Detail (maximale Regie)

- Präziser Header (BPM, Swing, Kit-Charakter, Atmos-Level).
- Hooks mit wiederholbaren Mikroregeln (Kick busy bars, ghost notes, bar-8-hit).
- Eigener Motifs-Block am Ende.

## Bausteine (kurz)

Für konkrete Copy/Paste-Bausteine nutze `references/LIBRARY.md` (Drums/Bass/Instrumente/Vocals/Mix/FX/Automation/Negative Space).
