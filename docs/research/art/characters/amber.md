# Amber (Genshin Impact)

Outfit: 5-Star Outrider, her default outfit. [community: S5] Neither viewer page names the outfit it shows. The match rests on four visible features: brown shorts with small side slits, brown gloves, a dark corset and a dark hip pouch. [viewer: B front] A press comparison lists exactly these as the original design that the alternate outfit, 100% Outrider, changed. [community: S6]

Game version or shot date: Viewer captures made on 13 November 2026. The game version the viewer models come from is unverified. The two in-game stills carry no date or version.

Confidence: Shape only. Two found in-game stills exist, but their source, version, platform and settings are unknown and the figure in them is under 800 px tall. They are used as a cross-check only. Every statement taken from them is marked "Provisional" and no brief rule rests on them.

Shots used:
- Viewer sheet A: 16 labelled views (Front, 3/4 Front, 1/4 Front, Side, 3/4 Back, 1/4 Back, Back, Face, 1/4 Face, 3/4 Face, Footwear, Front Detail, 3/4 Front Detail, Back Detail, 3/4 Back Detail, Back of Head). Bind pose, red backdrop, viewer lighting. Tagged `[viewer: A <view>]`.
- Viewer captures B: four captures (front, back, outfit front, outfit back; the last two show the clothing on a blank mannequin). Bind pose, white backdrop, viewer lighting. Tagged `[viewer: B <view>]`.
- In-game stills: `ingame-front` (daylight, standing in grass, no HUD) and `ingame-back` (dim light, HUD visible). Tagged `[shot: <name>]`.

Links and capture details are in [references/shots.md](../references/shots.md).

How each viewer differs from the in-game stills is recorded in [references/viewers.md](../references/viewers.md).

## Production brief: Blender

Partial: shape only. These rules cover the model and its textures. There are no rules yet for outlines, shading bands, highlights, rim light or how materials respond to light.

1. Block out the body in an orthographic front view at about seven head-heights, with shoulders about one head wide and legs a little over half the height. (Axis 1)
2. Model the face as a smooth surface whose only clear relief is a small nose tip, and draw brows, lash lines, eyelid crease and mouth line in the face texture. (Axis 2)
3. Paint each iris, its pupil mark and its two highlights into the eye texture in Texture Paint, with the highlights on the same side in both eyes, not mirrored. (Axis 3)
4. Build hair from a smooth cap plus a few thick, tapered clumps with pointed tips, and paint strand lines and a darker-crown-to-lighter-tip gradient onto them instead of modelling strands. (Axis 4)
5. Draw stitches, seams, crease marks and trim edges as thin dark strokes on the base-colour texture in Texture Paint, and keep them out of the mesh. (Axis 6)
6. End every garment piece with a trim band or a hard colour change, and model the largest trims, such as cuff bands and boot tops, as raised geometry. (Axis 7)
7. Group ornament into a few clusters (head, neck and chest, belt line, boot tops) and leave sleeves, shorts and lower legs plain. (Axis 8)
8. Model the body and main garments with a Mirror modifier, then add accessories that exist on one side only as separate, unmirrored objects. (Axis 8)
9. Give each material region one flat base colour, and build the palette from a dark, low-saturation family over roughly half the figure, one saturated signature colour, white, and a metal accent under a tenth of the area. (Axis 10)
10. Paint metal accents as a desaturated khaki-gold, around 30% saturation and 70–78% value, with lighter and darker flat facets, not as saturated yellow. (Axis 10)

