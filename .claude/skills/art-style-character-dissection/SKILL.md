---
name: "art-style-character-dissection"
description: "Dissect how one game character looks in-game into an artist-ready reference doc. Use whenever a character's look, hair, outlines, shading, colours, clothing or weapon is researched or documented."
---

# Art-Style Character Dissection

Turn one in-game character into one reference doc that an artist, or a production bot, can rebuild the look from without opening the game. A doc answers three questions in order: what is visible, how it is probably made, and how to reproduce it in each production tool.

This skill works for any game. The project instructions decide which game, which folder the docs live in, which production tools get a brief, and what is out of scope. Defaults when they say nothing: folder `docs/research/art/`, one brief for Blender and one for Three.js / WebGPU, default outfit only. All paths below are relative to that folder.

## Rules

1. **In-game model only.** Splash art, cards, key visuals, trailers and merchandise are not evidence. Mention them only to note where they differ from the model. A viewer sheet is a render of the game's own model outside the game, from a model viewer or turntable. It is evidence for the shape side only: what belongs to the model and its textures, such as silhouette, proportions, the construction of face, eyes and hair, clothing, ornament, painted lines and unlit base colours. It is never evidence for what the game's renderer adds: outlines, shading bands, highlights, rim light, material response, or how the character sits in a scene.
2. **Seen or cited, nothing else.** You cannot view images found through web search. Describe only what is visible in a shot or viewer sheet the user provided, or stated in a source you opened. Anything you know from memory is inference and is tagged as inference.
3. **Observation and technique stay separate.** "Hair reads as five large clumps" is observation. "Probably two-tone cel shading with a painted highlight mask" is technique.
4. **Every claim carries an evidence tag.**
5. **Every axis, same order, every time.** If you cannot fill one, write "Not observable" and name the shot or source that would resolve it.
6. **Reproduce the style, never the character.** No instructions for copying a specific design. No extracted or ripped game assets.
7. **Out of scope:** abilities, effects, lore, gameplay.

## Procedure

1. **Pin the subject.** One character, one outfit, one doc. Record the game version or the date of the shots.

2. **Ask for shots, then stop.** List what you need: front, side, back, three-quarter, face close-up, hair detail, weapon in hand, and one shot outdoors in daylight. Ask for flat, neutral lighting where possible. Wait until the user provides them. With neither an in-game shot nor a viewer sheet, do not dissect. With a viewer sheet only, do not wait for more: dissect the shape side, write "Not observable" for everything the renderer adds, and list the in-game shots that would fill it.

3. **Load the shared context.** Read `_axes.md` and everything in `aesthetics/`. When a viewer sheet is used, also read `references/viewers.md`. If `_axes.md` holds no agreed axes, propose a list based on the defaults below, wait for agreement, save it, then continue.

4. **Search for text sources.** Look for developer talks and interviews, and for technical breakdowns of how this game renders characters. Note what each one covers. Never cite a page you did not open.

5. **Observe.** Fill the Observation field of every axis from the shots and viewer sheets only. Name the shot or view each statement comes from.

6. **Explain the technique.** For every axis, say how the look is probably achieved, without naming a production tool. Link to an `aesthetics/` doc instead of repeating a game-wide finding.

7. **Compare.** Read up to three existing docs in `characters/`. Note what this character shares with them and where it breaks the pattern. Game-wide candidates live in `aesthetics/_candidates.md`, not in the character doc: add this character's line to each existing candidate, add new candidates there, and in the doc name only the candidate IDs it supports or breaks. When a candidate qualifies for promotion, say so; the aesthetics doc is written with the art-style-aesthetics-synthesis skill, never inside a dissection.

8. **Write the production briefs.** One per tool, each able to stand alone. Five to ten numbered rules per brief. When confidence is Shape only, head each brief "Partial: shape only", write rules only for what was observed or cited, and accept fewer than five. Each rule is one imperative sentence that can be carried out in that tool, followed by the axis it rests on. A rule says how to reproduce what was observed. It is not a claim about how the developer built it, and not a design decision for another game. Close each brief with its own sources: one link the maker can open for every technique its rules name. Manual and API pages for the production tool are source type `tool docs`, cited only in a brief's source list.

