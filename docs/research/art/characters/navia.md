# Navia (Genshin Impact)

Outfit: Yellow Velvet Salon, her default and the only outfit listed for her. [community: S5] The sheets carry no outfit name. The match rests on a community description of her look that lists the same pieces the views show: a large decorated hat with a white feather, a sleeveless navy, white and black bodice with an open back, a layered black-and-yellow skirt that opens at the front over a white miniskirt, a ship's-wheel motif on both hips, black thigh-high boots with blue gems, and a glove on the right arm only. [community: S6] [viewer: A Front, B front, B back]

Game version or shot date: Viewer captures provided on 13 November 2026. The game version the viewer models come from is unverified. Her debut banner ran in version 4.3. [community: S5]

Confidence: Shape only. Two viewer sheets cover the character and there is no in-game shot.

Shots used:
- Viewer sheet A: 16 labelled views (Front, 3/4 Front, 1/4 Front, Side, 3/4 Back, 1/4 Back, Back, Face, 1/4 Face, 3/4 Face, Footwear, Front Detail, 3/4 Front Detail, Back Detail, 3/4 Back Detail, Back of Head). Bind pose, amber backdrop, viewer lighting. Tagged `[viewer: A <view>]`.
- Viewer captures B: three captures (front, side, back). White backdrop, viewer lighting, bind pose. Tagged `[viewer: B <view>]`.

Links and capture details are in [references/shots.md](../references/shots.md). What each viewer gets right and wrong is in [references/viewers.md](../references/viewers.md).

## Production brief: Blender

Partial: shape only. These rules cover the model and its textures. There are no rules yet for outlines, shading bands, highlights, rim light or how materials respond to light.

1. Block out a tall build in an orthographic front view at an estimated seven to seven and a half head-heights with heels, with shoulders about 1.1 heads wide, a waist about 0.65, and legs below a short front skirt taking a little over half the height. (Axis 1)
2. Make three shapes wider than the shoulders: a tilted hat brim about 1.8 heads wide, a hair mass about 2.5 heads wide at hip level, and layered skirt tails about 3 heads wide that hang behind the legs to mid-calf. (Axis 1)
3. Model the face as a smooth surface whose only clear relief is a small nose tip, and paint brows, lash bands, crease lines and lip colour in the face texture. (Axis 2)
4. Paint each eye in Texture Paint with a thick lash band that ends in a wing and carries one upward spike, an iris that is dark at the top and pale at the bottom, and two highlights placed on the same sides in both eyes, not mirrored. (Axis 3)
5. Build hair from a smooth cap, a fringe of a few large flat pointed locks, and long ringlets modelled as thick spiral ribbons with pointed ends, and paint strand lines instead of modelling strands. (Axis 4)
6. Draw lacing, lace patterns, embroidery scrolls, pleat lines and ruffle shapes as strokes and flat shapes on the base-colour texture in Texture Paint, and keep them out of the mesh. (Axis 6)
7. Build the back of the skirt in tiers that alternate a saturated colour with dark patterned panels, and end every tier and every other garment edge with contrast: metal piping, a pale band, a lace hem or a painted ruffle. (Axis 7)
8. Repeat three motifs at different sizes across the whole design, here bows, faceted blue gems in gold frames and gold lattice work, and build the gems from simple faceted shapes. (Axis 8)
9. Model the body and its symmetric garments with a Mirror modifier, then add one-sided items, such as hat trim, a single glove and a single shoulder ornament, as separate, unmirrored objects. (Axis 8)
10. Give each material region one flat base colour: near-black, brown-black and navy for hat, bodice, sleeves and boots, one yellow at about 55–60% saturation for the skirt tails and bows, white for the chest panel and front skirt, and metal as a khaki-gold at about 30–40% saturation. (Axis 10)

