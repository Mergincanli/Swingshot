---
name: "art-style-aesthetics-synthesis"
description: "Write one game-wide art-style doc from character docs and research reports. Use when a candidate is promoted, a research report is filed, or a look topic like outlines or shading is written up."
---

# Art-Style Aesthetics Synthesis

Turn what several character docs and research reports say about one topic into one game-wide doc that an artist, or a production bot, can build from. A character doc says how one character looks. An aesthetics doc says what holds across the game, how far it varies, how it is probably made, and how to reproduce it in each production tool.

This skill works for any game. The project instructions decide which game, which folder the docs live in, and which production tools get a brief. Defaults when they say nothing: folder `docs/research/art/`, one brief for Blender and one for Three.js / WebGPU. All paths below are relative to that folder.

It is the companion of the art-style-character-dissection skill and shares its evidence tags and its viewer-sheet rule: a viewer sheet is evidence for the shape side only, never for what the game's renderer adds.

## Rules

1. **One topic, one doc.** A topic is one part of the look that a maker builds as one thing: outlines, face shading, hair, eyes, shadow colour, palette, ornament. If a doc starts to cover two, split it.
2. **Seen or cited, nothing else.** Every statement rests on a character doc, a research report, or a source you opened. A report's claim about a source is not the source: open the source before citing it. Anything from memory is tagged as inference.
3. **What is seen and how it is made stay separate.**
4. **Say how far it holds.** Name the characters it was checked on, the ones that break it, and the range it varies in. Never write "always" or "every" from fewer than three characters.
5. **Report disagreement, do not settle it.** When sources disagree on a method, give each side with its source and say what evidence would settle it.
6. **Describe the reference game.** No design decisions for another game. Reproduce the style, never a character. No extracted or ripped game assets.

## When to write a doc

- A candidate in `aesthetics/_candidates.md` holds for three or more characters.
- An official or breakdown source states a game-wide finding, usually through a research report.
- The user asks for a topic.

Before writing, list the docs you propose: topic, expected status, and the candidates each takes in. Wait for the user's approval of that list.

## Procedure

1. **Pin the topic.** Name it and list the candidates and report sections it takes in. Check `aesthetics/` first: if a doc already covers the topic, update that doc.

2. **Collect.** Read `_axes.md`, `aesthetics/_candidates.md`, the character docs in `characters/`, the reports in `references/reports/`, and `references/viewers.md`. Pull every observation and statement on the topic, each with its tag.

3. **Write "What holds".** State the finding in one or two sentences. Then give the evidence per character, the range of variation, and the exceptions.

4. **Write "How it is made".** Three parts, kept apart: what the developer says, what recreations do, and where they disagree.

5. **Write the production briefs.** One per tool, each able to stand alone. Five to ten numbered rules per brief. Each rule is one imperative sentence that can be carried out in that tool. A rule may rest on a recreation's method; when it does, name that recreation in the brief's sources. Close each brief with its own sources: one link the maker can open for every technique its rules name. Manual and API pages for the production tool are source type `tool docs`.

6. **Set the status.**

7. **Update the shared files.**
   - `aesthetics/_candidates.md`: set the outcome of each candidate taken in to "promoted", with a link to the doc.
   - Character docs: where a Technique field repeats the finding, replace the repeated text with one line that links to the doc. Never change an Observation field.
   - `INDEX.md`: add or update the doc's row, type aesthetics, with the status in the Confidence column.
   - `references/sources.md`: add new sources.

8. **Save.** One file per topic in `aesthetics/`, named after the topic in lowercase with hyphens, ending in `.md`. If you cannot write to the folder, output each complete file in its own block, headed by its full path.

9. **Run the checklist.**

## Evidence tags

The same set as in art-style-character-dissection: `[shot: name]`, `[viewer: name]`, `[official]`, `[breakdown]`, `[community]`, `[inferred]`. Two more:

- `[doc: name, axis]` taken from a character doc. Name the doc and the axis.
- `[report: name]` a conclusion drawn by a research report itself. For a fact the report takes from a source, cite that source.

## Status

- **Established:** holds for three or more characters on evidence that counts for its side: viewer sheets or in-game shots for the shape side, in-game shots for what the renderer adds.
- **Sourced:** rests on `[official]` or `[breakdown]` sources and is not yet seen in our own shots.
- **Emerging:** fewer than three characters, or the sources disagree on the core of it.

## Doc format

Use this exact template so docs stay comparable.

```
# [Topic] ([Game])
Status:
Checked on:
Candidates taken in:

## Production brief: Blender
1.
Sources for this brief:

## Production brief: Three.js / WebGPU
1.
Sources for this brief:

## What holds
Finding:
Per character:
Range:
Exceptions:

## How it is made
The developer says:
Recreations do:
Disagreements:

## Sources
## Open questions
```

## Checklist

- Could a maker who has never seen the game build this part of the look from the briefs alone?
- Does every statement carry a tag, and every `[official]` and `[breakdown]` a link you opened?
- Is it clear how many characters the finding was checked on, and which ones break it?
- Are developer statements, recreations and disagreements kept apart?
- Is there one brief per tool, each with five to ten rules and its own sources, and no rule that depends on the other brief?
- Is the doc free of abilities, lore, gameplay and design advice for another game?
- Are `_candidates.md`, `INDEX.md` and `references/sources.md` updated, and is repeated Technique text in character docs replaced by links, with no Observation field changed?

## Example

Abridged, and about an invented game on purpose. It shows tone, tagging and how to handle a disagreement. It is not a source: never reuse its content.

```
# Outlines (Skyward Atlas)
Status: Sourced
Checked on: Mira, Tolv
Candidates taken in: C4, C9

## What holds
Finding: Every character carries a thin outline whose colour follows the material it borders. It is never pure black. [doc: mira, axis 6] [doc: tolv, axis 6]
Range: about 0.2% to 0.4% of figure height. [doc: mira, axis 6]
Exceptions: none found in two characters. Too few to call it a rule.

## How it is made
The developer says: nothing found on outlines.
Recreations do: one builds a second, slightly larger shell that shows only its inside faces [breakdown]; another finds edges in the finished image [breakdown].
Disagreements: the two methods differ at inner folds. Close-ups of a concave fold at two distances would settle which one the game uses.
```
