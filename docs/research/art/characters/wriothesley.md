# Wriothesley (Genshin Impact)

Outfit: Night's Chilling Howl, his default and the only outfit listed for him. [community: S5] The sheets carry no outfit name. The listing describes the outfit by a rugged grey wolf chain, and the views show a silver wolf-head emblem on the chest with a heavy chain hanging from it. [community: S5] [viewer: A Face, B front] No fuller written description was opened.

Game version or shot date: Viewer captures provided on 13 November 2026. The game version the viewer models come from is unverified. The listing's banner history tags a version 4.1 banner as his debut. [community: S5]

Confidence: Shape only. Two viewer sheets cover the character and there is no in-game shot.

Shots used:
- Viewer sheet A: 16 labelled views (Front, 3/4 Front, 1/4 Front, Side, 3/4 Back, 1/4 Back, Back, Face, 1/4 Face, 3/4 Face, Footwear, Front Detail, 3/4 Front Detail, Back Detail, 3/4 Back Detail, Back of Head). Bind pose, black backdrop, viewer lighting. Tagged `[viewer: A <view>]`.
- Viewer captures B: three captures (front, side, back). Pale grey backdrop with a floor shadow, viewer lighting, bind pose. Tagged `[viewer: B <view>]`.

Links and capture details are in [references/shots.md](../references/shots.md). What each viewer gets right and wrong is in [references/viewers.md](../references/viewers.md).

## Production brief: Blender

Partial: shape only. These rules cover the model and its textures. There are no rules yet for outlines, shading bands, highlights, rim light or how materials respond to light.

1. Block out a tall adult build in an orthographic front view at about seven and three-quarter head-heights with thick soles included, with shoulders about 1.7 heads wide and a waist about one head wide. (Axis 1)
2. Hang a long outer garment from the shoulders like a cape, with its sleeves left empty, so that it stands about three heads wide behind a narrow body. (Axis 1)
3. Model the face as a smooth surface whose only clear relief is a small nose tip, and paint brows, lash bands, crease lines, a short mouth line and any marks on the skin in the face texture. (Axis 2)
4. Paint each eye in Texture Paint as a narrow opening under a thick lash band, with an iris that is dark at the top and has a pale crescent along its lower rim. (Axis 3)
5. Build hair from a smooth cap plus thick pointed locks swept up and back, and paint strand lines and any lighter streaks onto whole locks instead of modelling strands. (Axis 4)
6. Draw seams, dashed stitch lines, quilting lines and panel lines as strokes on the base-colour texture in Texture Paint, and keep them out of the mesh. (Axis 6)
7. End every piece with a contrasting edge: a line of piping in the accent colour, a row of metal studs, a spiked or pointed cuff, or a fur collar. (Axis 7)
8. Repeat three motifs at different sizes across the design, here chain links, small diamond studs and pointed spikes, and build them from simple faceted shapes. (Axis 8)
9. Model the body and its symmetric garments with a Mirror modifier, then add the one-sided items, such as a chest emblem with its chain, a single thigh strap and a hanging weight at one hip, as separate, unmirrored objects. (Axis 8)
10. Give each material region one flat base colour: near-black, dark grey and navy over most of the figure, mid and light greys for the inner garments, one dark red for lining, tie and trim, metal as neutral silver, and a pale blue kept to a few gems. (Axis 10)