Sources for this brief:
- Orthographic view: [Blender Manual, Perspective/Orthographic](https://docs.blender.org/manual/en/latest/editors/3dview/navigate/projections.html)
- Texture Paint: [Blender Manual, Texture Paint introduction](https://docs.blender.org/manual/en/latest/sculpt_paint/texture_paint/introduction.html)
- Mirror modifier: [Blender Manual, Mirror Modifier](https://docs.blender.org/manual/en/latest/modeling/modifiers/generate/mirror.html)

## Production brief: Three.js / WebGPU

Partial: shape only. The model and textures are authored elsewhere; these rules cover what the runtime must keep intact. There are no rules yet for shading, outlines or lighting.

1. Check proportions through an `OrthographicCamera` and measure from chin to sole, because headwear hides the top of the head and the two viewers' cameras put the skirt hem at 37% and 38% of that length. (Axis 1)
2. Set `colorSpace = SRGBColorSpace` on every base-colour texture so the flat colours display as authored. (Axis 10)
3. Take lacing, lace patterns, embroidery scrolls, pleat lines and ruffle shapes from the base-colour map, and do not generate them with an edge-detection pass. (Axis 6)
4. Keep both eye highlights in the eye's base-colour map, and do not add a specular or reflection highlight to the eye material. (Axis 3)
5. Render hair locks and ringlets as opaque geometry with no alpha fade at the tips. (Axis 4)
6. Cut the holes and jagged edges of lace with the base-colour map's alpha channel and an `alphaTest` threshold, so that whatever lies behind the lace shows through. (Axis 7)

Sources for this brief:
- Orthographic camera: [three.js docs, OrthographicCamera](https://threejs.org/docs/pages/OrthographicCamera.html)
- Texture colour space: [three.js manual, Color Management](https://threejs.org/manual/pages/color-management.html) and [three.js docs, Texture](https://threejs.org/docs/pages/Texture.html)
- Alpha test: [three.js docs, Material](https://threejs.org/docs/pages/Material.html)

## Dissection

Left and right are the character's own. Measurements and colour values are approximate.

### 1. Silhouette and proportions

Observation:
- The hat hides the top of the head in every view, so head-heights cannot be measured. [viewer: A Front, A Side, B back]
- Measured lengths, hat included: the figure is 710 px from the top of the hat to the soles, heels included. The chin sits 17% of the way down, the hem of the front skirt 48%, the boot tops 52% and the ankle gems 94%. [viewer: A Front]
- From chin to sole is 589 px; the legs below the skirt hem take 369 px of it. [viewer: A Front]
- Estimate: if the eye line sits 60–67% of the way down the head, as it does on Amber and Xilonen, the head is 83 to 100 px tall and the figure 6.9 to 8.1 head-heights without the hat, with about 7.3 in the middle. [inferred] On that estimate the legs below the hem take about 54% of the height. [inferred]
- Widths, in heads of about 94 px from the same estimate: bare shoulders about 1.1 (106 px), waist about 0.65 (60 px), front skirt at the hips about 1.2 (114 px). [viewer: A Front]
- Three shapes are wider than the shoulders: the hat brim at about 1.8 heads (170 px); the hair at hip level, 2.4 heads in the Front view and 2.7 in the Back view; and the skirt tails, 2.7 heads in the Front view and 3.3 in the Back view. [viewer: A Front, A Back]
- Hair and tails stand behind the body, and the viewer's camera has perspective, so their true widths lie between the two readings: about 2.5 and 3 heads. [inferred] The evidence for the perspective is in [references/viewers.md](../references/viewers.md).
- Head silhouette: a low, flat-topped hat with a wide flat brim, worn tilted so the brim is lower on the right, with a feather and flowers standing above it on the right. [viewer: B front, B side]
- Hair falls in one long mass to the waist and ends in large ringlets at about the level of the boot tops. [viewer: A Side, B side]
- Upper body: bare shoulders between a close-fitting bodice and puffed sleeve tops with bows. [viewer: B front]
- Lower body from the front: a short flared skirt, a band of bare thigh, and long dark boots, with the yellow skirt tails as a wide shape behind the legs. [viewer: A Front, B front]
- Lower body from behind: layered tiers that end in two long pointed tails. [viewer: B back, A Back]
- The tails end at mid-calf: their tips sit 82% of the way down the figure, hat included, in the Side view, where they are as far from the camera as the body. [viewer: A Side] The Front view shows them ending at 76% and the Back view at 91%. [viewer: A Front, A Back]
- From the side, the ringlets and the skirt tails stand out behind the torso by about a quarter of the figure's height. [viewer: A Side]
- Every view shows the bind pose. [viewer: A Front, B front]

Technique: Proportions belong to the mesh. [inferred] The developer describes character models as built from three-view drawings to shared standards for tessellation, topology and textures. [official: S1]

### 2. Head and face construction

Observation:
- The face is a smooth surface with little modelled relief. The nose is a small point with no bridge line or nostrils. [viewer: B side, A Face]
- The lips are small and pink, about `#CEB0AD`, with barely raised volume. [viewer: A Face, B front]
- The chin is small and pointed, the cheeks full, and the jaw has no visible angle. [viewer: A Face, A 3/4 Face]
- Each eye, lash wings included, is about a third of the visible face width. The gap between the eyes is about 0.9 of an eye-width. [viewer: A Face]
- Eyebrows are short, thin strokes in a khaki darker than the hair. [viewer: B front, A Face]
- In both viewers, brow strokes are drawn on top of the fringe locks that cross them. [viewer: A 1/4 Face, A 3/4 Face, B front] Whether the game draws brows over hair is unverified; an in-game face close-up would resolve it.
- A soft pink tint sits round the outer corner of each eye. [viewer: A Face, B front]
- A small pale dot sits on the tip of the nose in viewer B. [viewer: B front] It does not show at the size of viewer A's Face view.
- Human ears are visible behind the side locks. Each carries a small dark-blue stud with a faceted blue drop. [viewer: B side, A Front Detail]
- How far down the head the eyes sit: Not observable. The hat hides the top of the head. A viewer capture with the hat hidden would resolve it.
- Face shading: Not observable. In-game face shots lit from the front and from the side would resolve it.

Technique:
- Brows, lash bands, lip colour, the eye tint and the nose dot are painted in the face texture. [inferred]
- The developer says faces use a dedicated shadow mask that responds to light direction, because standard shading could not give the wanted face. [official: S1] Two recreations describe it as a face shadow texture [breakdown: S3] and a custom face light map. [breakdown: S4]

### 3. Eyes

Observation:
- Upper lash: a thick, near-black band, about `#23252E`, that ends in a pointed wing at the outer corner and carries one upward spike about a third of the way in from that corner. [viewer: A Face, B front]
- The inner half of the band is overlaid with red-brown strokes, about `#624340`, and two or three thin lashes point down and inward at the inner corner. [viewer: A Face, B front]
- A thin crease line sits above the lash, and a short dark line marks the outer end of the lower lid. [viewer: A Face, B front]
- The white of the eye has a grey band under the upper lash. [viewer: A Face, B front]
- Iris: a dark blue ring at the edge, dark blue at the top, about `#2E5C87`, and pale cyan at the bottom, about `#ADDAE3`. A pale oval with a dark U-shaped line under it stands for the pupil. [viewer: A Face, B front]
- Each iris has two highlights: a white four-point star at image-left and a small bright cyan oval, about `#3CDAF1`, at upper image-right. [viewer: A Face, B front]
- The highlights sit on the same sides in both eyes, not mirrored, and stay in place across three camera angles and both viewers. [viewer: A Face, A 1/4 Face, A 3/4 Face, B front]
- The eye opening is rounder than on Xilonen and Clorinde: its height under the lash is about 0.45 of the eye's width. [viewer: A Face]
- The iris is about 20 px wide in the largest view, so finer detail is Not observable. An in-game face close-up would resolve it.

Technique: Iris, lashes and highlights are painted in a texture, since the highlights do not move with the viewer's camera. [inferred] Whether the game shades the eyes or adds a moving highlight: Not observable. In-game face close-ups from two angles would resolve it.

### 4. Hair: shape language, clumps, highlight, shadow

Observation:
- A smooth cap covers the skull; the hat hides its top. [viewer: B back, A Back of Head]
- The fringe is five or six large, flat, pointed locks. One falls between the eyes to the bridge of the nose. [viewer: B front, A Face]
- Long side locks frame the face, and one curled strand hangs in front of each shoulder to the chest. [viewer: B front, A Face]
- At the back a black ribbon bow with two long tails gathers the upper hair. Two thin looped strands hang from the level of the bow to the shoulders. [viewer: B back, A Back of Head]
- The lengths fall as one mass to the waist and end in four large ringlets at about the level of the boot tops. [viewer: B back, A Side] A community description counts four curls at the back and two in front. [community: S6]
- The ringlets are thick spiral ribbons with a hollow centre and pointed ends. [viewer: B back, B side]
- Thin darker lines run along the locks and ringlets. There are no individual strands. [viewer: B back, A Back of Head]
- Clump edges are crisp, with no fade at the tips. [viewer: B front, B back]
- Base colour is a pale blonde, about `#D9C196`, up to about `#E9D2A5` on the lit side of a ringlet. There is no root-to-tip gradient. [viewer: B front, B back] Viewer A agrees, at about `#E8CC9E`. [viewer: A Front]
- Both viewers show lighter marks on the fringe and on the ringlets, in the same places: white with jagged ends in viewer A, a paler blonde with softer edges in viewer B. [viewer: A Face, A Back Detail, B front, B back] The difference is recorded in [references/viewers.md](../references/viewers.md); neither is evidence for the game's highlight.
- Highlight shape, shadow tone and whether the highlight moves with the camera: Not observable. Two in-game hair close-ups from different camera heights, in daylight, would resolve it.

Technique:
- Hair is built from solid locks and spiral ribbons, with strand lines painted on. [inferred]
- One recreation reports that shine marks painted in the hair textures mask a real-time specular highlight. [breakdown: S4] The marks both viewers show would fit such a mask; this is unverified. See candidate C17 in [aesthetics/_candidates.md](../aesthetics/_candidates.md).

### 5. Skin: tone, shading bands, rim light

Observation:
- Base tone is very pale and warm, about `#E7DBD0` on the face and `#E7D9CC` on the shoulder. [viewer: B front] Viewer A agrees, at about `#E8DDD3`. [viewer: A Front]
- Skin shows on the face and ears, the shoulders and upper chest, the upper back between the hair, a band of thigh between skirt and boots, the left hand, and through the openings of the boot tops. [viewer: B front, B back]
- Skin takes about 5% of the figure's area from the front. [viewer: B front]
- A nail on the left hand is painted pale blue. [viewer: B front]
- Shading bands and rim light: Not observable. In-game shots in direct sun and in shade would resolve it.

Technique: Unverified. See candidates C9, C10 and C12 in [aesthetics/_candidates.md](../aesthetics/_candidates.md).

### 6. Outlines and inner lines

Observation:
- Outlines: Not observable. Neither viewer draws one. [viewer: A Front, B front] In-game front, side and back shots at two distances would resolve it.
- Lines drawn onto the surface:
  - Lacing: down the front of each boot, a column of lighter six-sided panels between two wavy dark lines. [viewer: A Footwear, B front]
  - Pleats: vertical lines on the white chest panel and on the front skirt. [viewer: A Face, B front]
  - Ruffles: rows of rounded shapes in a darker yellow with thin brown edges along the outer edges of the skirt tails. The same shapes show under both viewers' lighting. [viewer: B back, A Back]
  - Hair: darker strand lines along locks and ringlets. [viewer: B back]
  - Face: brows, lashes, crease line and lips, as covered in Axes 2 and 3. [viewer: A Face]
- Flat shapes drawn onto the surface:
  - Lace: on the choker, on both long sleeves and on the hems of the dark skirt panels. [viewer: B front, B back]
  - Scrolls: tan embroidery at the waist and down the sides of the bodice, a gold scroll on the right forearm, and a darker scroll on the grey-brown panels of the skirt. [viewer: B front, B side, B back]
  - A cream band and a cream three-lobed motif on the large yellow panels of the skirt. [viewer: B back]
- Knee creases: none visible on the boots. [viewer: B front, B back]

Technique: The surface lines and flat shapes are painted into the base-colour texture. [inferred] The outline method is unverified; the two recreations opened for Amber use different methods. [breakdown: S3, S4]

### 7. Clothing: structure, layering, trim, how pieces end

Observation:
- Hat: near-black, with a low flat-topped crown and a wide flat brim. A pleated ribbon with a row of pale studs runs round the crown. [viewer: B side, B back]
- Neck: a black lace choker with a row of gold beads and a gold diamond at its centre, and below it a gold necklace with three oval blue gems, the middle one the largest. [viewer: A Face, B front]
- Bodice: navy, sleeveless and close-fitting, edged in gold piping. It opens in a V over a white pleated panel that is topped by a gold band and a white ruffle. Three pairs of gold clasps face each other across the panel. [viewer: A Face, B front]
- Waist: the bodice ends in a point at the front with tan scroll embroidery and a gold ornament at its centre; a gold embroidered band runs down each side. [viewer: B front, B side]
- Back: the upper back is bare, crossed by gold straps with round studs. [viewer: B back]
- Sleeves: separate from the bodice. Each starts in a black puff edged with black lace, carries a navy bow with a lighter blue edge and a gold square knot, and has a yellow bow on its outer side. A white ruffle hangs below the puff. A tight brown-black sleeve then runs to the wrist. [viewer: B front, A Front Detail]
- Hips: a gold ship's wheel with navy insets sits on each hip on a black puffed bow, and a black sash crosses the front in two swags. [viewer: B front, A Front Detail]
- Front skirt: white, short and pleated, with a gold band above the hem and a second white layer under it. [viewer: B front]
- Back skirt: below a bow at the back of the waist, yellow rounded panels alternate with grey-brown panels that carry a darker scroll and a lace edge. Under them come two large yellow panels with a cream band, dark side panels with lace hems, and two long pointed yellow tails. The skirt is split down the centre back. [viewer: B back, A Back]
- From the front only the inner face of the skirt tails shows, behind the legs. [viewer: A Front, B front]
- Legs: thigh-high boots in brown-black. Each top is a band of gold pointed arches, with a near-black bow and a gold fan-shaped ornament below it at the front. Each ankle has a black bow with tails at the back. The toe is pointed; the heel is a tan block. [viewer: B front, A Footwear, B back]
- Lace edges are cut out: the background shows through small holes at the glove and sleeve cuffs, and the yellow cloth shows through drop-shaped holes in the hems of the dark skirt panels. [viewer: B front, B back]
- How pieces end: every edge is marked by contrast. The bodice ends in gold piping, the front skirt in a gold band, the skirt tiers in cream bands, lace hems or painted ruffles, the sleeves in lace cuffs, the boots in gold arches. [viewer: B front, B back]

Technique: Large forms, bows, clasps and wheels are geometry; lacing, lace patterns, scrolls and ruffles are painted. [inferred] One recreation says hand-painted shadows are baked into the character textures at seams and folds. [breakdown: S4] Whether the lace holes are cut with texture transparency or modelled is unverified; a close-up of a lace hem would resolve it.

### 8. Detail and ornament

Observation:
- Detail clusters: the hat; the neck and collarbone; both shoulders; the clasps on the bodice and the wheels at the hips; the boot tops; the ankles; and the ornament at the back of the waist. [viewer: B front, B back]
- Plain areas: the long mass of hair, the bare shoulders and chest, the front skirt, the large yellow panels of the tails, and the sides and backs of the boots. [viewer: B front, B back]
- Three motifs repeat at different sizes: [viewer: B front, B back, B side]
  - Bows: at the back of the hair, two on each sleeve top, under each hip wheel, at each boot top, at each ankle and at the back of the waist, twelve in all. [viewer: B front, B back, B side]
  - Faceted blue gems in gold frames: on the hat brim, beside the left eye, at both ears, three on the necklace, on both forearms, at the back of the waist with a drop below it, and at both ankles. [viewer: B front, B back, B side]
  - Gold lattice and pointed-arch work: the frame of the hat ornament, the boot tops, the straps across the back. [viewer: A Face, B front, B back]
- Asymmetry: the body and most garments are mirror-symmetric; these items differ between the sides. [viewer: B front, B side]
  - Hat: tilted lower on the right. On its right side sit a white feather, a white flower, two pale-yellow roses, a dusty dark-blue rose, upright yellow ribbon ends and black lace. On its left side a gold open-work diamond frame holds a blue gem, and a gold piece with a blue crystal hangs from the brim beside the left eye. [viewer: B side, B front, A Face]
  - Right arm: a gold-framed ornament with two blue gems and gold scrollwork on the forearm, and a black glove over the whole hand. [viewer: B side, B front]
  - Left arm: a plain lace-patterned sleeve with one blue gem at the wrist and a lace cuff; the hand is bare. [viewer: B front]
  - Shoulder bows: the left one carries a gold ornament with an orange centre, the right one a gold diamond-shaped clasp. [viewer: A Front Detail, B side]
- Gems: all blue, cut as ovals, diamonds or double-pointed crystals, except the orange centre of the ornament on the left shoulder. [viewer: B front, A Front Detail]
- At the back of the waist a gold open-work frame holds a blue gem above a blue crystal drop; a narrow pale strip hangs from it down the split of the skirt. [viewer: B back]
- Gold pieces carry three or four flat tones, one per facet. [viewer: A Face, B front]

Technique: Bows, clasps, wheels and gems are simple geometry with one flat tone per facet. [inferred] Which scrolls are raised and which are only painted is unverified; a close-up at a raking angle would resolve it.

### 9. Materials

Observation:
- How cloth, lace, metal and the gems respond to light: Not observable. In-game close-ups of the bodice clasps, a hip wheel, the necklace gems and a lace hem in direct sun, from two camera angles, would resolve it.
- The viewers show only the painting underneath. Gold is painted in three or four flat tones per piece and each gem in lighter and darker blue facets. [viewer: A Face, B front]
- The long sleeves and the glove read as a warm brown-black, about `#4E4841`, against the neutral near-black of the hat, about `#343337`. [viewer: B front] A community description calls the glove sheer. [community: S6] Whether skin shows through it in-game: Not observable.
- The inner face of the skirt tails reads differently in each viewer: a yellow that fades to cream in viewer A, a dull khaki, about `#937753`, in viewer B. [viewer: A Front, B front] Both are the viewers' own shading of a surface turned away from their light.

Technique: Unverified. One recreation describes metal as a matcap combined with a real-time specular term [breakdown: S4]; the other uses a matcap-style gradient lookup driven by the view and light directions. [breakdown: S3] Neither covers lace or sheer cloth.

### 10. Colour

Observation: Base colours were sampled from B front, B side and B back, the more evenly lit viewer. The viewer still lights the model, so values are approximate. [viewer: B front, B side, B back] Iris and lash values were sampled from viewer A's Face view, the largest view of the eyes. [viewer: A Face]

| Role | Where | Approx. base colour | Saturation, value |
|---|---|---|---|
| Dark base: near-black | Hat, sleeve puffs, hair bow, boot bows, choker | `#343337`, `#3E3E42`, `#414144`, `#3D3C41`, `#44403F` | 4–8%, 22–27% |
| Dark base: brown-black | Long sleeves, glove, boots | `#4E4841`, `#4C4743`, `#443F39` | 12–17%, 27–31% |
| Dark base: slate | Sash | `#484850` | 10%, 31% |
| Dark base: navy | Bodice, wheel insets, sleeve bows, hat rose | `#464D5F`, `#41495D`, `#4C5365`, `#4F5668` | 24–30%, 36–41% |
| Signature: yellow | Skirt tails and tiers, hat ribbon | `#EFBC69`, `#E8B563`, `#E2B567` | 54–57%, 89–94% |
| Yellow, painted darker | Ruffle shapes, tier shadows | `#CD9A4B` | 63%, 80% |
| Cream | Bands and motifs on the skirt | `#ECE5CD` | 13%, 93% |
| Skirt panels | Grey-brown, with scroll | `#544B3B` | 30%, 33% |
| Hair | Fringe and sides, lit ringlet | `#D9C196`, `#E9D2A5` | 29–31%, 85–91% |
| Skin | Face, shoulder | `#E7DBD0`, `#E7D9CC` | 10–12%, 91% |
| White | Chest panel, front skirt | `#EAEAEA`, `#EFEFED` | 0–1%, 92–94% |
| Gold | Clasps, waist ornament, boot tops, heels | `#B79F7F`, `#D7B28A`, `#A48B6B`, `#B3916C` | 31–40%, 64–84% |
| Boot panels | Lighter lacing panels | `#62574B` | 23%, 38% |
| Gems | Necklace, crystal by the eye, back ornament | `#356EBD`, `#3F67C1`, `#4D98D9` | 64–72%, 74–85% |
| Hat flower | Yellow rose | `#F5DD9E` | 36%, 96% |
| Lips | | `#CEB0AD` | 16%, 81% |
| Iris, viewer A | Top, bottom, cyan highlight | `#2E5C87`, `#ADDAE3`, `#3CDAF1` | 66%, 53%; 24%, 89%; 75%, 95% |
| Lash, viewer A | Band, red-brown strokes | `#23252E`, `#624340` | 24%, 18%; 35%, 38% |

- Area in bind pose, front view: near-black, brown-black and navy 42%; pale blonde hair with gold and cream 19%; the inner face of the yellow skirt tails 17%; white 11%; skin about 5%. Back view: pale blonde hair with gold and cream 35%; yellow 28%; dark neutrals 27%; white 6%. [viewer: B front, B back] Hair, gold and cream sit too close in colour to be counted apart.
- Saturation: only the yellow and the small blue gems are strongly saturated. Hair sits at about 30%, navy at 24–30%, the other darks below 20%. [viewer: B front, B back]
- The yellow sits almost entirely at the back and sides. From the front it shows only as the inner face of the skirt tails and as small bows. [viewer: B front, B back]
- Gold metal is a desaturated khaki, close to Amber's. Hair and gold share one hue, about 31–38°, and differ in value and saturation. [viewer: B front]
- Black: there is no pure black. The darkest cloth sits at 22–27% value; the lash band is darker, at about 18%. [viewer: B front, A Face]
- The dark colours come in three temperatures: neutral near-black on the hat and bows, warm brown-black on sleeves and boots, cool navy on the bodice. [viewer: B front]
- White: neutral, used for the chest panel, the front skirt and the sleeve ruffles. [viewer: B front]
- Viewer A, sampled as a check, agrees within a few percent: skin `#E8DDD3`, hat `#3D3D44`, boots `#423D39`, white `#DDDCDD`, lit hair `#E8CC9E`. [viewer: A Front]
- Lit tone and shadow tone per colour: Not observable. In-game shots of the same pose in direct sun and in shade would resolve it.

Technique: Each material region holds one flat base colour in the texture, with painted darker shapes at ruffles and tier edges. [inferred] One recreation reports that the game sets shadow colours per character with shadow ramps. [breakdown: S4] Unverified on Navia.

### 11. Weapon

Observation: Not observable. No view shows a weapon. Her weapon type is listed as claymore. [community: S5] An in-game shot with the weapon in hand, one with it stowed if it stays visible, and the weapon's name would resolve it.

Technique: Not observable, for the same reason.

### 12. Readability

Observation:
- From shape alone, five things identify her: the wide tilted dark hat; the long mass of pale hair ending in ringlets; a dark fitted bodice with a white centre; the layered yellow skirt with long tails; and long dark boots under a short white skirt. [viewer: B front, B back]
- From the front the figure is mostly dark and pale, with yellow as a backdrop shape behind the legs. From behind, hair and yellow cover almost two-thirds of the figure. [viewer: B front, B back]
- Hair and yellow are close in value, about 85–94%, and are separated by saturation, about 30% against 56%. [viewer: B back]
- The dark hat brim frames the face from above, and the dark choker and bodice frame it from below. [viewer: B front]
- In motion: Not observable. Three frames of a run cycle would resolve it.
- At a distance: Not observable. An in-game shot with the figure small in frame would resolve it.

Technique: The large blocks are separated by value at the front and by saturation at the back. [inferred]

### 13. Fit with the world

Observation: Not observable. In-game shots in Fontaine, her home region [community: S7], by day and with the figure small in frame, would resolve it.

Technique: The developer says characters and scenes are rendered in separate passes, and that characters receive real-time and ambient environment light through a 24-hour cycle. [official: S1]

## Comparison

### With other characters

Compared with [amber.md](amber.md), [xilonen.md](xilonen.md) and [clorinde.md](clorinde.md).

Shared:
- Face: smooth, with a small nose point and features painted on. [viewer: A Face]
- Eyes: a thick upper lash band with a wing and one upward spike, as on Amber and Xilonen; an iris darker at the top; a grey band on the white; painted highlights on the same sides in both eyes. [viewer: A Face]
- Lashes in two colours, red-brown on the inner half, as on Xilonen. [viewer: A Face]
- Hair: a cap plus solid pointed locks with painted strand lines and crisp tips. [viewer: B back]
- Painted lines and patterns on the surface, and darker painted shapes at folds. [viewer: B back]
- Gold metal: a desaturated khaki, `#B79F7F` here against `#BFAB86` on Amber. [viewer: B front]
- No pure black in the cloth. [viewer: B front]
- Detail in clusters with plain areas between, and asymmetry from one-sided accessories on a symmetric body. [viewer: B front]
- Every garment edge marked by contrast. [viewer: B front, B back]
- Palette built like Amber's and Clorinde's: a dark base, one saturated colour, white, and gold. [viewer: B front, B back]
- With Clorinde: a hat that hides the top of the head, white at the chest, blue gems in gold frames, and legs below the skirt hem at 53–54% of the height. [viewer: A Front]

Where Navia breaks the pattern:
- Outline: three shapes far wider than the body, the hat, the hair and the skirt tails. On the other three the outline stays close to the body or grows on one side only. [viewer: A Front]
- Hair: the largest single shape, pale, ending in ringlets modelled as spiral ribbons; no gradient. [viewer: B back]
- Ornament: at least a dozen bows and a dozen blue gems; the other three repeat their motifs less often. [viewer: B front, B back]
- Edges: lace with cut-out holes, an edge type not seen on the other three. [viewer: B front, B back]
- Colour placement: the saturated colour sits behind the figure. From the front it is 17% of the area and in the viewer's shade; from behind it is 28%. [viewer: B front, B back]
- Dark colours in three temperatures at once; Amber's lean red and Clorinde's lean blue. [viewer: B front]
- Eyes: a rounder opening than on Xilonen and Clorinde, and a star-shaped highlight. [viewer: A Face]
- Skin: bare shoulders, chest and back above a fully covered lower arm and leg; Clorinde shows only her face and neck. [viewer: B front, B back]

### Game-wide candidates

Supports: C1, C2, C3, C4, C6, C7, C8, C13, C14, C15, C16.

Supports in part: C5, C18.

Breaks: none.

The candidates and their evidence are in [aesthetics/_candidates.md](../aesthetics/_candidates.md).

## Sources

- S1. [Famitsu report (in Japanese) of miHoYo's GDC 2021 talk "'Genshin Impact': Crafting an Anime Style Open World", given by Haoyu Cai](https://www.famitsu.com/news/202107/23228135.html). Covers the character pipeline, separate passes for characters and scenes, the face shadow mask, and real-time and ambient light on characters. A press report of the talk, not the talk itself.
- S2. [miHoYo, Unite Seoul 2020, "From Mobile to Console: Genshin Impact's rendering technology on Console", slides by Zhenzhong Yi](https://image.docswell.com/s/UnityJapan/KWRPQ5-210617-unity-dojo20211mihoyozhenzhongyi). Covers the two rendering pipelines, PC and console against mobile.
- S3. [Adrian Mendez, "Genshin Impact Character Shader Breakdown (Unity URP)"](https://adrianmendez.artstation.com/projects/wJZ4Gg). A recreation in Unity; it does not claim the game uses the same methods.
- S4. [bjayers on ArtStation, "Blender NPR: Recreating the Genshin Impact Shader"](https://bjayers.artstation.com/blog/category/5). A recreation in Blender, mixed with statements about how the game behaves.
- S5. [GenshinBuilds, Navia](https://genshin-builds.com/en/character/navia). Names Yellow Velvet Salon as her default and only listed outfit, lists her weapon type as claymore, and lists her debut banner in version 4.3.
- S6. [MyAnimeList, Navia, appearance text credited to the Genshin Impact Wiki](https://myanimelist.net/character/248826). Lists the pieces of her outfit, counts four curls at the back of her hair and two in front, puts the glove on the right arm and calls it sheer.
- S7. [Gfinity Esports, "Genshin Impact Navia build"](https://www.gfinityesports.com/article/genshin-impact-navia-build). States that she is from Fontaine.

Tool documentation is listed under each brief.

## Open questions

1. Which game version do the viewer models come from?
2. How tall is the head under the hat? Every view hides its top, so the 6.9 to 8.1 head-heights above are an estimate. A viewer capture with the hat hidden, if the viewer allows it, would give the figure directly.
3. In-game shots that would lift this doc above Shape only. Record game version, platform and graphics preset with each, because PC and console use a different rendering pipeline from mobile. [official: S2]

   | Shot | Fills |
   |---|---|
   | Front, side and back, full body, idle, flat light | Axes 1, 5, 6 |
   | The same from farther away | Axes 6, 12 |
   | Face close-up, lit from the front and from the side | Axes 2, 3 |
   | Hair close-up from two camera heights, in daylight | Axis 4 |
   | Same pose in direct sun and in shade | Axes 5, 10 |
   | Bodice clasps, a hip wheel, necklace gems and a lace hem in sun, from two angles | Axes 8, 9 |
   | Weapon in hand, weapon stowed, and its name | Axis 11 |
   | Figure small in frame in Fontaine, by day | Axes 12, 13 |
   | Three frames of a run cycle | Axis 12 |

4. Are the lighter marks on her hair painted highlights? Both viewers show them, in different strengths. An in-game hair close-up from two angles would show whether they move.
5. Are the holes in the lace cut with texture transparency, or modelled?
6. Does the game draw brows on top of the fringe, as both viewers do?
7. Does skin show through the long sleeves and the glove in-game?
