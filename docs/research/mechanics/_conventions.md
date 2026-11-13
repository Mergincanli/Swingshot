# Mechanics research conventions

Agreed vocabulary and formats for everything under `docs/research/mechanics/`. Change only by agreement with Mustafa, and record each change in the change log at the bottom.

## Scope

Describe GunZ: The Duel as it behaved. Never propose what Swingshot should do, never improve on the reference, and never fill a gap with a guess. Unknown stays "Unknown".

- In scope: movement, animation cancels, melee, blocking, ranged weapon behaviour, hit registration, play styles.
- Out of scope: skins, cosmetics, lore, quests, monetisation, asset lists. Source code is read as evidence (see Source code) and is never copied into a doc.

## Versions

- Version labels are set in `versions.md` once Mustafa has confirmed the reference version. Until then, name each build in full.
- When versions disagree, prefer: 1. the version competitive players settled on, 2. the original international release, 3. the Steam release.
- Every claim names the version it applies to. Never merge versions into one "GunZ".

## Evidence tags

- **Verified:** several independent sources, or footage Mustafa has confirmed.
- **Code:** read directly in the source code or data files of a public repository. It holds for that repository's build only.
- **Community consensus:** widely repeated, no primary evidence.
- **Single-source:** one source only.
- **Inferred:** reasoned from behaviour, stated by no source. Allowed only in Cause sections.

Sources that copy each other (mirrors, reposts, quotes) count as one source.

Video: do not describe what a video shows unless its description or transcript states it, or Mustafa has watched it and confirmed it, or supplied screenshots from it. Say what was observed and by whom. A link alone proves nothing.

Research reports in `references/reports/` are maps, not sources. Open the pages they point to and cite those.

Pages that refuse to open: a claim seen only in a search-result excerpt is a lead, not a finding. Mark it "excerpt only", keep it out of every Production Brief, and list the page under Open questions. Do not file the page in `references/sources.md` until someone has opened it.

Numbers (frames, milliseconds, damage, spread, range) need a source. Without one, write "Unquantified".

## Source code

Public source repositories of the game may be read to establish rules and values. Nothing from them is copied.

- Cite the repository, the file and the function, and the date it was read.
- Describe what the code does in words and numbers. No code blocks and no copied lines. A file path, a function name, and a constant's name with its value are allowed.
- Label each code claim with the build the repository is based on, using the labels in `versions.md` (for example `L10` or `PS-RG`), never `IJJI`. Where no period source confirms the same behaviour for `IJJI`, say so under Version differences.
- A fork may have changed the original. Check its README, change notes and history for the area the doc covers, and say what the fork changed. Prefer the least-modified source.
- When code and community sources disagree, record both. Code decides for its own build only.
- Give a unit only when the code makes it certain. Otherwise write "unit not stated".
- Say which files were read, and which part when a file was cut off. Never describe code that was not seen.
- When a value sits in a file that cannot be read, such as an animation file, say so. Do not estimate it.
- Record only the values a doc needs. Never reproduce a data file or a table from it wholesale.
- Default repositories: read rafadsm/Gunz1.5 first and cross-check every claim in fxpgunz/gunz-1.0. Write the first as "`L15` mod" (the 1.5 source with one maintainer's later additions) and the second as "`PS-RG` fork" (Open GunZ, a fork of Refined Gunz, `L10` base). A code claim goes into a Production Brief only when both agree, or with the difference written next to it.

## Confidence, per doc

- **High:** the core fields are Verified, or Code from the reference version.
- **Medium:** mostly Community consensus, or Code from another build.
- **Low:** mostly Single-source, or large gaps.

## Importance to audience

The audience is veteran GunZ players. Rate each technique or rule as Essential to the feel, Nice to have, or Forgettable, with one line of reasoning drawn from how players talk about it.

## Action names

Write inputs as game actions, not keys. Starting list: jump, dash, slash, block, shoot, reload, swap weapon, alt attack. Alt attack is the second attack input: a launch with a sword or kodachi on the floor, a lunge with a dagger, a wall hang when held in the air with a melee weapon. Add a new action name to this list before using it in a doc.

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
- 2026-11-13: source types news and repository added in `references/sources.md`; rule added for excerpt-only claims.
- 2026-11-13: source code allowed as evidence; Code tag and Source code rules added.
- 2026-11-13: confidence rule for code from another build; action name alt attack; default repositories for code claims.
