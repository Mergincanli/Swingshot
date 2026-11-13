# Game-wide candidates

Findings that may hold for the whole game, each with its status per character. This is the only place the list lives: character docs name the candidate IDs they support or break and link here.

A candidate is promoted to its own doc in this folder, with the art-style-aesthetics-synthesis skill, when it holds for three or more characters or when an official or breakdown source states it.

One `## ID. Statement` section per candidate, with these fields:

- Side: shape (the model and its textures) or rendering (what the game's renderer adds)
- Outcome: open; promoted, with a link to the doc; or dropped, with the reason
- Holds for: how many of the characters checked
- One line per character: Holds, Breaks or Not observable, a qualifier where needed, and the evidence tag

IDs are never reused or renumbered.

Characters checked so far: Amber, Xilonen, Clorinde, Navia. In each character's line, `[viewer: ...]` and `[shot: ...]` use that character doc's own view and shot names, and `[doc: name, axis]` says where in the doc the evidence sits.

## C1. Stitches, seams, creases and trim edges are painted into the base-colour texture

- Side: shape
- Outcome: promoted to [painted-lines-and-fold-shapes.md](painted-lines-and-fold-shapes.md)
- Holds for: 4 of 4
- Amber: Holds. [viewer: B outfit front, B outfit back] [doc: amber, axis 6]
- Xilonen: Holds. [viewer: B front, B back] [doc: xilonen, axis 6]
- Clorinde: Holds. Blouse, sleeve and glove seams, pleat stripes and cloth patterns. [viewer: B outfit front, B back] [doc: clorinde, axis 6]
- Navia: Holds. Boot lacing, pleat lines, lace patterns and embroidery scrolls. [viewer: B front, B back, A Footwear] [doc: navia, axis 6]

## C2. Textures hold hand-painted darker shapes at folds and overhangs

- Side: shape
- Outcome: promoted to [painted-lines-and-fold-shapes.md](painted-lines-and-fold-shapes.md)
- Holds for: 3 of 4
- Amber: Holds. The same darker fold shapes show under both viewers' lighting. [viewer: B outfit front] [doc: amber, axes 7 and 10] A recreation states that hand-painted shadows are baked into the character textures. [breakdown: [bjayers](https://bjayers.artstation.com/blog/category/5)]
- Xilonen: Not observable. No clear fold shapes at the size of the views. [viewer: B front] [doc: xilonen, axis 7]
- Clorinde: Holds. Small fold shapes beside the blouse buttons and a fold line on each boot cuff show under both viewers' lighting. [viewer: B outfit front, A Face, B front] [doc: clorinde, axes 6 and 7]
- Navia: Holds. Rows of rounded ruffle shapes in a darker yellow along the skirt tails show under both viewers' lighting. [viewer: B back, A Back] [doc: navia, axes 6 and 10]

## C3. The face is nearly featureless geometry, shaded by a light-direction mask

- Side: shape for the geometry, rendering for the mask
- Outcome: open
- Holds for: 4 of 4 for the geometry; 0 of 4 for the mask
- Amber: Holds for the geometry. [viewer: A Face] [doc: amber, axis 2] The mask is Not observable; the developer describes it. [official: [Famitsu's report of the GDC 2021 talk](https://www.famitsu.com/news/202107/23228135.html)]
- Xilonen: Holds for the geometry, with slightly raised lips. [viewer: A Face] [doc: xilonen, axis 2] The mask is Not observable.
- Clorinde: Holds for the geometry. [viewer: A Face, B side] [doc: clorinde, axis 2] The mask is Not observable.
- Navia: Holds for the geometry. [viewer: A Face, B side] [doc: navia, axis 2] The mask is Not observable.

## C4. Eye highlights are painted and placed the same way in both eyes

- Side: shape
- Outcome: open
- Holds for: 4 of 4
- Amber: Holds. Two highlights per iris, on the same side in both eyes. [viewer: A Face, A 1/4 Face, A 3/4 Face] [doc: amber, axis 3]
- Xilonen: Holds. One highlight per iris, at the top centre of both. [viewer: A Face, A 1/4 Face, A 3/4 Face] [doc: xilonen, axis 3]
- Clorinde: Holds. One white crescent at the bottom centre of both irises. [viewer: A Face, A 1/4 Face, A 3/4 Face, B front] [doc: clorinde, axis 3]
- Navia: Holds. Two highlights per iris, a white star and a cyan oval, on the same sides in both eyes. [viewer: A Face, A 1/4 Face, A 3/4 Face, B front] [doc: navia, axis 3]

## C5. Hair is a cap plus thick pointed clumps with painted strand lines and gradient

- Side: shape
- Outcome: open
- Holds for: 4 of 4 for the cap, the clumps and the strand lines; 2 of 4 for the gradient
- Amber: Holds. Straight locks and a slight crown-to-tip shift. [viewer: B back] [doc: amber, axis 4]
- Xilonen: Holds. Curled clumps, braids modelled as geometry and a three-stop gradient. [viewer: B back] [doc: xilonen, axis 4]
- Clorinde: Holds for the cap, the clumps and the strand lines: long thin locks and one tail. No root-to-tip gradient; one lock is a lighter blue. [viewer: B front, B back] [doc: clorinde, axis 4]
- Navia: Holds for the cap, the clumps and the strand lines: large fringe locks, and ringlets modelled as spiral ribbons. No root-to-tip gradient. [viewer: B front, B back] [doc: navia, axis 4]

## C6. Gold metal is a desaturated khaki with flat facets

- Side: shape
- Outcome: open
- Holds for: 4 of 4
- Amber: Holds. About `#BFAB86`. [viewer: B outfit front] [doc: amber, axes 8 and 10]
- Xilonen: Holds. About `#AB9873`. [viewer: B front] [doc: xilonen, axes 8 and 10]
- Clorinde: Holds. About `#837464`, darker and greyer. [viewer: B front, B back] [doc: clorinde, axes 8 and 10]
- Navia: Holds. About `#B79F7F`. [viewer: B front] [doc: navia, axes 8 and 10]

## C7. Every garment edge is marked by contrast

- Side: shape
- Outcome: open
- Holds for: 4 of 4
- Amber: Holds, as trim bands and hard colour changes. [viewer: B outfit front, B outfit back] [doc: amber, axis 7]
- Xilonen: Holds, as a frayed fringe, a printed cuff, plates and pendants. The fringe and rips are irregular edges, not bands. [viewer: B front, A Front] [doc: xilonen, axis 7]
- Clorinde: Holds, as gold borders, white cuffs, rows of tassels and brighter linings. [viewer: B outfit front, B back] [doc: clorinde, axis 7]
- Navia: Holds, as gold piping, gold bands, cream bands, lace hems and painted ruffles. The lace hems have cut-out holes. [viewer: B front, B back] [doc: navia, axis 7]

## C8. Palette: dark low-saturation base, one saturated colour, white, small gold accent

- Side: shape
- Outcome: open
- Holds for: 3 of 4
- Amber: Holds. [viewer: B front] [doc: amber, axis 10]
- Xilonen: Breaks. Skin is the largest area and several saturated hues sit side by side. [viewer: B front, A Front] [doc: xilonen, axis 10]
- Clorinde: Holds. A charcoal and navy base, one blue-violet family at 38–48% saturation, white, and gold at 8% of the front view. Gold rises to 16% from behind, and sheer tights add a fifth tone. [viewer: B front, B back] [doc: clorinde, axis 10]
- Navia: Holds. A base of near-black, brown-black and navy, one yellow at 54–57% saturation, white, and gold. The yellow sits mostly behind the figure, and pale blonde hair is a second large light area. [viewer: B front, B back] [doc: navia, axis 10]

## C9. Shadow tones shift hue and are set per character, not just darkened

- Side: rendering
- Outcome: open
- Holds for: 1 of 4
- Amber: Holds for the hue shift, on the white boots in dim light. [shot: ingame-back] [doc: amber, axis 10] That shadow colours are set per character comes from a recreation. [breakdown: [bjayers](https://bjayers.artstation.com/blog/category/5)]
- Xilonen: Not observable. No in-game shot. [doc: xilonen, axis 10]
- Clorinde: Not observable. No in-game shot. [doc: clorinde, axis 10]
- Navia: Not observable. No in-game shot. [doc: navia, axis 10]

## C10. A character does not cast shadows on itself and goes fully into shade, not partly

- Side: rendering
- Outcome: open
- Holds for: 0 of 4
- Amber: Not observable. In daylight, face and thigh each read as one flat tone, which fits the claim but does not test it. [shot: ingame-front] [doc: amber, axis 5] A recreation states it. [breakdown: [bjayers](https://bjayers.artstation.com/blog/category/5)]
- Xilonen: Not observable. No in-game shot. [doc: xilonen, axis 5]
- Clorinde: Not observable. No in-game shot. [doc: clorinde, axis 5]
- Navia: Not observable. No in-game shot. [doc: navia, axis 5]

## C11. Outline colour follows the local material and is not black

- Side: rendering
- Outcome: open
- Holds for: 1 of 4
- Amber: Holds, on hair and skin. The line samples as dark wine around the hair, warm brown at the jaw and dark brown beside the thigh; none is black. [shot: ingame-front, ingame-back] [doc: amber, axis 6] A recreation notes that some game materials tint the outline to match. [breakdown: [bjayers](https://bjayers.artstation.com/blog/category/5)]
- Xilonen: Not observable. No in-game shot. [doc: xilonen, axis 6]
- Clorinde: Not observable. No in-game shot. [doc: clorinde, axis 6]
- Navia: Not observable. No in-game shot. [doc: navia, axis 6]

## C12. An even-width light rim runs along silhouette edges

- Side: rendering
- Outcome: open
- Holds for: 1 of 4, in part
- Amber: Holds in part, on the white boots in one still. A lighter strip sits just inside the outline on the same side of both boots; the other side and other materials were not sampled. [shot: ingame-front] [doc: amber, axis 5] One recreation says the rim does not follow the mesh shape [breakdown: [bjayers](https://bjayers.artstation.com/blog/category/5)]; another builds it in screen space from depth. [breakdown: [Adrian Mendez](https://adrianmendez.artstation.com/projects/wJZ4Gg)]
- Xilonen: Not observable. No in-game shot. [doc: xilonen, axis 5]
- Clorinde: Not observable. No in-game shot. [doc: clorinde, axis 5]
- Navia: Not observable. No in-game shot. [doc: navia, axis 5]

## C13. The body is symmetric; asymmetry comes from one-sided accessories

- Side: shape
- Outcome: open
- Holds for: 4 of 4
- Amber: Holds. Four one-sided items on an otherwise mirror-symmetric design. [viewer: B front, B back] [doc: amber, axis 8]
- Xilonen: Holds. More than a dozen one-sided items. [viewer: B front, B back] [doc: xilonen, axis 8]
- Clorinde: Holds. Seven one-sided items, among them a drape and a banner on the left and a cord with a tassel on the right. [viewer: B front, B back] [doc: clorinde, axis 8]
- Navia: Holds. The hat trim, a glove on the right hand only, the forearm ornaments and the shoulder-bow ornaments differ between the sides. [viewer: B front, B side, A Front Detail] [doc: navia, axis 8]

## C14. Detail sits in clusters separated by large plain areas of cloth or skin

- Side: shape
- Outcome: open
- Holds for: 4 of 4
- Amber: Holds. Five clusters; the plain areas are cloth and hair. [viewer: A Front, B front] [doc: amber, axis 8]
- Xilonen: Holds. Five clusters; the plain areas are mostly bare skin. [viewer: B front, B back] [doc: xilonen, axis 8]
- Clorinde: Holds. Seven clusters; the plain areas are the sleeves, the skirt, the tights, the drape and the hair. [viewer: B front, B back] [doc: clorinde, axis 8]
- Navia: Holds. Seven clusters; the plain areas are the hair, the bare shoulders, the front skirt and the large yellow panels. Ornament is denser than on the other three. [viewer: B front, B back] [doc: navia, axis 8]

## C15. Eye recipe: thick upper lash band with a wing and one upward spike, iris darker at the top, grey band on the white

- Side: shape
- Outcome: open
- Holds for: 3 of 4, and 1 in part
- Amber: Holds. [viewer: A Face, B front] [doc: amber, axis 3]
- Xilonen: Holds, with lashes in two colours and a slit pupil. [viewer: A Face, B front] [doc: xilonen, axis 3]
- Clorinde: Holds in part. A thick lash band, an iris darker at the top and a grey band on the white; no upward spike in any view. [viewer: A Face, A 3/4 Face, B front] [doc: clorinde, axis 3]
- Navia: Holds, with red-brown strokes over the inner half of the lash band. [viewer: A Face, B front] [doc: navia, axis 3]

## C16. No pure black; the darkest values sit at about 20–25%

- Side: shape
- Outcome: open
- Holds for: 4 of 4
- Amber: Holds. Darkest areas at 20–24% value, mostly leaning red. [viewer: B front] [doc: amber, axis 10]
- Xilonen: Holds. Darkest areas at 20–25% value, close to neutral. [viewer: B front, A Front] [doc: xilonen, axis 10]
- Clorinde: Holds. Darkest areas at 22–27% value, leaning blue. [viewer: B front] [doc: clorinde, axis 10]
- Navia: Holds. Darkest cloth at 22–27% value, in neutral, warm and cool darks. The lash band is darker, at about 18%. [viewer: B front, A Face] [doc: navia, axis 10]

## C17. Hair highlights are flat, hard-edged marks painted for the hair, not a soft sheen

- Side: shape for the painted marks, rendering for the highlight they would drive
- Outcome: open
- Holds for: 0 of 4. Not observable in-game; the viewers disagree on whether the marks are there or on how strong they are, and a viewer is not evidence for highlights
- Amber: Not observable. Neither viewer shows hard-edged marks; the phoshco sheet shows a soft pale band across the back of the head, read there as viewer lighting. [viewer: A Back of Head] [doc: amber, axis 4] A recreation reports that shine marks painted in the hair textures mask a real-time specular highlight. [breakdown: [bjayers](https://bjayers.artstation.com/blog/category/5)]
- Xilonen: Not observable. Small flat marks sit on the fringe and in a row on the back of the head; whether they are ornaments or painted highlights is unverified. [viewer: B front, B back] [doc: xilonen, axis 4]
- Clorinde: Not observable. The phoshco sheet draws a row of crisp white jagged marks round the crown and a few low on the tail; the other viewer draws none there. [viewer: A Back of Head, A Back Detail, B back] [doc: clorinde, axis 4]
- Navia: Not observable. Both viewers show lighter marks on the fringe and the ringlets, in the same places: white with jagged ends in the phoshco sheet, a paler blonde with softer edges in the other viewer. [viewer: A Face, A Back Detail, B front, B back] [doc: navia, axis 4]

## C18. Build: about seven head-heights tall with shoes included, legs a little over half the height

- Side: shape
- Outcome: open
- Holds for: 3 of 4, and 1 in part. All four are women; no man or child has been checked
- Amber: Holds. 6.9 head-heights; legs, crotch to sole, 54%. [viewer: A Front] [doc: amber, axis 1]
- Xilonen: Holds. 7.4 head-heights including platform shoes; legs, crotch to sole, 56%. [viewer: A Front] [doc: xilonen, axis 1]
- Clorinde: Holds. About 7.0 head-heights with high heels, between 6.7 and 7.3 because the hat hides the top of the head; legs below the skirt hem 53%. [viewer: A Side] [doc: clorinde, axis 1]
- Navia: Holds in part. Legs below the skirt hem take about 54% of the height. Head-heights cannot be measured, because the hat hides the top of the head in every view; an estimate gives about 7.3, between 6.9 and 8.1. [viewer: A Front] [doc: navia, axis 1]