Sources for this brief:
- Orthographic view: [Blender Manual, Perspective/Orthographic](https://docs.blender.org/manual/en/latest/editors/3dview/navigate/projections.html)
- Texture Paint: [Blender Manual, Texture Paint introduction](https://docs.blender.org/manual/en/latest/sculpt_paint/texture_paint/introduction.html)
- Mirror modifier: [Blender Manual, Mirror Modifier](https://docs.blender.org/manual/en/latest/modeling/modifiers/generate/mirror.html)

## Production brief: Three.js / WebGPU

Partial: shape only. The model and textures are authored elsewhere; these rules cover what the runtime must keep intact. There are no rules yet for shading, outlines or lighting.

1. Check proportions through an `OrthographicCamera`, because a close perspective camera changed the measured height from 6.9 to 5.7 head-heights between the two viewers. (Axis 1)
2. Set `colorSpace = SRGBColorSpace` on every base-colour texture so the flat colours display as authored. (Axis 10)
3. Take stitches, seams and crease marks from the base-colour map, and do not generate them with an edge-detection pass. (Axis 6)
4. Keep both eye highlights in the eye's base-colour map, and do not add a specular or reflection highlight to the eye material. (Axis 3)
5. Render hair clumps as opaque geometry with no alpha fade at the tips. (Axis 4)

Sources for this brief:
- Orthographic camera: [three.js docs, OrthographicCamera](https://threejs.org/docs/pages/OrthographicCamera.html)
- Texture colour space: [three.js manual, Color Management](https://threejs.org/manual/pages/color-management.html) and [three.js docs, Texture](https://threejs.org/docs/pages/Texture.html)

## Dissection

Left and right are the character's own. Measurements and colour values are approximate.

### 1. Silhouette and proportions

Observation:
- Height is about 6.9 head-heights from the top of the hair to the soles, bow excluded (head 98 px, figure 676 px). [viewer: A Front]
- The same measure gives 5.7 in B front (head 180 px, figure 1029 px). [viewer: B front] That capture is not used for proportions: its camera appears to sit close and look down, which enlarges the head. [inferred]
- The bow adds about 0.4 head-height on top. [viewer: A Front]
- Shoulders are about as wide as the head with its hair. The waist is about 0.4 head wide. [viewer: A Front]
- Legs, crotch to sole, take about 54% of the height. [viewer: A Front]
- Head silhouette: a round hair mass, two long upright bow loops, and two small tufts sticking out sideways at ear level. [viewer: A Front, B back]
- Torso silhouette: slim, with sleeves that end in cuffs wider than the upper arm. [viewer: B outfit front]
- Hair reaches the belt at the back and fans into pointed locks. [viewer: B back]
- Legs read as one long, smooth shape from mid-thigh to toe. [viewer: A Front]
- Hip accessories break the outline on both sides: a tall case on the right thigh, and on the left a pouch plus a hanging tassel that ends just below the top of the white boot. [viewer: A Front, B front]
- Provisional: in idle pose the arms hang and the sleeves read as wide bells, so the outline is narrower than in bind pose. Height is at least 6.3 head-heights down to the ankle; grass hides the feet. [shot: ingame-front]

Technique: Proportions belong to the mesh. [inferred] The developer describes character models as built from three-view drawings to shared standards for tessellation, topology and textures. [official: S1]

### 2. Head and face construction

Observation:
- The face is a smooth surface with almost no modelled features. The nose is a small point, visible in profile, with no bridge line or nostrils. [viewer: A Side, A Face]
- The mouth is a short line with barely raised lips. [viewer: A Face, B front]
- The chin is small and pointed, the cheeks full, and the jaw has no visible angle. [viewer: A Face, A 3/4 Face]
- The eyes sit low: their centre is about 60–65% of the way down from hair top to chin. [viewer: A Front, A Face]
- Each eye, lash wings included, is about a third of the face width. The gap between the eyes is about one eye-width. [viewer: A Face]
- Eyebrows are thin, short, dark lines, mostly covered by the fringe. [viewer: A Face, B front]
- A faint pink tint sits under each eye, strongest toward the outer corner. [viewer: B front]
- Ears are small, simple and mostly hidden by hair. [viewer: A 3/4 Face]
- Whether brows or eyes show through the hair in-game: Not observable. An in-game face close-up would resolve it.
- Face shading: Not observable. In-game face shots lit from the front and from the side would resolve it.
- Provisional: viewer B's lighting shows lip and nose volume as soft shading, while the in-game face is one flat tone with a single small highlight dot on the nose and a short mouth line. [viewer: B front] [shot: ingame-front]

Technique:
- Brows, lash lines and mouth line are drawn in the face texture. [inferred]
- The developer says standard shading could not give the wanted face, so faces use a dedicated shadow mask that responds to light direction. [official: S1]
- Third-party recreations describe the same idea: a face shadow texture whose channels cover light angles 0–180° and 180–360° [breakdown: S3], and a custom face light map in place of edited normals. [breakdown: S4]

### 3. Eyes

Observation:
- Upper lash: a thick dark band that tapers to a pointed wing at the outer corner, with one upward spike about a third of the way in from the outer corner. [viewer: A Face, B front]
- The outer corner carries a red-brown tint, and the lower outer edge is drawn in orange-red. [viewer: A Face]
- A thin crease line sits above the lash, and a thin, short line marks the lower lid. [viewer: A Face, B front]
- The white of the eye has a grey band under the upper lash. [viewer: A Face]
- Iris: a tall oval cut off by the upper lash, with a darker ring at its edge. It is dark red-brown at the top, grades to orange, and has a bright yellow rounded patch in the lower centre. A small dark vertical mark stands for the pupil. [viewer: A Face, B front]
- Each iris has two highlights: a larger round white dot at upper image-right and a smaller pink oval at upper image-left. [viewer: A Face]
- The highlights sit on the same side in both eyes, not mirrored, and stay in place across three camera angles. [viewer: A Face, A 1/4 Face, A 3/4 Face]
- The iris is about 35 px wide in the largest view, so finer detail is Not observable. An in-game face close-up would resolve it.
- Provisional: in-game the irises read yellower than in either viewer. [shot: ingame-front]

Technique: Iris, lashes and highlights are painted in a texture, since the highlights do not move with the viewer's camera. [inferred] Whether the game shades the eyes or adds a moving highlight: Not observable. In-game face close-ups from two angles would resolve it.

### 4. Hair: shape language, clumps, highlight, shadow

Observation:
- A smooth cap covers the skull. [viewer: B back, A Back of Head]
- The fringe is five to seven large, flat, pointed clumps. The central clump crosses the bridge of the nose and ends in a forked point between the eyes. [viewer: B front, A Face]
- Side locks frame the face down to jaw level and end in points. [viewer: B front]
- At the back the hair is one mass to the shoulder blades, then splits into eight to ten thick, tapered locks with pointed tips. The outer locks flick outward. [viewer: B back, A Back]
- Thin darker lines run along the clumps and separate them. There are no individual strands. [viewer: B front, B back]
- Clump edges are crisp, with no fade at the tips. [viewer: B back]
- Base colour is a dark, low-saturation brown: about `#4F3F3F` at the crown and about `#634C44`, lighter and warmer, in the lower lengths. [viewer: B front, B back] The same crown-to-tip shift shows under viewer A's different lighting. [viewer: A Back Detail]
- A red hairband with a thin gold edge carries the bow. [viewer: B front, A 3/4 Face]
- Highlight shape, shadow tone and whether the highlight moves with the camera: Not observable. Two in-game hair close-ups from different camera heights, in daylight, would resolve it.
- Viewer A shows a soft pale band across the back of the head. That is the viewer's lighting and is not evidence. [viewer: A Back of Head]
- Provisional: in-game the hair reads as a dark wine-brown, about `#5A2D3A`, redder and more saturated than the viewers' base colour. [shot: ingame-front]

Technique:
- Hair is built from solid clumps, with strand lines and the crown-to-tip gradient painted on. [inferred]
- One recreation reports that shine marks painted in the hair textures mask a real-time specular highlight. [breakdown: S4] Another shows the highlight only where the hair is lit and trims it at the sides with a view-dependent term. [breakdown: S3] Neither is observed on Amber.

### 5. Skin: tone, shading bands, rim light

Observation:
- Base tone is very pale and warm, about `#FFEDD7` on cheek and thigh. [viewer: B front]
- Skin shows on the face, neck, upper chest, wrists and a band of thigh. [viewer: A Front]
- Shading bands and rim light: Not observable. In-game shots in direct sun and in shade would resolve it.
- Provisional: the face is one flat tone, about `#F5CCB0`. The neck is slightly darker and more saturated, about `#F5BFA1`, and meets the face at a hard edge under the jaw. The thigh is one flat tone across its width. [shot: ingame-front]

Technique: Unverified. See candidates C9 and C10 under Comparison.

### 6. Outlines and inner lines

Observation:
- Outlines: Not observable. Neither viewer draws one. [viewer: A Front, B front] In-game front, side and back shots at two distances would show where outlines appear, how thick they are and where they vanish.
- Provisional: a thin dark line surrounds the whole silhouette and separates overlapping parts. It is about 2 px wide where the figure is at least 724 px tall, roughly 0.3% of figure height. [shot: ingame-front]
- Provisional: the line's colour follows what it borders. It samples as dark wine, about `#462638`, around the hair, and as warm brown, about `#B2785E`, at the jaw. No sampled line is pure black. [shot: ingame-front]
- Lines drawn onto the surface:
  - Dashed stitches: dark dashes along each sleeve and around the armhole, cream dashes along the corset seams, dashes on the pocket flaps. [viewer: B outfit front, B outfit back]
  - Seams and edges: dark lines along the hood seams, the shorts' centre seam, the pocket outlines and the belt edges, and a lighter line just inside the shorts hem. [viewer: B outfit front, B outfit back]
  - Creases: two short tapered strokes at each knee, front and back. [viewer: B front, B back]
  - Trim edges: a thin dark line beside most gold trim, including the bow corners, hood trim and lacing frame. [viewer: B front, B outfit back]
  - Slot marks along the goggle rims. [viewer: B outfit front]
  - Hair strand lines, brows, lashes and mouth line, as covered in Axes 2 to 4. [viewer: B front]
- Provisional: the knee creases and corset seam lines stay visible in-game. [shot: ingame-front]

Technique:
- The surface lines are painted into the base-colour texture. [inferred]
- The outline method is unverified. Two third-party recreations use different methods and neither says which the game uses. One builds an inverted hull, a second back-facing shell slightly larger than the model, and notes that some game materials tint the outline to match. [breakdown: S4] The other detects edges in screen space from depth and normals and suppresses them on the face. [breakdown: S3]

### 7. Clothing: structure, layering, trim, how pieces end

Observation:
- Jacket: red, hooded and cropped. It ends at mid-back in a curved hem notched at the centre, stays open at the front, and has long sleeves. The hood lies flat on the upper back. [viewer: B outfit back, B outfit front]
- Cuffs: each sleeve ends in an oversized dark-brown cuff, wider than the sleeve and joined to it by a raised gold band. A tight near-black inner sleeve shows below the cuff. [viewer: B outfit front]
- Chest piece: white, with a dark-brown V-shaped collar band and a small gold ornament at its centre. [viewer: B outfit front] A white layer also shows at the back between the jacket hem and the corset. [viewer: B back]
- Corset: dark brown, from under the bust to the belt, with a shaped top edge. At the back it has a red laced panel framed in gold. [viewer: B outfit front, B outfit back]
- Belt: salmon-brown with darker loops. [viewer: B outfit back]
- Shorts: dark brown and short, with a notched slit on each side that shows a white lining with a zigzag edge, and two back pockets. [viewer: B outfit front, B outfit back]
- Boots: white and thigh-high. The top section is a red band. The white part starts at a gold-trimmed scalloped edge that rises to a point on the outer thigh. The heel is a small dark block; toe caps and sole rim are gold. [viewer: B front, B back, A Footwear]
- Gloves: dark brown with a red ribbed cuff and a gold plate on the back of the hand. [viewer: B back]
- Goggles: brass rims and dark-brown lenses, worn round the neck. [viewer: B outfit front]
- Bow: two long upright red loops. [viewer: B front]
- How pieces end: every piece ends in a contrasting band or a hard colour change. Examples are the gold band at the cuffs, the gold scalloped trim at the boot tops, the gold trim on the hood, the lighter line at the shorts hem and the red ribbing at the glove cuff. No edge is frayed, soft or faded. [viewer: B outfit front, B outfit back, B front]
- Cuff outlines are visibly polygonal, made of straight segments. [viewer: B outfit back]

Technique:
- Large forms and the main trims are geometry. Folds are few and painted: the same darker fold shapes on sleeves and hood show under both viewers' lighting. [inferred]
- One recreation says hand-painted shadows are baked into the character textures at seams, folds, under the arms and under the neck. [breakdown: S4]

### 8. Detail and ornament

Observation:
- Detail clusters in five places: the head (bow, eyes), the neck and chest (goggles, collar ornament, corset emblems), the belt line (ornaments, pouches, gem), the boot tops (gold trim and a gold winged ornament on the outer side) and the toes. [viewer: A Front, B front]
- Plain areas: the sleeves apart from one stitch line, the shorts, the hair lengths and the whole white length of the boots apart from the knee creases. [viewer: B front, B back]
- Asymmetry: four things break an otherwise mirror-symmetric design. [viewer: B front, B back]
  - A gold cross sits on the right bow loop only. [viewer: B front, B back]
  - A dark thigh strap with a gold buckle sits on the right leg only. [viewer: B front, B back]
  - A tall dark case hangs on the right thigh from a diagonal strap. Gold leaf-shaped ornaments mark where the strap meets the belt, front and back. [viewer: B front, B back]
  - The left hip carries a smaller pouch, a red gem and a tassel. [viewer: B front, B back]
- Emblems: two gold emblems on the corset's centre line, a large crest above a smaller winged shape; a gold chevron at the base of the hood; gold plates on both upper sleeves; gold triangular caps on both bow tips. [viewer: B outfit front, B outfit back, B front]
- Gems: one. A round red gem in a gold setting at the left hip, with a symbol inside. [viewer: B front, A Front Detail]
- Tassel: three or four long feather shapes hang below the gem. They are red with pale rib marks and fade to orange at the tips. [viewer: B back]
- Gold ornament carries lighter and darker flat facets. [viewer: B outfit front]
- Which emblems are raised and which are flat: Not observable. A close-up at a raking angle would resolve it.

Technique: Large trims are geometry; small ornament is painted or in low relief. [inferred]

### 9. Materials

Observation:
- How cloth, metal, leather, glass and the gem respond to light: Not observable. In-game close-ups of the goggles, gold trim, belt and gem in direct sun, from two camera angles, would resolve it.
- The viewers show only the painting underneath. Gold trim is painted in two or three flat tones. The goggle lenses are painted as a vertical gradient from dark brown to orange-brown. The gem is painted with a bright rim. [viewer: B outfit front, B front]
- Provisional: in-game the corset emblem samples at about `#B99C7F`, close in saturation and value to the viewer's `#BFAB86`, and the goggle rims carry brighter spots up to about `#F3CDAF`. [shot: ingame-front]

Technique: Unverified. One recreation describes metal as a matcap combined with a real-time specular term. [breakdown: S4] The other uses a matcap-style gradient lookup driven by the view and light directions. [breakdown: S3]

### 10. Colour

Observation: Base colours were sampled from B front and B back, the most evenly lit views. The viewer still lights the model, and the skin sample sits at full brightness, so highlights may be clipped. [viewer: B front, B back] Viewer A, sampled as a check, agrees on hue and reads darker: red `#872F34`, hair `#543D3D`, white `#DCD9D6`, skin `#ECD8C1`. [viewer: A Front]

| Role | Where | Approx. base colour | Saturation, value |
|---|---|---|---|
| Dominant: dark browns | Hair | `#4F3F3F` to `#634C44` | 20–31%, 31–39% |
| | Shorts, corset | `#5A4343`, `#523F3F` | 23–26%, 32–35% |
| | Cuffs, gloves | `#694B4B`, `#5D4545` | 26–29%, 36–41% |
| | Pouch, case | `#34302F`, `#3E3634` | 10–16%, 20–24% |
| Secondary: red | Jacket, bow, boot tops | `#A63F3F`, `#9E3B3B` | 62–63%, 62–65% |
| Secondary: white | Boots, chest piece | `#E5E2DF`, `#EAE6E4` | 3%, 90–92% |
| Skin | Cheek, thigh | `#FFEDD7` | 16%, 100% |
| Accent: gold | Trims, emblems | `#BFAB86`, facets up to `#C6B58B` | 27–30%, 67–78% |
| Accent | Belt | `#9B675D` | 40%, 61% |
| Accent | Tassel tips | `#DC9056` | 61%, 86% |
| Near-black | Inner sleeves | `#3B3A3E` | 6%, 24% |

- Area in bind pose, front view: dark browns 42%, white 19%, red 17%, gold 8%, skin 7%. Back view: dark browns 57%, white 17%, red 12%, gold 4%, skin 4%. [viewer: B front, B back]
- Saturation: only the red is strongly saturated. The browns sit at 20–30%. The gold is a desaturated khaki, not yellow. [viewer: B front]
- Black: there is no pure black. The darkest areas are the near-black inner sleeves and the brown-black pouch. [viewer: B front]
- White: slightly warm, and used for the two largest plain areas, the boots and the chest piece. [viewer: B front]
- Hue: every dark colour except the inner sleeves leans red, hue 0–15°, not neutral or blue. [viewer: B front, B back]
- Iris colour values: Not observable. The iris is too small to sample in every view; an in-game face close-up would resolve it.
- Lit tone and shadow tone per colour: Not observable. In-game shots of the same pose in direct sun and in shade would resolve it.
- The textures themselves hold a second, darker tone in places: red `#A63F3F` with `#953C3C` under the hood, and white `#EAE6E4` with `#CAC5C1` under the bust. [viewer: B front, B outfit front]
- Provisional, daylight still: red `#902126`, hair `#5A2D3A`, corset `#43262B`, white `#C0B5B4`, skin `#F5CCB0`. Against the viewer's base colours these are darker, more saturated and shifted toward red. The white reading suggests the figure is in shade or the still has a warm cast. [shot: ingame-front]
- Provisional, dim-light still: the white boots split into two flat tones with a hard edge, lit about `#A4A5A4` and shadow about `#756B78`. The shadow tone is cooler and leans purple; it is not just darker. [shot: ingame-back]

Technique: Each material region holds one flat base colour in the texture, with a few painted darker shapes. [inferred] One recreation reports that the game sets the colours on each side of the shadow edge per character with shadow ramps. [breakdown: S4] Unverified on Amber.

### 11. Weapon

Observation: Not observable. No view and no still shows a bow. An in-game shot with the bow in hand, one with it stowed if it stays visible, and the bow's name would resolve it.

Technique: Not observable, for the same reason.

### 12. Readability

Observation:
- From the front, four shapes identify her: the two upright bow loops on a round dark head, long dark hair to the belt, a red upper body, and long white legs under a red band. [viewer: A Front]
- From behind, hair hides most of the red. The bow, the red boot tops and the white legs carry the identity. [viewer: B back]
- Neighbouring blocks differ strongly in value: white at about 90%, red at about 65%, dark brown at about 31–35%. [viewer: B front]
- In motion: Not observable. Three frames of a run cycle would resolve it.
- At a distance: Not observable. An in-game shot with the figure small in frame would resolve it.
- Provisional: at about 430 px tall the bow, hair mass, red bands and white legs still separate clearly, while the gold detail no longer reads. [shot: ingame-back]

Technique: The large blocks are separated by value first and hue second. [inferred]

### 13. Fit with the world

Observation:
- Not observable. In-game shots in Mondstadt in daylight and in shade, with the figure small in frame, would resolve it.
- Provisional: against green grass, a blue-grey cliff and a pale building, her red and dark brown do not occur in the background, so the figure separates by hue as well as by outline. [shot: ingame-front]
- Provisional: in dim light on dark grass, the white legs and red bands stay the brightest and most saturated shapes in frame. [shot: ingame-back]

Technique:
- The developer says characters and scenes are rendered in separate passes, and that characters receive real-time light and ambient environment light, including cast shadows such as trees, through a 24-hour cycle. [official: S1]
- On console, characters get a directional ambient-occlusion effect computed from capsules that follow the skeleton. [official: S2]

## Comparison

### With other characters

None yet. This is the first doc in `characters/`.

### Game-wide candidates

These look game-wide but rest on one character. Nothing has been written to `aesthetics/`. Each candidate needs two more characters before it moves there.

- C1. Stitches, seams, creases and trim edges are painted into the base-colour texture. Basis: Axis 6. [viewer: B outfit front, B outfit back]
- C2. Textures hold hand-painted darker shapes at folds and overhangs. Basis: Axes 7 and 10. [viewer: B outfit front] [breakdown: S4]
- C3. The face is nearly featureless geometry, and its shading comes from a mask that responds to light direction. Basis: Axis 2. [viewer: A Face] [official: S1] Not yet observed in-game.
- C4. Eye highlights are painted, on the same side in both eyes. Basis: Axis 3. [viewer: A Face]
- C5. Hair is a cap plus a few thick pointed clumps, with painted strand lines and a crown-to-tip gradient. Basis: Axis 4. [viewer: B back]
- C6. Gold accents are a desaturated khaki with painted facets. Basis: Axes 8 and 10. [viewer: B outfit front]
- C7. Every garment piece ends in a trim band or a hard colour change. Basis: Axis 7. [viewer: B outfit front]
- C8. Palette structure: a dark, low-saturation base, one saturated signature colour, white, and a small gold accent. Basis: Axis 10. [viewer: B front]
- C9. Shadow tones shift hue and are set per character, not just darkened. Basis: Axis 10. [breakdown: S4] Provisional support. [shot: ingame-back]
- C10. A character does not cast shadows on itself and goes fully into shade, not partly. [breakdown: S4] Provisional support: the whole figure reads flat in the daylight still. [shot: ingame-front]
- C11. Outline colour follows the local material and is not black. [breakdown: S4] Provisional support. [shot: ingame-front]
- C12. A light rim of even width runs along silhouette edges. One recreation says it does not follow the mesh shape [breakdown: S4]; the other builds it in screen space from depth and states it is not a surface-angle effect. [breakdown: S3] Provisional support: a lighter strip, about `#E6CFC6` against `#C0B5B4`, sits just inside the outline on the same side of both boots. [shot: ingame-front]

## Sources

- S1. [Famitsu report (in Japanese) of miHoYo's GDC 2021 talk "'Genshin Impact': Crafting an Anime Style Open World", given by Haoyu Cai](https://www.famitsu.com/news/202107/23228135.html). Covers the character pipeline, separate passes for characters and scenes, the face shadow mask, and real-time and ambient light on characters. This is a press report of the talk, not the talk itself. Silent on cel shading, outlines and hair.
- S2. [miHoYo, Unite Seoul 2020, "From Mobile to Console: Genshin Impact's rendering technology on Console", slides by Zhenzhong Yi](https://image.docswell.com/s/UnityJapan/KWRPQ5-210617-unity-dojo20211mihoyozhenzhongyi). Covers the two rendering pipelines (PC and console; mobile), "PBR based stylized rendering" (slide 9) and capsule ambient occlusion for characters (slides 32–34). Silent on toon shading, outlines, rim light, hair and faces.
- S3. [Adrian Mendez, "Genshin Impact Character Shader Breakdown (Unity URP)"](https://adrianmendez.artstation.com/projects/wJZ4Gg). A recreation in Unity. Covers the light and shadow split, face shadow texture, hair highlight, metal, outline and edge highlight. It does not claim the game uses the same methods.
- S4. [bjayers on ArtStation, "Blender NPR: Recreating the Genshin Impact Shader"](https://bjayers.artstation.com/blog/category/5). A recreation in Blender, mixed with statements about how the game behaves. Covers painted shadows in textures, shadow ramps, the face light map, hair shine masks, metal, inverted-hull outlines and rim light.
- S5. [Game8, "How to Get the 5-Star Outrider Outfit"](https://game8.co/games/Genshin-Impact/archives/355423). Names 5-Star Outrider as Amber's default outfit.
- S6. [Screen Rant, Rain Kengly, 28 January 2022, on the alternate outfits](https://screenrant.com/genshin-impact-alternate-outfits-jean-mona-rosaria-amber/). Lists what changed between Amber's original outfit and 100% Outrider.

Tool documentation is listed under each brief.

## Open questions

1. Where do the two in-game stills come from, and which game version, platform and graphics preset do they show? Until that is known they stay provisional. If either is a trailer frame, it is not evidence.
2. Which game version do the viewer models come from?
3. In-game shots that would lift this doc above Shape only. Record game version, platform and graphics preset with each, because PC and console use a different rendering pipeline from mobile. [official: S2]

   | Shot | Fills |
   |---|---|
   | Front, side and back, full body, idle, flat light | Axes 1, 5, 6 |
   | The same from farther away | Axes 6, 12 |
   | Face close-up, lit from the front and from the side | Axes 2, 3 |
   | Hair close-up from two camera heights, in daylight | Axis 4 |
   | Same pose in direct sun and in shade | Axes 5, 10 |
   | Goggles, gold trim, belt and gem in sun, from two angles | Axes 8, 9 |
   | Bow in hand, bow stowed, and the bow's name | Axis 11 |
   | Figure small in frame in Mondstadt, by day | Axes 12, 13 |
   | Three frames of a run cycle | Axis 12 |

4. Which outline method does the game use? S3 and S4 disagree. An official talk on character rendering, or close-ups of the outline at concave folds and at several distances, would settle it.
5. Are the darker fold shapes part of the base-colour texture, or does viewer B's shader add them? They also show under viewer A's lighting, which points to the texture. An in-game shot in flat light would confirm it.
6. Do brows and eyes show through the fringe in-game?
