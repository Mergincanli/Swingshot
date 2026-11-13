# Zhongli (Genshin Impact)

Outfit: Hermit of Mortal Life, his default and the only outfit listed for him. [community: S5] The sheets carry no outfit name, and the listing describes the outfit only as his everyday wear, so the pieces could not be matched against a written description. The default status rests on that listing alone.

Game version or shot date: Viewer captures provided on 13 November 2026. The game version the viewer models come from is unverified. The listing's banner history tags a version 1.1 banner as his debut. [community: S5]

Confidence: Shape only. Two viewer sheets cover the character and there is no in-game shot.

Shots used:
- Viewer sheet A: 16 labelled views (Front, 3/4 Front, 1/4 Front, Side, 3/4 Back, 1/4 Back, Back, Face, 1/4 Face, 3/4 Face, Footwear, Front Detail, 3/4 Front Detail, Back Detail, 3/4 Back Detail, Back of Head). Bind pose, black backdrop, viewer lighting. Tagged `[viewer: A <view>]`.
- Viewer captures B: three captures (front, side, back). Pale grey backdrop, viewer lighting, bind pose. Tagged `[viewer: B <view>]`.

Links and capture details are in [references/shots.md](../references/shots.md). What each viewer gets right and wrong is in [references/viewers.md](../references/viewers.md).

## Production brief: Blender

Partial: shape only. These rules cover the model and its textures. There are no rules yet for outlines, shading bands, highlights, rim light or how materials respond to light.

1. Block out a tall adult build in an orthographic front view at about eight and a half head-heights, with shoulder pieces about 1.8 heads wide, a waist about one head wide, and legs taking a little over half the height. (Axis 1)
2. Give the outer garment a fitted upper body and a long open skirt that flares to about 2.5 heads wide at mid-calf, so the outline is a narrow top over a wide base. (Axis 1)
3. Model the face as a smooth surface whose only clear relief is a small nose tip, and paint brows, lash bands, crease lines and a short mouth line in the face texture. (Axis 2)
4. Paint each eye in Texture Paint as a narrow opening under a thick lash band, with an iris that runs from dark at the top to its brightest tone at the bottom centre and a coloured mark along the outer half of the lower lid. (Axis 3)
5. Build hair from a smooth cap plus layered pointed locks and one long thin tail, and paint strand lines and a root-to-tip colour change onto them instead of modelling strands. (Axis 4)
6. Draw crease lines, seams, fret and scale patterns and cloth swirls as strokes and flat shapes on the base-colour texture in Texture Paint, and keep them out of the mesh. (Axis 6)
7. End every piece with a contrasting edge: pale scroll trim on dark lapels, light piping along seams, an ornament band on each cuff, and a tassel at each front point of the hem. (Axis 7)
8. Repeat one small motif, here a rhombus, at many sizes from collar to shoes, and add a second, square fret motif on two or three large surfaces. (Axis 8)
9. Model the body and its garments with a Mirror modifier, then add the few one-sided items, such as a single earring and a single chest pin, as separate, unmirrored objects. (Axis 8)
10. Give each material region one flat base colour: near-black and dark charcoal over the largest area, one brown family for the outer garment, pale desaturated gold for ornament, and one saturated warm accent kept to gems and the tip of the hair. (Axis 10)