Sources for this brief:
- Orthographic view: [Blender Manual, Perspective/Orthographic](https://docs.blender.org/manual/en/latest/editors/3dview/navigate/projections.html)
- Texture Paint: [Blender Manual, Texture Paint introduction](https://docs.blender.org/manual/en/latest/sculpt_paint/texture_paint/introduction.html)
- Mirror modifier: [Blender Manual, Mirror Modifier](https://docs.blender.org/manual/en/latest/modeling/modifiers/generate/mirror.html)

## Production brief: Three.js / WebGPU

Partial: shape only. The model and textures are authored elsewhere; these rules cover what the runtime must keep intact. There are no rules yet for shading, outlines or lighting.

1. Check proportions through an `OrthographicCamera`, because the two viewers' cameras gave 7.7 and 6.9 head-heights for the same model. (Axis 1)
2. Set `colorSpace = SRGBColorSpace` on every base-colour texture so the flat colours display as authored. (Axis 10)
3. Take seams, dashed stitch lines, quilting lines and panel lines from the base-colour map, and do not generate them with an edge-detection pass. (Axis 6)
4. Keep the iris painting in the eye's base-colour map, and do not add a specular or reflection highlight to the eye material. (Axis 3)
5. Render hair locks and fur points as opaque geometry with no alpha fade at the tips. (Axis 4)
6. Render both faces of a draped outer garment, with `side = DoubleSide` or with modelled inner faces, because its lining shows from the front and its outside from behind. (Axis 7)

Sources for this brief:
- Orthographic camera: [three.js docs, OrthographicCamera](https://threejs.org/docs/pages/OrthographicCamera.html)
- Texture colour space: [three.js manual, Color Management](https://threejs.org/manual/pages/color-management.html) and [three.js docs, Texture](https://threejs.org/docs/pages/Texture.html)
- Material sides: [three.js docs, Material](https://threejs.org/docs/pages/Material.html)

## Dissection

Left and right are the character's own. Measurements and colour values are approximate.

### 1. Silhouette and proportions

Observation:
- Height is about 7.7 head-heights from the top of the hair to the soles, thick soles included (head about 84 px, figure 652 px). The chin can be placed only to within 2 px, so the figure lies between 7.5 and 7.9. [viewer: A Front]
- The hair stands high above the skull, which makes the head measure taller and the count lower than on a character with flat hair. [viewer: A Front, A Side]
- The same measure gives 6.9 in B front (head 169 px, figure 1170 px). [viewer: B front] That viewer is not used for proportions, as recorded in [references/viewers.md](../references/viewers.md).
- The jacket's shoulders span about 1.7 heads (147 px). The waistcoat is about one head wide at the waist (83 px). [viewer: A Front]
- Where the legs part: Not observable. Loose trousers and large knee plates cover it. [viewer: A Front, B front] A view of the body without the outfit would resolve it; none is expected.
- The knee plates start about 56% of the way down the figure and the boots about 67%. [viewer: A Front]
- Head silhouette: hair swept up and back in thick pointed locks, with two upright pointed tufts at the back of the crown. [viewer: B back, B side]
- A long coat hangs from the shoulders like a cape. Its sleeves are empty and end in large turned-up cuffs that stand off the body at hip level. [viewer: B back, B side, A Front]
- In bind pose the coat spreads to about three heads wide (about 265 px) and ends at about knee level, about 62% of the way down. [viewer: A Front]
- A mass of spiky fur sits behind the neck and over the shoulders. [viewer: B back, A Back of Head]
- Upper body: short jacket sleeves end above the elbow in outward-pointing spikes. [viewer: B front]
- The legs end in tall boots with a thick sole and many strap ends sticking out behind. [viewer: B side, A Footwear]
- A chain with a pointed end hangs from the coat's back and stands out behind the figure in the Side view. [viewer: A Side, B side]
- Every view shows the bind pose. [viewer: A Front, B front]

Technique: Proportions belong to the mesh. [inferred] The developer describes character models as built from three-view drawings to shared standards for tessellation, topology and textures. [official: S1]

### 2. Head and face construction

Observation:
- The face is a smooth surface with little modelled relief. The nose is a small point with no bridge line or nostrils. [viewer: B side, A Face]
- The mouth is a short line with barely raised lips and no lip colour. [viewer: A Face, B front]
- The face is long, with a pointed chin and no visible jaw angle. [viewer: A Face, A 3/4 Face]
- The eye line sits about 63% of the way down from the top of the hair to the chin. [viewer: A Front]
- The gap between the eyes is about one eye-width. [viewer: A Face]
- Eyebrows are thick, dark, angled bars. [viewer: A Face, B front]
- A short red-brown curved mark sits under the right eye. [viewer: A Face]
- Thin vertical lines are drawn on the throat between the neck bands. [viewer: A Face]
- Human ears are visible. The right ear carries several small silver studs along its rim; each lobe carries a black stud. [viewer: A Face, B side]
- A long fringe lock falls over part of the left eye. [viewer: A Face, B front]
- Whether brows or eyes show through the hair in-game: Not observable. An in-game face close-up would resolve it.
- Face shading: Not observable. In-game face shots lit from the front and from the side would resolve it.

Technique:
- Brows, lash bands, crease lines, the mouth line, the mark under the eye and the throat lines are painted in the skin texture. [inferred]
- The developer says faces use a dedicated shadow mask that responds to light direction, because standard shading could not give the wanted face. [official: S1] Two recreations describe it as a face shadow texture [breakdown: S3] and a custom face light map. [breakdown: S4]

### 3. Eyes

Observation:
- The eye opening is narrow: its height under the lash is about a third of the eye's width. [viewer: A Face]
- Upper lash: a thick dark band with a short point at the outer corner. No upward spike rises from it. [viewer: A Face, B front]
- Two thin crease lines sit above the lash. [viewer: A Face]
- The white of the eye is greyer under the upper lash. [viewer: A Face]
- Iris: mid blue, darker at the top, with a pale blue crescent along its lower rim and a dark vertical pupil. [viewer: A Face, B front]
- No separate white highlight can be made out. The pale crescent sits in the same place in both eyes. [viewer: A Face, B front]
- The iris is about 13 px wide in the largest view, so finer detail is Not observable. An in-game face close-up would resolve it.

Technique: Iris and lashes are painted in a texture. [inferred] Whether the game shades the eyes or adds a moving highlight: Not observable. In-game face close-ups from two angles would resolve it.

### 4. Hair: shape language, clumps, highlight, shadow

Observation:
- A smooth cap covers the skull. [viewer: B back, A Back of Head]
- The hair is swept up and back from the forehead in thick pointed locks, short at the sides and the nape. [viewer: A Face, B side]
- One long fringe lock falls forward over the left eye. [viewer: A Face, B front]
- Two pointed tufts stand upright at the back of the crown. [viewer: B back, A Back of Head]
- Thin darker lines run along the locks. There are no individual strands. [viewer: B back, A Face]
- Clump edges are crisp, with no fade at the tips. [viewer: B front, B back]
- Base colour is near-black with a blue tint, about `#39393D`. Several whole locks are a lighter grey. There is no root-to-tip gradient. [viewer: B front, A Face]
- Viewer A draws one crisp white jagged mark on the fringe. Viewer B draws none. [viewer: A Face, B front] The difference is recorded in [references/viewers.md](../references/viewers.md); neither is evidence for the game's highlight.
- The fur collar follows the same shape language: a few large pointed tufts with darker lines, no fine fur. [viewer: B back, A Back of Head]
- Highlight shape, shadow tone and whether the highlight moves with the camera: Not observable. Two in-game hair close-ups from different camera heights, in daylight, would resolve it.

Technique:
- Hair and fur are built from solid pointed clumps, with strand lines and the grey streaks painted on. [inferred]
- One recreation reports that shine marks painted in the hair textures mask a real-time specular highlight. [breakdown: S4] The white mark in viewer A would fit such a mask shown as plain colour; this is unverified. See candidate C17 in [aesthetics/_candidates.md](../aesthetics/_candidates.md).

### 5. Skin: tone, shading bands, rim light

Observation:
- Base tone is pale and warm, about `#E2CABF` on the cheek. [viewer: B front] Viewer A agrees, at about `#EAD1C5`. [viewer: A Front]
- Skin shows on the face and ears, the throat between the neck bands, the fingers, and through gaps in the wraps on both forearms. [viewer: B front, B back]
- Skin takes about 3% of the figure's area from the front. [viewer: B front]
- Shading bands and rim light: Not observable. In-game shots in direct sun and in shade would resolve it.

Technique: Unverified. See candidates C9, C10 and C12 in [aesthetics/_candidates.md](../aesthetics/_candidates.md).

### 6. Outlines and inner lines

Observation:
- Outlines: Not observable. Neither viewer draws one. [viewer: A Front, B front] In-game front, side and back shots at two distances would resolve it.
- Lines drawn onto the surface:
  - Seams: on the waistcoat, down the trousers and along the coat's panels. [viewer: B front, B back]
  - Stitches: pale dashed lines beside the coat's back seams. [viewer: B back]
  - Quilting: a diamond lattice of darker lines over the whole coat lining. [viewer: B front, A Front]
  - Panel lines: long curved lines down the front of each boot. [viewer: B front, A Footwear]
  - Hair: darker strand lines along the locks. [viewer: B back]
  - Face and throat: brows, lashes, crease lines, mouth line, the mark under the eye and the throat lines, as covered in Axes 2 and 3. [viewer: A Face]
- Flat shapes drawn onto the surface:
  - A darker emblem pattern on the red centre panel of the coat's back and on the red panel down the side of the trousers. [viewer: B back, B side]
  - A swirl pattern on the knee plates. [viewer: B front]
  - A small emblem on the upper sleeve. [viewer: B side]
- Darker fold shapes: soft darker shapes sit under the chest on the waistcoat in both viewers. [viewer: A Face, B front]
- Knee creases: none visible; the knee plates cover the knees. [viewer: B front]

Technique: Surface lines, flat shapes and painted folds: see [Painted lines and fold shapes](../aesthetics/painted-lines-and-fold-shapes.md). The outline method is unverified; the two recreations opened for Amber use different methods. [breakdown: S3, S4]

### 7. Clothing: structure, layering, trim, how pieces end

Observation:
- Neck: two black bands wrap the throat, with skin showing between them. [viewer: A Face, B front]
- Shirt and tie: a navy collar, open at the throat, and a long dark red tie with a silver three-pointed piece at the knot. [viewer: A Face, B front]
- Waistcoat: grey, with wide pointed lapels and two columns of small silver diamond studs. [viewer: A Face, B front]
- Jacket: navy, with short sleeves that end above the elbow in a ring of outward-pointing spikes, edged with a dark red line and set with red square studs. [viewer: B front, A Front Detail]
- Forearms: black wraps from elbow to wrist, torn open in places. The right arm's wrap is nearly whole; the left arm's is crossed bands with wide gaps. [viewer: B front]
- Hands: black fingerless gloves with silver pieces at the knuckles. [viewer: B front, B side]
- Coat: dark grey outside, dark red inside, worn over the shoulders with empty sleeves. It has a tall dark red collar, a fur collar behind the neck, and large turned-up cuffs with strap tabs and silver diamond studs. [viewer: B front, B back, B side]
- Coat lining: dark red, quilted in a diamond lattice with a small silver diamond stud at each crossing. From the front the lining is what shows on both sides of the body. [viewer: B front, A Front]
- Coat back: two dark grey halves on either side of a dark red centre panel, with dark red piping along the seams and three silver diamond studs down each half. [viewer: B back]
- Belt: dark red with dark strap sections and a silver spiked buckle set with pale blue gems. Dark straps cross the hips below it. [viewer: B front, A Front Detail]
- Trousers: light grey and loose. A dark red patterned panel runs down the outside of the right leg; no view shows the outside of the left leg. [viewer: B front, B side]
- Knees: a large grey plate with a paler rim over each knee and lower thigh. [viewer: B front]
- Boots: navy, from the knee down, with a dark red V-shaped stripe at the top, rows of straps with silver buckles and pointed tabs down the sides and back, and a thick treaded sole with a silver plate at the toe. [viewer: B front, B side, A Footwear]
- How pieces end: every edge is marked by contrast. The jacket sleeves end in spikes with a red line, the coat in red piping and studded cuffs, the boots in a red stripe and a silver toe plate, the collar in fur. [viewer: B front, B back]

Technique: Large forms, spikes, studs, chains and straps are geometry. [inferred] Seams, stitches and quilting lines: see [Painted lines and fold shapes](../aesthetics/painted-lines-and-fold-shapes.md). Whether the tears in the arm wraps are cut-outs in the texture or modelled is unverified; a close-up of a forearm would resolve it.

### 8. Detail and ornament

Observation:
- Detail clusters: the ears and fringe; the neck and tie; the chest emblem and its chain; the sleeve ends; the belt; the hands and wrists; the coat's cuffs; the knee plates; the boots; and on the back the gem and chain at the shoulders and the clasp and chain at the waist. [viewer: B front, B back]
- Plain areas: the front of the waistcoat, the trousers, the outside of the coat between its studs, and the lining apart from its regular quilting. [viewer: B front, B back]
- Three motifs repeat at different sizes: [viewer: B front, B back, B side]
  - Chain links: from the chest emblem, across the upper back, down the centre of the coat's back, at the left hip and at the left wrist. [viewer: B front, B back]
  - Small diamond studs: on the waistcoat, the lining, the coat's back, the coat's cuffs and the trousers. [viewer: B front, B back]
  - Spikes and points: the sleeve ends, the belt buckle, the clasp on the coat's back, the fur, the boot tabs and the hair. [viewer: B front, B back, B side]
- Asymmetry: the body and most garments are mirror-symmetric; these items sit on one side only. [viewer: B front, B back]
  - Right: a large silver wolf-head emblem with a pale blue crescent on the chest, with a heavy chain hanging from it in two loops; a dark strap round the thigh; the studs along the ear's rim. [viewer: B front, A Face]
  - Left: a chain with a long silver weight and a dark red pointed tip at the hip; a chain at the wrist and a red gem on the back of the glove; the fringe lock over the eye; a round gem on the back of the shoulder. [viewer: B front, B back]
  - The two forearm wraps differ. [viewer: B front]
- Gems: a round pale cyan gem carrying a snowflake-like symbol in a pale gold scroll frame, on the back of the left shoulder; pale blue gems in the belt buckle; a cyan and a dark red pointed piece at the end of the back chain; a red gem on the left glove. [viewer: B back, B front]
- Back: a chain of large silver links runs across the shoulders from the round gem. At the waist a silver spiked ring with four strap tabs joins the coat's halves, and a spiked chain hangs from it down the centre to below the hem. [viewer: B back, A Back Detail]
- Metal is silver throughout; the only gold is the frame of the round gem. [viewer: B front, B back]
- Silver pieces carry three or four flat tones, one per facet. [viewer: A Face, B back]

Technique: Chains, studs, spikes and buckles are simple faceted geometry with one flat tone per facet. [inferred] Which emblems are raised and which are only painted is unverified; a close-up at a raking angle would resolve it.

### 9. Materials

Observation:
- How cloth, fur, silver, the wraps and the gems respond to light: Not observable. In-game close-ups of the chest emblem, a chain, the belt buckle, the fur collar and the round gem in direct sun, from two camera angles, would resolve it.
- The viewers show only the painting underneath. Silver is painted in three or four flat greys per piece, each gem in lighter and darker facets, and the fur in two or three flat greys with darker lines. [viewer: A Face, B back]

Technique: Unverified. One recreation describes metal as a matcap combined with a real-time specular term [breakdown: S4]; the other uses a matcap-style gradient lookup driven by the view and light directions. [breakdown: S3] Neither covers fur.

### 10. Colour

Observation: Base colours were sampled from B front and B back, the more evenly lit viewer. The viewer still lights the model, and neither viewer is a reference for brightness, so the values are viewer readings. [viewer: B front, B back]

| Role | Where | Approx. base colour | Saturation, value |
|---|---|---|---|
| Dark base: near-black | Neck bands, arm wraps | `#232323` | 0%, 14% |
| Dark base: hair | | `#39393D` | 7%, 24% |
| Dark base: dark grey | Coat outside, gloves | `#444347`, `#47454A`, `#413F42` | 5–7%, 26–29% |
| Dark base: fur | Collar, lit and shaded | `#616164`, `#454448` | 3–6%, 28–39% |
| Dark base: navy | Jacket, boots | `#464754`, `#383B45` | 17–19%, 27–33% |
| Grey | Waistcoat | `#67636E`, `#6B6672` | 10–11%, 43–45% |
| Grey | Knee plates | `#57535D`, `#625C68` | 11–12%, 36–41% |
| Light grey | Trousers | `#7F7F8A`, `#82828E` | 8%, 54–56% |
| Signature: dark red | Tie, boot stripe | `#6C3842`, `#723542` | 48–54%, 42–45% |
| Signature: dark red | Lining, belt | `#4D3037`, `#52313A`, `#4F2C30` | 38–44%, 30–32% |
| Dark red, brightest | Tip of the hip chain | `#903945` | 60%, 56% |
| Silver | Emblem, chains, hip weight | `#6F6D71`, `#6A666E`, `#8C8C8C`, `#838283` | 0–7%, 43–55% |
| Pale blue and cyan | Buckle gems, back gem, back pendant | `#92C1E2`, `#A6F1FC`, `#75CFD6` | 34–45%, 84–99% |
| Skin | Cheek | `#E2CABF` | 15%, 89% |

- Area in bind pose, front view, floor shadow excluded: near-black and dark grey 26%; dark red 24%; navy 20%; mid grey 17%; light grey and silver 9%; skin 3%. Back view: near-black and dark grey 66%; mid grey 11%; dark red 10%; navy 8%; light grey and silver 3%. [viewer: B front, B back]
- Structure: a dark, nearly neutral base; mid and light greys for waistcoat and trousers; one dark red for lining, tie and trim; silver metal; a pale blue kept to a few gems. [viewer: B front, B back]
- There is no white and almost no gold. Light grey takes the place of white, and silver the place of gold. [viewer: B front, B back]
- Hue: the darks and greys are neutral or lean blue to violet, about 225–270°. The red sits at about 345–350°. The gems sit at about 185–205°. [viewer: B front, B back]
- Saturation: only the red and the small gems are saturated. The red sits at 38–54% on cloth. [viewer: B front]
- The red shows mostly from the front, as lining. From behind the figure is two-thirds near-black and dark grey. [viewer: B front, B back]
- Black: no sample is pure black. The darkest areas, the neck bands and arm wraps, read 14% in viewer B, darker than on the four women. [viewer: B front]
- Viewer A, sampled as a check, agrees on hue and reads the red more saturated: tie `#712F3E`, lining `#5D2E3D`, waistcoat `#686672`, trousers `#878894`, jacket `#444654`, boots `#383D4C`, hair `#3F4148`. [viewer: A Front]
- The grey of the lighter hair locks and the gold of the gem frame were not sampled: Not observable at this size. A close-up would resolve it.
- Lit tone and shadow tone per colour: Not observable. In-game shots of the same pose in direct sun and in shade would resolve it.

Technique: Each material region holds one flat base colour in the texture, with a few painted darker shapes. [inferred] One recreation reports that the game sets shadow colours per character with shadow ramps. [breakdown: S4] Unverified on Wriothesley.

### 11. Weapon

Observation: Not observable. No view shows a weapon. His weapon type is listed as catalyst. [community: S5] An in-game shot with the weapon in hand, one with it stowed if it stays visible, and the weapon's name would resolve it.

Technique: Not observable, for the same reason.

### 12. Readability

Observation:
- From shape alone, five things identify him: hair swept up into points with two upright tufts; a coat hung from the shoulders with a fur collar and empty, cuffed sleeves; a dark red lining framing a grey body from the front; short spiked sleeves over wrapped forearms; and tall strapped boots with thick soles. [viewer: B front, B back, B side]
- Front and back read differently. The front is grey, navy and red in near-equal parts; the back is almost one dark shape, marked by the pale round gem, the chain across the shoulders and the chain down the centre. [viewer: B front, B back]
- Value steps: light grey trousers at about 55%, waistcoat at about 44%, red at 30–45%, navy and dark grey at 27–33%, wraps at 14%. The trousers are the lightest large shape. [viewer: B front]
- In motion: Not observable. Three frames of a run cycle would resolve it.
- At a distance: Not observable. An in-game shot with the figure small in frame would resolve it.

Technique: The body is separated from the coat by hue, grey against dark red, and the coat from the background by its dark outside. [inferred]

### 13. Fit with the world

Observation: Not observable. In-game shots in the Fortress of Meropide, the place his listing names [community: S5], with the figure small in frame, would resolve it.

Technique: The developer says characters and scenes are rendered in separate passes, and that characters receive real-time and ambient environment light through a 24-hour cycle. [official: S1]

## Comparison

### With other characters

Compared with [zhongli.md](zhongli.md), [clorinde.md](clorinde.md) and [amber.md](amber.md).

Shared:
- Face: smooth, with a small nose point and features painted on. [viewer: A Face]
- Eyes: a thick upper lash band, an iris darker at the top, and a greyer band on the white. [viewer: A Face]
- Hair: a cap plus solid pointed locks with painted strand lines and crisp tips. [viewer: B back]
- Painted lines on the surface, and darker painted shapes at folds. [viewer: B front, B back]
- Detail in clusters with plain areas between, and a symmetric body with one-sided accessories. [viewer: B front]
- Every garment edge marked by contrast. [viewer: B front, B back]
- With Zhongli: a long face, thick straight brows, no lip colour, no upward lash spike, a build well above seven head-heights, a long outer garment, and darkest areas below 20% value. [viewer: A Face, A Front]
- With Amber: one dark red as the only saturated cloth colour. [viewer: B front]

Where Wriothesley breaks the pattern:
- Metal: silver throughout, where the other characters use pale gold. [viewer: B front, B back]
- White: none. Light grey trousers are the lightest large area. [viewer: B front]
- Outer garment: worn off the arms, so its lining shows from the front and its outside from behind; the two views differ more than on any other character so far. [viewer: B front, B back]
- Hair: no gradient; whole locks in a second, lighter tone, as Clorinde has one. [viewer: A Face]
- Marks on the skin: a mark under one eye and lines on the throat. [viewer: A Face]
- Fur: a collar built like hair, from large pointed tufts. [viewer: B back]
- Cloth with torn openings on the forearms; Xilonen is the only other character with ripped edges. [viewer: B front]
- Build: about 7.7 head-heights, between the women and Zhongli's 8.4; his tall hair and thick soles both enter the count. [viewer: A Front]

### Game-wide candidates

Supports: C1, C2, C3, C7, C13, C14.

Supports in part: C5, C8, C15, C16.

Breaks: C18, on head-heights.

The candidates and their evidence are in [aesthetics/_candidates.md](../aesthetics/_candidates.md).

## Sources

- S1. [Famitsu report (in Japanese) of miHoYo's GDC 2021 talk "'Genshin Impact': Crafting an Anime Style Open World", given by Haoyu Cai](https://www.famitsu.com/news/202107/23228135.html). Covers the character pipeline, separate passes for characters and scenes, the face shadow mask, and real-time and ambient light on characters. A press report of the talk, not the talk itself.
- S2. [miHoYo, Unite Seoul 2020, "From Mobile to Console: Genshin Impact's rendering technology on Console", slides by Zhenzhong Yi](https://image.docswell.com/s/UnityJapan/KWRPQ5-210617-unity-dojo20211mihoyozhenzhongyi). Covers the two rendering pipelines, PC and console against mobile.
- S3. [Adrian Mendez, "Genshin Impact Character Shader Breakdown (Unity URP)"](https://adrianmendez.artstation.com/projects/wJZ4Gg). A recreation in Unity; it does not claim the game uses the same methods.
- S4. [bjayers on ArtStation, "Blender NPR: Recreating the Genshin Impact Shader"](https://bjayers.artstation.com/blog/category/5). A recreation in Blender, mixed with statements about how the game behaves.
- S5. [GenshinBuilds, Wriothesley](https://genshin-builds.com/en/character/wriothesley). Names Night's Chilling Howl as his default and only listed outfit, describes it by a grey wolf chain, lists his weapon type as catalyst, names the Fortress of Meropide, and tags a version 4.1 banner as his debut.

Tool documentation is listed under each brief.

## Open questions

1. Which game version do the viewer models come from?
2. Where do the legs part under the trousers? No view shows it.
3. In-game shots that would lift this doc above Shape only. Record game version, platform and graphics preset with each, because PC and console use a different rendering pipeline from mobile. [official: S2]

   | Shot | Fills |
   |---|---|
   | Front, side and back, full body, idle, flat light | Axes 1, 5, 6 |
   | The same from farther away | Axes 6, 12 |
   | Face close-up, lit from the front and from the side | Axes 2, 3 |
   | Hair close-up from two camera heights, in daylight | Axis 4 |
   | Same pose in direct sun and in shade | Axes 5, 10 |
   | Chest emblem, a chain, belt buckle, fur collar and round gem in sun, from two angles | Axes 8, 9 |
   | Weapon in hand, weapon stowed, and its name | Axis 11 |
   | Figure small in frame in the Fortress of Meropide | Axes 12, 13 |
   | Three frames of a run cycle | Axis 12 |

4. Is the white mark on his fringe in viewer A a painted highlight? Viewer B does not show it.
5. Are the tears in the arm wraps cut-outs in the texture, or modelled?
6. Does the coat stay on the shoulders in the idle pose in-game, as it does in both viewers' bind pose?
