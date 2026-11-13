# Mechanics research conventions

Agreed vocabulary and formats for everything under `docs/research/mechanics/`. Change only by agreement with Mustafa, and record each change in the change log at the bottom.

## Scope

Describe GunZ: The Duel as it behaved. Never propose what Swingshot should do, never improve on the reference, and never fill a gap with a guess. Unknown stays "Unknown".

- In scope: movement, animation cancels, melee, blocking, ranged weapon behaviour, hit registration, play styles.
- Out of scope: skins, cosmetics, lore, quests, monetisation, code, asset lists.

## Versions

- Version labels are set in `versions.md` once Mustafa has confirmed the reference version. Until then, name each build in full.
- When versions disagree, prefer: 1. the version competitive players settled on, 2. the original international release, 3. the Steam release.
- Every claim names the version it applies to. Never merge versions into one "GunZ".

## Evidence tags

- **Verified:** several independent sources, or footage Mustafa has confirmed.
- **Community consensus:** widely repeated, no primary evidence.
- **Single-source:** one source only.
- **Inferred:** reasoned from behaviour, stated by no source. Allowed only in Cause sections.

Sources that copy each other (mirrors, reposts, quotes) count as one source.

Video: do not describe what a video shows unless its description or transcript states it, or Mustafa has watched it and confirmed it, or supplied screenshots from it. Say what was observed and by whom. A link alone proves nothing.

Research reports in `references/reports/` are maps, not sources. Open the pages they point to and cite those.

Numbers (frames, milliseconds, damage, spread, range) need a source. Without one, write "Unquantified".

## Confidence, per doc

- **High:** the core fields are Verified.
- **Medium:** mostly Community consensus.
- **Low:** mostly Single-source, or large gaps.

## Importance to audience

The audience is veteran GunZ players. Rate each technique or rule as Essential to the feel, Nice to have, or Forgettable, with one line of reasoning drawn from how players talk about it.

## Action names

Write inputs as game actions, not keys. Starting list: jump, dash, slash, block, shoot, reload, swap weapon. Add a new action name to this list before using it in a doc.

## Doc header

Every doc starts with:

```
# [Title]
Game: GunZ: The Duel
Reference version:
Confidence: High / Medium / Low
Status: draft / reviewed
```

A doc is `draft` until Mustafa has read it, then `reviewed`. Only Mustafa sets `reviewed`.

## Doc types

- `techniques/`: one technique per file, written with the mechanic-deconstruction skill.
- `systems/`: one game-wide rule set per file, format below. Techniques link to systems and do not repeat them.
- `styles/`: one play style per file, format below.

### System doc

```
## Production Brief        5 to 10 numbered lines: the rules a builder has to reproduce, as facts about GunZ, each tagged. Ends with "Not established:".
## What this system covers
## Rules                   numbered, each tagged
## Values                  numbers with their source, or "Unquantified"
## Version differences
## Techniques that depend on it   links into techniques/
## Open questions
## Sources
```

### Style doc

Styles combine techniques, so they have no Production Brief.

```
## Other names
## Enabling weapons
## Core techniques         links into techniques/
## What it was for
## How common              in which community and version
## Counters
## Open questions
## Sources
```

## Index and reference files

The columns and allowed values of `INDEX.md`, `references/sources.md` and `references/footage.md` are defined at the top of each file. Follow them exactly.

## File names

Lowercase with hyphens, no version in the name: `slash-shot.md`. Raw Research reports: `references/reports/YYYY-MM-DD-topic.md`.

## Change log

- 2026-11-13: first version.
- 2026-11-13: status values and index columns aligned with the art research; index and reference-file formats moved into those files; rules added for video, copied sources and Research reports; file name for reports.