Sources for this brief:
- Orthographic view: [Blender Manual, Perspective/Orthographic](https://docs.blender.org/manual/en/latest/editors/3dview/navigate/projections.html)
- Texture Paint: [Blender Manual, Texture Paint introduction](https://docs.blender.org/manual/en/latest/sculpt_paint/texture_paint/introduction.html)
- Mirror modifier: [Blender Manual, Mirror Modifier](https://docs.blender.org/manual/en/latest/modeling/modifiers/generate/mirror.html)

## Production brief: Three.js / WebGPU

Partial: shape only. The model and textures are authored elsewhere; these rules cover what the runtime must keep intact. There are no rules yet for shading, outlines or lighting.

1. Check proportions through an `OrthographicCamera`, because the two viewers' cameras gave 8.4 and 7.6 head-heights for the same model. (Axis 1)
2. Set `colorSpace = SRGBColorSpace` on every base-colour texture so the flat colours display as authored. (Axis 10)
3. Take crease lines, seams, fret and scale patterns and cloth swirls from the base-colour map, and do not generate them with an edge-detection pass. (Axis 6)
4. Keep the iris painting in the eye's base-colour map, and do not add a specular or reflection highlight to the eye material. (Axis 3)
5. Render hair locks and the hair tail as opaque geometry with no alpha fade at the tips. (Axis 4)

Sources for this brief:
- Orthographic camera: [three.js docs, OrthographicCamera](https://threejs.org/docs/pages/OrthographicCamera.html)
- Texture colour space: [three.js manual, Color Management](https://threejs.org/manual/pages/color-management.html) and [three.js docs, Texture](https://threejs.org/docs/pages/Texture.html)

## Dissection

Left and right are the character's own. Measurements and colour values are approximate.

### 1. Silhouette and proportions

Observation:
- Height is about 8.4 head-heights from the top of the hair mass to the soles, the crown tuft excluded (head about 76 px, figure 639 px). The chin can be placed only to within 2 px, so the figure lies between 8.2 and 8.6. [viewer: A Front]
- The crown tuft adds about 0.2 of a head on top. [viewer: A Front]
- The same measure gives 7.6 in B front (head 151 px, figure 1151 px). [viewer: B front] That viewer is not used for proportions, as recorded in [references/viewers.md](../references/viewers.md).
- The shoulder plates span about 1.8 heads (140 px). The coat is about one head wide at the waist (80 px). [viewer: A Front]
- The trouser legs part 53% of the height above the soles, so the legs take a little over half the figure. [viewer: A Front]
- The head is small against the body: with its hair it is about as wide as the coat's waist, about 82 px against 80 px. [viewer: A Front]
- Head silhouette: short layered hair with pointed locks, a forked tuft standing up at the crown, and side locks that reach the jaw. [viewer: A Face, B front]
- A long thin tail of hair hangs from the nape to about hip level. [viewer: B back, A Side]
- Upper body: angular plates widen both shoulders, and the sleeves end in pointed cuffs that stand out from the forearm. [viewer: B front]
- A long coat is fitted to the waist and opens below it. Its skirt flares to about 2.5 heads wide (190 px) and ends at mid-calf in pointed tails, about 78% of the way down the figure. [viewer: A Front]
- From the side the coat's back tail stands out behind the legs, and the front tails end in long tassels. [viewer: A Side, B side]
- The legs are straight and slim under the coat and end in low shoes with a low heel. [viewer: B front, B side]
- Every view shows the bind pose. [viewer: A Front, B front]

Technique: Proportions belong to the mesh. [inferred] The developer describes character models as built from three-view drawings to shared standards for tessellation, topology and textures. [official: S1]

### 2. Head and face construction

Observation:
- The face is a smooth surface with little modelled relief. The nose is a small point with no bridge line or nostrils. [viewer: B side, A Face]
- The mouth is a short line with barely raised lips and no lip colour. [viewer: A Face, B front]
- The face is longer and narrower than on the four women dissected so far, with a pointed chin and no visible jaw angle. [viewer: A Face, A 3/4 Face]
- The eye line sits about 62% of the way down from the top of the hair mass to the chin. [viewer: A Front]
- The eyes are narrow. The gap between them is about 1.2 eye-widths. [viewer: A Face]
- Eyebrows are thick, straight, dark bars that slope down toward the nose. [viewer: A Face, B front]
- A red-orange mark runs along the outer half of each lower lid and past the outer corner. [viewer: A Face, B front]
- Human ears are visible beside the side locks. The left ear carries one earring: a dark piece, an amber bead and a long pale tassel. The right ear carries none. [viewer: A Face, B front, B back]
- A long fringe lock crosses the bridge of the nose between the eyes. [viewer: A Face, B front]
- Whether brows or eyes show through the hair in-game: Not observable. An in-game face close-up would resolve it.
- Face shading: Not observable. In-game face shots lit from the front and from the side would resolve it.

Technique:
- Brows, lash bands, crease lines, the lower-lid mark and the mouth line are painted in the face texture. [inferred]
- The developer says faces use a dedicated shadow mask that responds to light direction, because standard shading could not give the wanted face. [official: S1] Two recreations describe it as a face shadow texture [breakdown: S3] and a custom face light map. [breakdown: S4]

### 3. Eyes

Observation:
- The eye opening is narrow: its height under the lash is about a third of the eye's width. [viewer: A Face]
- Upper lash: a thick dark band that tapers to a point at the outer corner. No upward spike rises from it. [viewer: A Face, A 3/4 Face, B front]
- Two thin crease lines sit above the lash. [viewer: A Face, B front]
- The white of the eye is greyer under the upper lash. [viewer: A Face]
- Iris: dark red-brown at the top, orange in the middle and bright yellow at the bottom centre, with a small pale mark at its centre. [viewer: A Face, B front]
- No separate white highlight can be made out. The brightest part of the iris, the yellow patch, sits in the same place in both eyes and across three camera angles and both viewers. [viewer: A Face, A 1/4 Face, A 3/4 Face, B front]
- The iris is about 14 px wide in the largest view, so pupil shape and finer detail are Not observable. An in-game face close-up would resolve it.

Technique: Iris, lashes and the lower-lid mark are painted in a texture, since they do not change with the viewer's camera. [inferred] Whether the game shades the eyes or adds a moving highlight: Not observable. In-game face close-ups from two angles would resolve it.

### 4. Hair: shape language, clumps, highlight, shadow

Observation:
- A smooth cap covers the skull, with a forked tuft standing up at the crown. [viewer: A Face, B back]
- The fringe is several long pointed locks swept across the forehead. The longest crosses the bridge of the nose. [viewer: A Face, B front]
- Side locks frame the face to jaw level and end in points that turn outward. [viewer: B front, A Face]
- The back is short and layered, ending in pointed locks at the nape. [viewer: B back, A Back of Head]
- One long thin tail leaves the nape through a gold-framed amber diamond clasp and hangs straight down the back to about hip level. [viewer: B back, A Back Detail]
- Thin darker lines run along the locks. There are no individual strands. [viewer: B back, A Back of Head]
- Clump edges are crisp, with no fade at the tips. [viewer: B front, B back]
- Colour changes from root to tip. The cap is a dark brown-grey, about `#4C4643`; the tips of the side locks turn orange-brown. [viewer: B front] The tail runs from dark, about `#534C4A`, through brown, about `#866044`, to bright orange at its tip, about `#E39847`. [viewer: B back]
- Viewer A draws crisp white jagged marks in a ring round the crown. Viewer B draws none. [viewer: A Face, A Back of Head, B front, B back] The difference is recorded in [references/viewers.md](../references/viewers.md); neither is evidence for the game's highlight.
- Highlight shape, shadow tone and whether the highlight moves with the camera: Not observable. Two in-game hair close-ups from different camera heights, in daylight, would resolve it.

Technique:
- Hair is built from solid clumps, with strand lines and the colour change painted on. [inferred]
- One recreation reports that shine marks painted in the hair textures mask a real-time specular highlight. [breakdown: S4] The white marks in viewer A would fit such a mask shown as plain colour; this is unverified. See candidate C17 in [aesthetics/_candidates.md](../aesthetics/_candidates.md).

### 5. Skin: tone, shading bands, rim light

Observation:
- Base tone is very pale and warm, about `#F3E3D0` on the cheek. [viewer: B front] Viewer A agrees, at about `#EADCCD`. [viewer: A Front]
- Skin shows only on the face, the ears and a short length of neck. Gloves cover the hands. [viewer: B front, B back]
- Skin takes about 2% of the figure's area from the front. [viewer: B front]
- Shading bands and rim light: Not observable. In-game shots in direct sun and in shade would resolve it.

Technique: Unverified. See candidates C9, C10 and C12 in [aesthetics/_candidates.md](../aesthetics/_candidates.md).

### 6. Outlines and inner lines

Observation:
- Outlines: Not observable. Neither viewer draws one. [viewer: A Front, B front] In-game front, side and back shots at two distances would resolve it.
- Lines drawn onto the surface:
  - Creases: one long line down the front of each trouser leg, and a centre seam between the legs. [viewer: B front, A Front]
  - Seams: lines along the coat's panels and along the sleeves. [viewer: B front, B back]
  - Hair: darker strand lines along the locks. [viewer: B back]
  - Face: brows, lashes, crease lines and mouth line, as covered in Axes 2 and 3. [viewer: A Face]
- Flat shapes drawn onto the surface:
  - Lighter brown swirls on both forearms, in the same places in both viewers. [viewer: A Front, B front]
  - A scale pattern on the lower part of each front panel of the coat. [viewer: B front, B side]
  - A square meander pattern in a lighter grey over the whole centre panel of the coat's back. [viewer: B back, A Back Detail]
  - Two black open rhombi on that panel, and stepped orange lines along its centre split. [viewer: B back]
  - Small square fret marks on the cuffs. [viewer: B front]
- Knee creases: none visible on the trousers. [viewer: B front, B back]
- Darker fold shapes: none can be made out at the size of the views. [viewer: B front]

Technique: Surface lines and flat shapes: see [Painted lines and fold shapes](../aesthetics/painted-lines-and-fold-shapes.md). The outline method is unverified; the two recreations opened for Amber use different methods. [breakdown: S3, S4]

### 7. Clothing: structure, layering, trim, how pieces end

Observation:
- Shirt: a tall slate collar with long points, closed at the throat. [viewer: A Face, B front]
- Throat: an amber diamond gem in a pale gold frame, above a white tie-shaped panel that carries a pale gold rhombus and thin gold chains. [viewer: A Face]
- Waistcoat: a beige upper layer, and under it a brown layer with orange-tan piping in V shapes and a row of small gold rhombi down the centre. [viewer: A Face, B front]
- Coat, upper part: dark brown and fitted, with wide black lapels edged in pale silver-white scroll shapes. A grey angular plate sits on each shoulder. [viewer: A Face, B front]
- Fastening: two pairs of pale open rhombi face each other across the chest, one pair above the other. [viewer: B front, A Front Detail]
- Sleeves: dark brown at the shoulder, warmer brown toward the wrist. A tan line runs down each sleeve from a rhombus knot at the upper arm. [viewer: B front, B back]
- Cuffs: large, pointed and turned back, black outside with an indigo face, carrying an ornament of two linked pale gold rhombi. [viewer: B front]
- Hands: near-black gloves. A pale band sits on one finger of the right hand. [viewer: B front] An amber rhombus in a grey frame sits on the back of the right hand, the one the side views show; the left hand's back is not shown. [viewer: B side, A Side]
- Coat, lower part: open at the front from the waist. Each front panel carries tan flame-shaped appliqué above the scale pattern and ends in a point. Each point carries a grey open rhombus, a black bead and a long cream tassel. [viewer: B front, A Front]
- Coat, back: a black yoke with a large cream square-knot emblem, framed by orange-tan bands in a V. Pale grey panels edged in tan lie over the shoulder blades. Below the yoke a slate centre panel runs to the hem between tan piping. [viewer: B back, A Back of Head]
- Lining: viewer A shows the inside of the coat's skirt as golden yellow, about `#C5A14F`. Viewer B shows no yellow in any capture. [viewer: A Front, A 3/4 Back, B front, B side] Which is right is unverified; the difference is recorded in [references/viewers.md](../references/viewers.md).
- Trousers: dark charcoal, straight and close-fitting. [viewer: B front]
- Lower legs: a dark brown section from mid-shin to ankle. [viewer: B front, A Footwear]
- Shoes: low, dark brown, with a strap across the instep and a red-brown sole and low heel. [viewer: A Footwear, B side]
- How pieces end: every edge is marked by contrast. The lapels end in pale scroll trim, the panels in tan piping, the cuffs in a gold ornament, the front points in tassels. No edge is frayed or faded. [viewer: B front, B back]

Technique: Large forms, plates, tassels and gems are geometry. [inferred] Seams and patterns: see [Painted lines and fold shapes](../aesthetics/painted-lines-and-fold-shapes.md). Whether the scroll trim on the lapels is raised or painted is unverified; a close-up at a raking angle would resolve it.

### 8. Detail and ornament

Observation:
- Detail clusters: the throat and collar; the lapels and shoulder plates; the chest fastening; the cuffs; the lower front panels of the coat with their tassels; the shins and shoes; and on the back the yoke emblem and the gems and chain at the waist. [viewer: B front, B back]
- Plain areas: the upper sleeves, the body of the coat between chest and hip, the trousers, and the hair. [viewer: B front, B back]
- One motif repeats at many sizes, the rhombus: the throat gem, the tie ornament, the waistcoat studs, the chest fastening, the sleeve knots, the cuff ornaments, two stacked open rhombi on each thigh, one in the line ornament on each shin, the tassel rings, the hair clasp and the gems on the back. [viewer: B front, B back, A Face]
- A second motif, a square fret, appears on the yoke emblem, in the meander pattern of the back panel, on the cuffs and as the buckle on each shoe. [viewer: B back, B front, A Footwear]
- Asymmetry: the body and almost the whole outfit are mirror-symmetric. Three things sit on one side only. [viewer: B front, B back]
  - A pale gold four-point pin on the right side of the chest. [viewer: B front, A 3/4 Front Detail]
  - The single earring on the left ear. [viewer: B front, B back]
  - The fringe lock that crosses the face. [viewer: A Face]
- Gems: all amber. One at the throat, one in the hair clasp, one on the back of the right hand, one on each side of the back at waist level, one in a round gold ornament at the centre of the lower back, and one at each lower corner of the back panel. [viewer: A Face, B back, B side]
- A chain of pale beads hangs in a swag between the two waist gems on the back. [viewer: B back, A Back Detail]
- Gold pieces carry two or three flat tones, one per facet. [viewer: A Face, B front]

Technique: Plates, studs, rings and tassels are simple faceted geometry with one flat tone per facet. [inferred] Which emblems are raised and which are only painted is unverified; a close-up at a raking angle would resolve it.

### 9. Materials

Observation:
- How cloth, metal, the shoulder plates and the gems respond to light: Not observable. In-game close-ups of a shoulder plate, the throat gem, the chest fastening and a cuff in direct sun, from two camera angles, would resolve it.
- The viewers show only the painting underneath. Gold is painted in two or three flat tones per piece, each gem in lighter and darker amber facets, and each shoulder plate in a few flat greys. [viewer: A Face, B front, B back]
- The forearm swirls are lighter than the cloth round them and sit in the same place in both viewers, so they are painted pattern, not a lighting effect of one viewer. [viewer: A Front, B front]

Technique: Unverified. One recreation describes metal as a matcap combined with a real-time specular term [breakdown: S4]; the other uses a matcap-style gradient lookup driven by the view and light directions. [breakdown: S3]

### 10. Colour

Observation: Base colours were sampled from B front and B back, the more evenly lit viewer. The viewer still lights the model, and neither viewer is a reference for brightness, so the values are viewer readings. [viewer: B front, B back]

| Role | Where | Approx. base colour | Saturation, value |
|---|---|---|---|
| Dark base: near-black | Lapels, gloves, shoes | `#282727`, `#282828`, `#2E2C2B` | 0–7%, 16–18% |
| Dark base: charcoal | Trousers | `#3B363B` | 8%, 23% |
| Dark base: hair | Cap | `#4C4643` | 12%, 30% |
| Brown family, darkest | Coat at shoulder and chest | `#3A2D29`, `#493833` | 29–30%, 23–29% |
| Brown family | Lower coat, waistcoat layer, scales | `#4E3D38`, `#6B5048`, `#66503F` | 28–38%, 31–42% |
| Brown family, warmest | Forearm | `#6F4A34` | 53%, 44% |
| Piping | Waistcoat | `#B08161` | 45%, 69% |
| Beige | Upper waistcoat layer | `#9D8A80` | 18%, 62% |
| Pale gold | Cuff ornament, chest fastening, shin line | `#DBCBA1`, `#CDBD9A`, `#A09679` | 24–26%, 63–86% |
| Tan | Appliqué, coat piping | `#7E6952`, `#76634D` | 35%, 46–49% |
| Slate | Collar, cuff face, back panel | `#6A6774`, `#4C495D`, `#48454D` | 10–22%, 30–45% |
| Grey | Shoulder plates | `#958F92`, `#868184` | 4%, 53–58% |
| White and cream | Tie panel, back panels, tassel | `#EDE9E7`, `#D4D4D4`, `#DECCB4` | 0–19%, 83–93% |
| Skin | Cheek | `#F3E3D0` | 14%, 95% |
| Amber accent | Throat gem, back gem, tip of the hair tail | `#B07F2D`, `#FFC041`, `#E39847` | 69–75%, 69–100% |

- Area in bind pose, front view: near-black, charcoal and the darkest browns 42%; mid browns 33%; pale gold, tan and beige 10%; white and pale grey 8%; grey and slate 4%; skin 2%; amber under 1%. Back view: dark tones 53%; mid browns 30%; gold and tan 8%; grey and slate 3%; amber and orange 2%; white 1%. [viewer: B front, B back]
- Structure: a dark base, one brown family over a third of the figure, pale gold ornament, a little white, and a saturated amber kept to gems and the tip of the hair. [viewer: B front, B back]
- Hue: the browns, golds, skin and amber all sit between about 10° and 45°. Slate, at about 250°, is the only clearly cool colour. [viewer: B front, B back]
- Saturation: only the amber is strongly saturated. The browns sit at 28–53%, the golds at 24–35%. [viewer: B front]
- Gold metal is a pale, desaturated khaki, the same family as on the four women. [viewer: B front]
- Black: no sample is pure black. The darkest areas read 16–18% in viewer B, darker than on the four women; viewer A reads the lapels darker still, about `#151314`. [viewer: B front, A Front]
- White: small and neutral, at the throat, over the shoulder blades and in the tassels. [viewer: B front, B back]
- Viewer A, sampled as a check, agrees on hue: hair `#544B48`, skin `#EADCCD`, trousers `#423A41`, forearm `#784C2F`, collar `#6F6C7D`, tassel `#E5D1B8`. [viewer: A Front]
- Iris values were not sampled: Not observable at this size. A close-up would resolve it.
- Lit tone and shadow tone per colour: Not observable. In-game shots of the same pose in direct sun and in shade would resolve it.

Technique: Each material region holds one flat base colour in the texture; the hair's colour change and the sleeve's shift from dark to warm brown are painted. [inferred] One recreation reports that the game sets shadow colours per character with shadow ramps. [breakdown: S4] Unverified on Zhongli.

### 11. Weapon

Observation: Not observable. No view shows a weapon. His weapon type is listed as polearm. [community: S5] An in-game shot with the weapon in hand, one with it stowed if it stays visible, and the weapon's name would resolve it.

Technique: Not observable, for the same reason.

### 12. Readability

Observation:
- From shape alone, five things identify him: a small head with a crown tuft; widened, plated shoulders; a long coat that is narrow at the waist and wide at mid-calf; a thin tail of hair with a bright orange tip; and a pale tassel at each front point of the coat. [viewer: B front, B back]
- From behind, the pale square-knot emblem on the black yoke and the patterned slate panel carry the identity, with the hair tail as a bright line down the centre. [viewer: B back]
- The figure is dark overall. The lightest shapes are the face, the white at the throat, the lapel trim and the tassels. [viewer: B front]
- Neighbouring blocks differ little in value, about 16–44%, and are separated by pale edging instead. [viewer: B front]
- In motion: Not observable. Three frames of a run cycle would resolve it.
- At a distance: Not observable. An in-game shot with the figure small in frame would resolve it.

Technique: The dark blocks are separated by light trim lines, and the warm accent marks the centre line and the gems. [inferred]

### 13. Fit with the world

Observation: Not observable. In-game shots in Liyue Harbor, where his listing places him [community: S5], by day and with the figure small in frame, would resolve it.

Technique: The developer says characters and scenes are rendered in separate passes, and that characters receive real-time and ambient environment light through a 24-hour cycle. [official: S1]

## Comparison

### With other characters

Compared with [amber.md](amber.md), [clorinde.md](clorinde.md) and [navia.md](navia.md). He is the first man dissected.

Shared:
- Face: smooth, with a small nose point and features painted on. [viewer: A Face]
- Eyes: a thick upper lash band, an iris darker at the top, and a greyer band on the white. [viewer: A Face]
- Hair: a cap plus solid pointed locks with painted strand lines and crisp tips; a painted root-to-tip colour change, as on Amber. [viewer: B back]
- Painted lines and patterns on the surface. [viewer: B front, B back]
- Gold as a pale, desaturated khaki with flat facets. [viewer: B front]
- Detail in clusters with plain areas between, and a symmetric body with a few one-sided accessories. [viewer: B front]
- Every garment edge marked by contrast. [viewer: B front, B back]
- One small motif repeated at many sizes, as the diamond on Clorinde. [viewer: B front]
- Legs at a little over half the height. [viewer: A Front]

Where Zhongli breaks the pattern:
- Build: about 8.4 head-heights against 6.9 to 7.4 on the women dissected so far, with a smaller head, shoulders about 1.8 heads wide and a waist about one head wide. [viewer: A Front]
- Face: longer and narrower; thick straight brows where the women have thin lines; no lip colour. [viewer: A Face]
- Eyes: no upward lash spike, as on Clorinde; no separate white highlight; a coloured mark under the outer half of the eye. [viewer: A Face]
- Skin: about 2% of the area, as on Clorinde; hands and neck are covered. [viewer: B front]
- Palette: no large saturated colour. The colour family is brown at low to medium saturation, and the saturated accent is under 2% of the area. [viewer: B front, B back]
- Value: darker overall, with the darkest areas at 16–18% and little white. [viewer: B front]
- Asymmetry: three one-sided items against seven on Clorinde and more on Navia. [viewer: B front]

### Game-wide candidates

Supports: C1, C3, C5, C6, C7, C13, C14.

Supports in part: C8, C15, C16, C18.

Breaks: none in full. C18 breaks on head-heights and holds on leg length.

The candidates and their evidence are in [aesthetics/_candidates.md](../aesthetics/_candidates.md).

## Sources

- S1. [Famitsu report (in Japanese) of miHoYo's GDC 2021 talk "'Genshin Impact': Crafting an Anime Style Open World", given by Haoyu Cai](https://www.famitsu.com/news/202107/23228135.html). Covers the character pipeline, separate passes for characters and scenes, the face shadow mask, and real-time and ambient light on characters. A press report of the talk, not the talk itself.
- S2. [miHoYo, Unite Seoul 2020, "From Mobile to Console: Genshin Impact's rendering technology on Console", slides by Zhenzhong Yi](https://image.docswell.com/s/UnityJapan/KWRPQ5-210617-unity-dojo20211mihoyozhenzhongyi). Covers the two rendering pipelines, PC and console against mobile.
- S3. [Adrian Mendez, "Genshin Impact Character Shader Breakdown (Unity URP)"](https://adrianmendez.artstation.com/projects/wJZ4Gg). A recreation in Unity; it does not claim the game uses the same methods.
- S4. [bjayers on ArtStation, "Blender NPR: Recreating the Genshin Impact Shader"](https://bjayers.artstation.com/blog/category/5). A recreation in Blender, mixed with statements about how the game behaves.
- S5. [GenshinBuilds, Zhongli](https://genshin-builds.com/en/character/zhongli). Names Hermit of Mortal Life as his default and only listed outfit, lists his weapon type as polearm, shows Liyue Harbor in its header, and tags a version 1.1 banner as his debut.

Tool documentation is listed under each brief.

## Open questions

1. Which game version do the viewer models come from?
2. Is the inside of the coat golden yellow, as in viewer A, or does it show no yellow, as in viewer B? An in-game shot from behind at three-quarter angle would settle it.
3. In-game shots that would lift this doc above Shape only. Record game version, platform and graphics preset with each, because PC and console use a different rendering pipeline from mobile. [official: S2]

   | Shot | Fills |
   |---|---|
   | Front, side and back, full body, idle, flat light | Axes 1, 5, 6 |
   | The same from farther away | Axes 6, 12 |
   | Face close-up, lit from the front and from the side | Axes 2, 3 |
   | Hair close-up from two camera heights, in daylight | Axis 4 |
   | Same pose in direct sun and in shade | Axes 5, 10 |
   | Shoulder plate, throat gem, chest fastening and cuff in sun, from two angles | Axes 8, 9 |
   | Weapon in hand, weapon stowed, and its name | Axis 11 |
   | Figure small in frame in Liyue Harbor, by day | Axes 12, 13 |
   | Three frames of a run cycle | Axis 12 |

4. Are the white marks on his hair in viewer A painted highlights? Viewer B does not show them. An in-game hair close-up from two angles would show whether they exist and whether they move.
5. Is the scroll trim on the lapels raised or painted?
6. Does a written description of this outfit exist that the pieces can be matched against? The listing opened gives none.