9. **Save and index.** Save the doc in `characters/`, named after the character in lowercase with hyphens, ending in `.md`. Add the shots to `references/shots.md`; a shot without a link is recorded as "pasted in chat, no link", and you ask once where it came from. Add the sources to `references/sources.md`. When a viewer sheet was checked against an in-game shot, record what matched and what differed in `references/viewers.md`, not in the character doc. Add or update the doc's row in `INDEX.md`. If you cannot write to the folder, output each complete file in its own block, headed by its full path.

10. **Run the checklist.**

## Evidence tags

Put the tag in square brackets at the end of the sentence or field it covers.

- `[shot: name]` visible in a provided in-game shot. Name the shot.
- `[viewer: name]` visible in a provided viewer sheet. Name the view. Shape side only.
- `[official]` stated by the developer in a talk, interview or documentation. Link it.
- `[breakdown]` from a technical analysis by a named third party. Link it.
- `[community]` widely repeated, no primary evidence.
- `[inferred]` your own reasoning from what is visible, or from memory.

## Confidence

- **High:** front, side, back and face close-up were provided, and the main technique claims rest on `[official]` or `[breakdown]`.
- **Medium:** the shots cover the character, but technique is mostly `[inferred]` or `[community]`.
- **Low:** fewer than three shots, or key axes are not observable.
- **Shape only:** a viewer sheet covers the character and there is no in-game shot. The shape side can be relied on; everything the renderer adds is unobserved.

An in-game shot whose source is unknown is provisional. Mark each statement taken from it "Provisional", rest no brief rule on it, and do not let it raise the confidence. Drop the label once the source is given.

## Default axes

Used only until `_axes.md` holds an agreed list.

1. Silhouette and proportions
2. Head and face construction
3. Eyes
4. Hair: shape language, clumps, highlight, shadow
5. Skin: tone, shading bands, rim light
6. Outlines: where they appear, thickness, colour, where they vanish
7. Clothing: structure, layering, trim, how pieces end
8. Materials: how cloth, metal, leather, glass and gems respond to light
9. Colour: dominant, secondary, accent; saturation; where black and white are used
10. Weapon: how it follows or breaks the character's palette and shapes
11. Readability: what identifies the character at a distance and in motion
12. Fit with the world: how the character reads against its region's palette

Colour values are approximations. Sample them from the most neutrally lit shot, name that shot, and label them approximate.

## Doc format

Use this exact template so docs stay comparable.

```
# [Character] ([Game])
Outfit:
Game version or shot date:
Confidence:
Shots used:

## Production brief: Blender
1.
Sources for this brief:

## Production brief: Three.js / WebGPU
1.
Sources for this brief:

## Dissection
### 1. [Axis name]
Observation:
Technique:

(one section per axis, in the order of _axes.md)

## Comparison
## Sources
## Open questions
```

## Checklist

- Could an artist who has never seen the character rebuild the look from the briefs alone?
- Is every axis filled, or marked "Not observable" with the missing shot named?
- Does every claim carry a tag, and every `[official]` and `[breakdown]` a link?
- Are Observation and Technique separate in every axis?
- Is there one brief per tool, each with five to ten rules (fewer when Shape only) and its own sources, and no rule that depends on the other brief?
- Is the doc free of abilities, lore and gameplay?
- Are `INDEX.md`, `references/shots.md`, `references/sources.md` and `aesthetics/_candidates.md` updated?

## Example

Abridged, and about an invented character on purpose. It shows tone, tagging and how to handle a gap. It is not a source: never reuse its content.

```
### 4. Hair
Observation: Reads as five large clumps, plus two thin strands that break the silhouette at the fringe. One hard-edged highlight band crosses the crown and follows the curve of the head, not the strands. Shadow is a single darker, slightly more saturated tone with a hard edge. [shot: front, hair detail]
Technique: Two-tone cel shading with a painted highlight mask is the likely route. [inferred] Whether the highlight moves with the camera: Not observable from stills; a short turntable clip would resolve it.
```

```
## Production brief: Blender
3. Split hair shading into two flat tones with a hard edge: Diffuse BSDF into Shader to RGB into a Color Ramp set to Constant. (Axis 4)

## Production brief: Three.js / WebGPU
3. Split hair shading into two flat tones with a hard edge: MeshToonMaterial with a two-step gradient map using nearest filtering. (Axis 4)
```