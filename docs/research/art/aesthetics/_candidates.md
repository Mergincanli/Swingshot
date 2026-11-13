# Game-wide candidates

Findings that may hold for the whole game, each with its status per character. This is the only place the list lives: character docs name the candidate IDs they support or break and link here.

A candidate is promoted to its own doc in this folder, with the art-style-aesthetics-synthesis skill, when it holds for three or more characters or when an official or breakdown source states it.

One `## ID. Statement` section per candidate, with these fields:

- Side: shape (the model and its textures) or rendering (what the game's renderer adds)
- Outcome: open; promoted, with a link to the doc; or dropped, with the reason
- Holds for: how many of the characters checked
- One line per character: Holds, Breaks or Not observable, a qualifier where needed, and the evidence tag

IDs are never reused or renumbered.

Characters checked so far: Amber, Xilonen. In each character's line, `[viewer: ...]` and `[shot: ...]` use that character doc's own view and shot names, and `[doc: name, axis]` says where in the doc the evidence sits.

## C1. Stitches, seams, creases and trim edges are painted into the base-colour texture

- Side: shape
- Outcome: open
- Holds for: 2 of 2
- Amber: Holds. [viewer: B outfit front, B outfit back] [doc: amber, axis 6]
- Xilonen: Holds. [viewer: B front, B back] [doc: xilonen, axis 6]

## C2. Textures hold hand-painted darker shapes at folds and overhangs

- Side: shape
- Outcome: open
- Holds for: 1 of 2
- Amber: Holds. The same darker fold shapes show under both viewers' lighting. [viewer: B outfit front] [doc: amber, axes 7 and 10] A recreation states that hand-painted shadows are baked into the character textures. [breakdown: [bjayers](https://bjayers.artstation.com/blog/category/5)]
- Xilonen: Not observable. No clear fold shapes at the size of the views. [viewer: B front] [doc: xilonen, axis 7]

## C3. The face is nearly featureless geometry, shaded by a light-direction mask

- Side: shape for the geometry, rendering for the mask
- Outcome: open
- Holds for: 2 of 2 for the geometry; 0 of 2 for the mask
- Amber: Holds for the geometry. [viewer: A Face] [doc: amber, axis 2] The mask is Not observable; the developer describes it. [official: [Famitsu's report of the GDC 2021 talk](https://www.famitsu.com/news/202107/23228135.html)]
- Xilonen: Holds for the geometry, with slightly raised lips. [viewer: A Face] [doc: xilonen, axis 2] The mask is Not observable.

## C4. Eye highlights are painted and placed the same way in both eyes

- Side: shape
- Outcome: open
- Holds for: 2 of 2
- Amber: Holds. Two highlights per iris, on the same side in both eyes. [viewer: A Face, A 1/4 Face, A 3/4 Face] [doc: amber, axis 3]
- Xilonen: Holds. One highlight per iris, at the top centre of both. [viewer: A Face, A 1/4 Face, A 3/4 Face] [doc: xilonen, axis 3]

## C5. Hair is a cap plus thick pointed clumps with painted strand lines and gradient

- Side: shape
- Outcome: open
- Holds for: 2 of 2
- Amber: Holds. Straight locks and a slight crown-to-tip shift. [viewer: B back] [doc: amber, axis 4]
- Xilonen: Holds. Curled clumps, braids modelled as geometry and a three-stop gradient. [viewer: B back] [doc: xilonen, axis 4]

## C6. Gold metal is a desaturated khaki with flat facets

- Side: shape
- Outcome: open
- Holds for: 2 of 2
- Amber: Holds. About `#BFAB86`. [viewer: B outfit front] [doc: amber, axes 8 and 10]
- Xilonen: Holds. About `#AB9873`. [viewer: B front] [doc: xilonen, axes 8 and 10]

## C7. Every garment edge is marked by contrast

- Side: shape
- Outcome: open
- Holds for: 2 of 2
- Amber: Holds, as trim bands and hard colour changes. [viewer: B outfit front, B outfit back] [doc: amber, axis 7]
- Xilonen: Holds, as a frayed fringe, a printed cuff, plates and pendants. The fringe and rips are irregular edges, not bands. [viewer: B front, A Front] [doc: xilonen, axis 7]

## C8. Palette: dark low-saturation base, one saturated colour, white, small gold accent

- Side: shape
- Outcome: open
- Holds for: 1 of 2
- Amber: Holds. [viewer: B front] [doc: amber, axis 10]
- Xilonen: Breaks. Skin is the largest area and several saturated hues sit side by side. [viewer: B front, A Front] [doc: xilonen, axis 10]

## C9. Shadow tones shift hue and are set per character, not just darkened

- Side: rendering
- Outcome: open
- Holds for: 1 of 2
- Amber: Holds for the hue shift, on the white boots in dim light. [shot: ingame-back] [doc: amber, axis 10] That shadow colours are set per character comes from a recreation. [breakdown: [bjayers](https://bjayers.artstation.com/blog/category/5)]
- Xilonen: Not observable. No in-game shot. [doc: xilonen, axis 10]

## C10. A character does not cast shadows on itself and goes fully into shade, not partly

- Side: rendering
- Outcome: open
- Holds for: 0 of 2
- Amber: Not observable. In daylight, face and thigh each read as one flat tone, which fits the claim but does not test it. [shot: ingame-front] [doc: amber, axis 5] A recreation states it. [breakdown: [bjayers](https://bjayers.artstation.com/blog/category/5)]
- Xilonen: Not observable. No in-game shot. [doc: xilonen, axis 5]

## C11. Outline colour follows the local material and is not black

- Side: rendering
- Outcome: open
- Holds for: 1 of 2
- Amber: Holds, on hair and skin. The line samples as dark wine around the hair, warm brown at the jaw and dark brown beside the thigh; none is black. [shot: ingame-front, ingame-back] [doc: amber, axis 6] A recreation notes that some game materials tint the outline to match. [breakdown: [bjayers](https://bjayers.artstation.com/blog/category/5)]
- Xilonen: Not observable. No in-game shot. [doc: xilonen, axis 6]

## C12. An even-width light rim runs along silhouette edges

- Side: rendering
- Outcome: open
- Holds for: 1 of 2, in part
- Amber: Holds in part, on the white boots in one still. A lighter strip sits just inside the outline on the same side of both boots; the other side and other materials were not sampled. [shot: ingame-front] [doc: amber, axis 5] One recreation says the rim does not follow the mesh shape [breakdown: [bjayers](https://bjayers.artstation.com/blog/category/5)]; another builds it in screen space from depth. [breakdown: [Adrian Mendez](https://adrianmendez.artstation.com/projects/wJZ4Gg)]
- Xilonen: Not observable. No in-game shot. [doc: xilonen, axis 5]

## C13. The body is symmetric; asymmetry comes from one-sided accessories

- Side: shape
- Outcome: open
- Holds for: 2 of 2
- Amber: Holds. Four one-sided items on an otherwise mirror-symmetric design. [viewer: B front, B back] [doc: amber, axis 8]
- Xilonen: Holds. More than a dozen one-sided items. [viewer: B front, B back] [doc: xilonen, axis 8]

## C14. Detail sits in clusters separated by large plain areas of cloth or skin

- Side: shape
- Outcome: open
- Holds for: 2 of 2
- Amber: Holds. Five clusters; the plain areas are cloth and hair. [viewer: A Front, B front] [doc: amber, axis 8]
- Xilonen: Holds. Five clusters; the plain areas are mostly bare skin. [viewer: B front, B back] [doc: xilonen, axis 8]

## C15. Eye recipe: thick upper lash band with a wing and one upward spike, iris darker at the top, grey band on the white

- Side: shape
- Outcome: open
- Holds for: 2 of 2
- Amber: Holds. [viewer: A Face, B front] [doc: amber, axis 3]
- Xilonen: Holds, with lashes in two colours and a slit pupil. [viewer: A Face, B front] [doc: xilonen, axis 3]

## C16. No pure black; the darkest values sit at about 20–25%

- Side: shape
- Outcome: open
- Holds for: 2 of 2
- Amber: Holds. Darkest areas at 20–24% value, mostly leaning red. [viewer: B front] [doc: amber, axis 10]
- Xilonen: Holds. Darkest areas at 20–25% value, close to neutral. [viewer: B front, A Front] [doc: xilonen, axis 10]
