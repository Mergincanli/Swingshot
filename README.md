# Swingshot

High skill 3rd person game.

One repo. Research in, product out. Research describes what other games do; production is what we make.

## Layout

```
docs/
  research/
    art/                      written only by the Genshin art-style research
      INDEX.md                every doc, status, confidence
      _axes.md                agreed dissection axes; change only by agreement
      aesthetics/             game-wide look findings: outlines, hair shading, skin, palette system, face construction
      characters/             one file per character, via art-style-character-dissection
      weapons/                only when a weapon deserves its own doc; otherwise inside the character file
      enemies/                one file per enemy type
      regions/                one file per region
      references/sources.md   every link used, with what it was used for
      references/shots.md     links to in-game screenshots, grouped by subject
    mechanics/                written only by the GunZ mechanics research
      INDEX.md                every doc, status, confidence, reference version
      _conventions.md         agreed vocabulary: version labels, evidence tags, importance scale, action names, doc formats; change only by agreement
      versions.md             version landscape: which builds exist, what differs, which one is the reference
      systems/                game-wide rules, one file per system; explained once, linked from techniques. Starting set, may change after versions.md:
        movement.md           dash, wall-run, wall-jump, air control, tumble
        animation-cancel.md   which actions interrupt which animations, and when
        melee.md              sword and dagger attacks, hitboxes, launch
        blocking.md           blocking melee and bullets
        ranged.md             weapon classes, shotgun spread, reload, weapon swap
        hit-registration.md   how hits are decided between players; netcode and lag behaviour
      techniques/             one file per technique, via mechanic-deconstruction
        butterfly.md
        slash-shot.md
        reload-shot.md
        ...
      styles/                 one file per play style: techniques it chains, weapons, why players chose it
        _survey.md            every style name found, naming conflicts resolved, what was searched for and not found
        k-style.md
        ...
      references/sources.md   every link used, with what it was used for and which version it describes
      references/footage.md   links to videos with timestamps, grouped by technique
      references/reports/     raw Research reports, saved unedited; never rewritten
  briefs/                     production contracts, maintained by hand
    art/blender/
    art/web/
    mechanics/
  decisions.md                every deliberate departure from the reference: date, what, why
blender/                      source files, textures, exports
web/                          Three.js / WebGPU demo
.claude/skills/               the skills the research runs on: art-style-character-dissection, mechanic-deconstruction
CLAUDE.md                     loaded by every Claude Code session; points to this README
```

Under `docs/research/`, a doc file exists only once it has been written. The names in the layout show what is expected, not what is there; `INDEX.md` in each folder lists what is there.

## Rules for research bots

1. Write only inside your own folder under `docs/research/`.
2. Update `INDEX.md` every time a doc is added or changed.
3. Game-wide findings go in `aesthetics/` or `systems/`, not repeated per character or technique.
4. Link screenshots and footage; never commit images or video.
5. Describe the reference game. Never propose what our game should do.

## Rules for the production bot

1. Read the brief first; briefs are the contract.
2. Open research only when a brief is unclear or silent.
3. If brief and research disagree, the brief wins; log it in `docs/decisions.md`.
4. Never edit `docs/research/`.

## Updating a brief

Research doc changes → its Production Brief section is re-read → the matching file in `docs/briefs/` is updated by hand, with the research commit noted.

## What does not belong here

- Screenshots, video or other captured media. Link them from the `references/` files.
- Anything extracted or copied from either game. We reproduce styles and systems, never assets or characters.
