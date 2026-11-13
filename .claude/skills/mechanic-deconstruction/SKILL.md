---
name: "mechanic-deconstruction"
description: Deconstruct one game mechanic into a designer-ready dossier entry. Use whenever a specific mechanic, technique, glitch, cancel, combo or movement trick from any game is researched, documented or explained, even if the user only says "look into X" or "how did X work".
---

# Mechanic Deconstruction

Turn one technique from a reference game into one doc that a builder can reproduce it from without opening the game. The doc answers three questions in order: what the player does, what the game does in response, and why players valued it.

Describe, never design. Do not propose mechanics, alternatives or improvements, and do not fill a gap with a plausible guess. The designer wants the original behaviour reproduced faithfully and makes every design decision himself. A doc that mixes in the writer's ideas makes it impossible to tell what the game did.

This skill works for any game. If the project has a README, a conventions file or instructions that set the folder layout, version labels, evidence tags or importance scale, follow those. They override the defaults below.

## Procedure

1. **Pin the subject.** One technique per doc. Record its name and every alias. If one name covers several techniques, or two communities use it for different things, split it into separate docs and say so.

2. **Search before writing.** Do not fill any field from memory. Lore around old games is full of confident, contradictory claims, and a builder who works from a myth loses weeks. Look for at least three kinds of source: a long-standing community wiki or guide, a high-level player's guide or frame-data post, and footage or a tutorial that shows or spells out the inputs. Note which game version each source describes. If the user supplies footage or screenshots, treat what is visible in them as evidence and say what you observed. When timing or state logic cannot be settled from text sources, ask the user for footage instead of guessing.

3. **Reconstruct the inputs.** Write the sequence as game actions in order (jump, slash, block), not key bindings. Bindings differ between players; actions do not.

4. **Record the timing.** Give frames or milliseconds only when a source states them, and cite that source. Otherwise write "Unquantified" and describe the window in players' own words. An honest "Unquantified" is useful. An invented number is harmful because it looks like data.

5. **Trace the state logic.** Which animation or state is interrupted, by which action, at what point. Which state the character ends in. What the character can do sooner because of it.

6. **Explain the cause.** Why the game allowed it: an engine rule, animation priority, netcode, an oversight. If the cause is a game-wide rule that a system doc already describes, link to that doc and do not repeat it. If the rule is not documented yet, describe it briefly here and list the missing system doc under Open questions. If you reasoned the cause from behaviour instead of finding it in a source, tag it Inferred.

7. **Describe the feel.** Keep this separate from the cause. What players gained (speed, safety, damage, mobility, mix-up, expression) and what made it hard (execution, timing, decision-making). Report this from how players describe it, not from your own judgement. The difficulty is part of the technique, so record it as carefully as the inputs.

8. **List counterplay and risk.** How opponents beat it, and what the player gives up or exposes by attempting it.

9. **Note version differences.** Only real differences in behaviour, listed per version.

10. **Rate importance to the audience.** Essential to the feel, nice to have, or forgettable. Add one line of reasoning drawn from how players talk about the technique.

11. **Tag, cite, and list what is missing.** Tag every field with one of: Verified (several independent sources, or footage that shows it), Community consensus (widely repeated, no primary evidence), Single-source, Inferred (allowed only under Cause). List the sources with their version. Under Open questions, list what you could not establish and how the user could check it himself, in the game client or by filming and counting frames.

12. **Write the Production Brief last and place it first.** Five to ten numbered lines. Each line is one behaviour a builder has to reproduce, written as a fact about the reference game, with its evidence tag. Include the timing demands and the counterplay, because they are part of the technique. Use only what the fields below it establish. End with a line "Not established:" that lists what a builder would still need to know.

13. **Check, then save.** Run the checklist. Save the doc where the project's layout puts technique docs, then update the index, the source list and the footage list the project keeps. If you cannot write files, output the complete doc in one block, ready to paste.

## Doc format

Use this exact template so docs stay comparable. Keep every field. When you have nothing, write "Unknown, searched: [what you looked for]" or "Not applicable". Put the evidence tag in square brackets at the end of each field or brief line.

```
# [Technique name]
Game:
Reference version:
Confidence: High / Medium / Low
Aliases:
Enabling weapon or condition:

## Production Brief
## Inputs
## Timing
## State logic
## Cause (implementation)
## Feel and payoff
## Counterplay and risk
## Version differences
## Importance to audience
## Open questions
## Sources
```

Confidence: High when the core fields are Verified, Medium when they are mostly Community consensus, Low when they are mostly Single-source or have large gaps.

## Checklist

- Could a builder who never played the game reproduce the technique from the Production Brief alone?
- Does every number have a source?
- Are cause and feel in separate sections?
- Does any line propose, improve or invent something? Remove it.
- Is every field tagged?

## Example

Abridged, and from a different game on purpose. It shows tone, tagging, the Production Brief and how to handle a missing number. It is not a source: research every doc fresh.

```
# Wavedash
Game: Super Smash Bros. Melee
Reference version: Unknown in this example
Confidence: Medium
Enabling weapon or condition: any character; slide length depends on the character's traction

## Production Brief
1. Air dodging diagonally into the ground right after a jump turns the dodge's momentum into a ground slide. [Verified]
2. After a short landing recovery the character can perform any ground action while still sliding. [Verified]
3. Slide distance depends on the dodge angle and the character's traction. [Community consensus]
4. The input window is tight and differs per character. [Community consensus]
Not established: the exact window in frames; the length of the landing recovery.

## Inputs
Jump, then immediately air dodge diagonally down into the ground. [Verified]

## Timing
Unquantified in this example. Players describe it as air dodging at the earliest moment after leaving the ground. [Community consensus]

## Cause (implementation)
Air-dodge velocity is preserved on landing and treated like any other ground momentum. [Inferred]

## Feel and payoff
Repositioning while staying free to act: attack, shield or grab out of a slide. Players locate the skill in spacing, choosing the angle and the follow-up, more than in the input itself. [Community consensus]
```
