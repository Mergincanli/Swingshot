# Clorinde (Genshin Impact)

Outfit: Sword of Honor, her default and the only outfit listed for her. [community: S5] The sheets carry no outfit name. The match rests on a community description of her look that lists the same pieces the views show: a white button-up shirt, a black underbust corset with four gold buttons, a short blue cape with epaulettes, and a long patterned cape with gold tassels hanging from the left shoulder. [community: S6] [viewer: A Front, B front]

Game version or shot date: Viewer captures provided on 13 November 2026. The game version the viewer models come from is unverified. Her debut banner ran in version 4.7. [community: S5]

Confidence: Shape only. Two viewer sheets cover the character and there is no in-game shot.

Shots used:
- Viewer sheet A: 16 labelled views (Front, 3/4 Front, 1/4 Front, Side, 3/4 Back, 1/4 Back, Back, Face, 1/4 Face, 3/4 Face, Footwear, Front Detail, 3/4 Front Detail, Back Detail, 3/4 Back Detail, Back of Head). Bind pose, violet backdrop, viewer lighting. Tagged `[viewer: A <view>]`.
- Viewer captures B: four captures (front, side, back, outfit front). White backdrop, viewer lighting, bind pose. The outfit front capture shows the clothing from collar to thigh with no head, and leaves out the hat, the long drape, the banner and the boots. Tagged `[viewer: B <view>]`.

Links and capture details are in [references/shots.md](../references/shots.md). What each viewer gets right and wrong is in [references/viewers.md](../references/viewers.md).

## Production brief: Blender

Partial: shape only. These rules cover the model and its textures. There are no rules yet for outlines, shading bands, highlights, rim light or how materials respond to light.

1. Block out a tall, slim build in orthographic front and side views: about seven head-heights with high heels included, a waist about 0.6 heads wide, hips about one head wide, and legs below a short skirt taking a little over half the height. (Axis 1)
2. Add headwear as its own shape that covers the top of the skull and rises about three-quarters of a head above it, and let its lowest point reach eye level while both irises stay visible. (Axis 1)
3. Model the face as a smooth surface whose only clear relief is a small nose tip, and paint brows, lash bands, crease lines and a pale lip line in the face texture. (Axis 2)
4. Paint each eye in Texture Paint as a narrow opening under a thick lash band, with an iris that runs from dark at the top to a bright rim at the bottom and one white highlight in the same place in both eyes. (Axis 3)
5. Build hair from a smooth cap, a few long, thin, pointed front locks and one long tapered tail, and paint strand lines and any differently coloured lock onto them instead of modelling strands. (Axis 4)
6. Draw seams, creases, pleat lines and cloth patterns as thin strokes and flat shapes on the base-colour texture in Texture Paint, and keep them out of the mesh. (Axis 6)
7. Layer the upper body from the inside out (shirt, corset, short cape, shoulder boards) and end every piece with a contrasting edge: a metal border, a white cuff, a lining in a brighter tone of the same hue, or a row of tassels. (Axis 7)
8. Build fringe, tassels, studs and beads from simple faceted shapes, and repeat one small motif, here a diamond, at several sizes from collar to boots. (Axis 8)
9. Model the body and its symmetric garments with a Mirror modifier, then add long hanging cloth on one side and a cord with a tassel on the other as separate, unmirrored objects. (Axis 8)
10. Give each material region one flat base colour: dark, low-saturation tones over about a third of the figure, one blue-violet family at about 40–48% saturation, near-white at the neck, wrists and ankles, and metal as a greyed khaki-gold at about 20–24% saturation and 50–58% value. (Axis 10)

Sources for this brief:
- Orthographic view: [Blender Manual, Perspective/Orthographic](https://docs.blender.org/manual/en/latest/editors/3dview/navigate/projections.html)
- Texture Paint: [Blender Manual, Texture Paint introduction](https://docs.blender.org/manual/en/latest/sculpt_paint/texture_paint/introduction.html)
- Mirror modifier: [Blender Manual, Mirror Modifier](https://docs.blender.org/manual/en/latest/modeling/modifiers/generate/mirror.html)

## Production brief: Three.js / WebGPU

Partial: shape only. The model and textures are authored elsewhere; these rules cover what the runtime must keep intact. There are no rules yet for shading, outlines or lighting.

1. Check proportions through an `OrthographicCamera`, because the two viewers' cameras disagree: the skirt hem sat 38% of the way from chin to sole in one and 40% in the other. (Axis 1)
2. Set `colorSpace = SRGBColorSpace` on every base-colour texture so the flat colours display as authored. (Axis 10)
3. Take seams, creases, pleat lines and cloth patterns from the base-colour map, and do not generate them with an edge-detection pass. (Axis 6)
4. Keep the eye highlight in the eye's base-colour map, and do not add a specular or reflection highlight to the eye material. (Axis 3)
5. Render hair locks, the hair tail and ribbon tails as opaque geometry with no alpha fade at the tips. (Axis 4)

Sources for this brief:
- Orthographic camera: [three.js docs, OrthographicCamera](https://threejs.org/docs/pages/OrthographicCamera.html)
- Texture colour space: [three.js manual, Color Management](https://threejs.org/manual/pages/color-management.html) and [three.js docs, Texture](https://threejs.org/docs/pages/Texture.html)

## Dissection

Left and right are the character's own. Measurements and colour values are approximate.

### 1. Silhouette and proportions

Observation:
- The hat hides the top of the head from the front, so head height was measured in the Side view, where the hair cap shows under the brim. Height is about 7.0 head-heights from the top of the visible hair cap to the soles, high heels included (head 41 px, figure 292 px). [viewer: A Side]
- The hat still covers the highest point of the skull, so the true figure lies between 6.7 and 7.3. [inferred]
- The same measure gives 6.7 in B side (head 156 px, figure 1050 px). [viewer: B side] That viewer is not used for proportions, as recorded in [references/viewers.md](../references/viewers.md).
- The hat and its plume rise about three-quarters of a head above the hair cap (31 px against a 41 px head). [viewer: A Side]
- The shoulder boards span about 1.5 heads from edge to edge, the waist is about 0.6 heads wide and the skirt at the hips about 1.0. [viewer: A Front] The head unit for these widths was carried over from the Side view by the chin-to-sole length.
- The skirt hem sits about 47% of the way down from the top of the head, so the legs below it take about 53% of the height. The knee sits at about 68%. [viewer: A Side]
- Head silhouette: a hat with a tall crown and a brim folded into three points, one low over the forehead and two swept up at the sides, with a plume arcing over the top. [viewer: B front, B side] A community description calls it a bycocket hat. [community: S6]
- Hair adds long thin locks beside the face, one lock that flicks out sideways at ear level on the left, and a thin tail that hangs down the back to the hem of the skirt. [viewer: B front, B back]
- Upper body: flat shoulder boards and a short cape widen both shoulders; the cape ends in points at elbow level. [viewer: B outfit front, B front]
- The outline is one-sided below the waist. On the left a drape and a two-tailed banner hang to the ankle; on the right only a tassel and a crystal hang at the hip. [viewer: B front, B back]
- The legs are slim and read as one smooth shape from skirt to ankle, ending in ankle boots with a wide white cuff and a thin high heel. [viewer: A Front, B side]
- The outfit front capture shows the arms lowered; every other view shows them in bind pose. [viewer: B outfit front, B front]

Technique: Proportions belong to the mesh. [inferred] The developer describes character models as built from three-view drawings to shared standards for tessellation, topology and textures. [official: S1]

### 2. Head and face construction

Observation:
- The face is a smooth surface with little modelled relief. The nose is a small point with no bridge line or nostrils. [viewer: B side, A Face]
- The mouth is a short, pale pink line with barely raised lips. [viewer: A Face, B front]
- The chin is small and pointed and the jaw has no visible angle. [viewer: A Face, A 3/4 Face]
- The eyes are narrow and set wide: the gap between them is about 1.3 eye-widths. [viewer: A Face]
- Eyebrows are thin, arched, dark-blue lines in the hue of the hair. [viewer: B front, A Face]
- A small pale dot sits on the tip of the nose in viewer B. [viewer: B front] It does not show at the size of viewer A's Face view.
- The face is partly covered: the hat's front point and one thin lock that crosses the face diagonally hide part of the right eye. [viewer: A Face, B front]
- Human ears are visible beside the front locks. Each carries a dark stud with a blue drop. [viewer: A Front Detail, B front]
- How far down the head the eyes sit: Not observable. The hat hides the top of the head. A higher-resolution side view, where the hair cap shows under the brim, would resolve it.
- Whether brows or eyes show through the hair in-game: Not observable. An in-game face close-up would resolve it.
- Face shading: Not observable. In-game face shots lit from the front and from the side would resolve it.

Technique:
- Brows, lash bands, lip line and the nose dot are painted in the face texture. [inferred]
- The developer says faces use a dedicated shadow mask that responds to light direction, because standard shading could not give the wanted face. [official: S1] Two recreations describe it as a face shadow texture [breakdown: S3] and a custom face light map. [breakdown: S4]

### 3. Eyes

Observation:
- The eye opening is narrow: the visible opening under the lash is about a third as high as the eye is wide. [viewer: A Face]
- Upper lash: a thick, near-black band that covers the top of the iris. It ends in a short point at the outer corner and in a downward point with thin strokes at the inner corner. [viewer: A Face, A 3/4 Face, B front]
- No upward spike rises from the lash band in any view. [viewer: A Face, A 1/4 Face, A 3/4 Face]
- A thin crease line sits above the lash. Two or three small dark marks sit under the lower edge of the iris; no dark lower lash line is drawn. [viewer: A Face, B front]
- The white of the eye has a grey-lilac band under the upper lash. [viewer: A Face, B front]
- Iris: dark indigo at the top, about `#31316E`, then a brighter violet ring, then a pink band along the lower rim. [viewer: A Face, B front]
- Each iris has one white crescent at the bottom centre, sitting on the pink band. It is in the same place in both eyes and unchanged across three camera angles and both viewers. [viewer: A Face, A 1/4 Face, A 3/4 Face, B front]
- The iris is about 17 px wide in the largest view, so pupil shape and finer detail are Not observable. An in-game face close-up would resolve it.

Technique: Iris, lashes and highlight are painted in a texture, since the highlight does not move with the viewer's camera. [inferred] Whether the game shades the eyes or adds a moving highlight: Not observable. In-game face close-ups from two angles would resolve it.

### 4. Hair: shape language, clumps, highlight, shadow

Observation:
- A smooth cap covers the skull; the hat hides its top. [viewer: B side, A Back of Head]
- Front: four to six long, thin, pointed locks frame the face and reach the collarbone. Their tips flick outward. [viewer: B front, A Face]
- One thin lock crosses the face diagonally from the hat's front point to the right cheek. [viewer: A Face, B front]
- One lock on the left is a lighter blue than the rest and sweeps sideways to a point at ear level. [viewer: B front, A Front Detail]
- Back: the hair is gathered low at the nape into one tail of a few long, tapered clumps that reaches the hem of the skirt. [viewer: B back, A Back]
- A black ribbon bow ties the tail. Its two thin tails hang to hip level. [viewer: B back, A Back of Head]
- Short loose locks flick out on both sides of the nape. [viewer: B back]
- Thin darker lines run along the clumps. There are no individual strands. [viewer: B back, B side]
- Clump edges are crisp, with no fade at the tips. [viewer: B front, B back]
- Base colour is a dark navy, about `#464A60` at the front and `#4E5168` on the tail; the lighter lock is about `#4C5E7F`. [viewer: B front, B back] There is no clear root-to-tip gradient; the end of the tail is slightly bluer, about `#4B5670`. [viewer: B back]
- A thin pale broken line runs down the strand in front of the left temple in both viewers. [viewer: A 3/4 Face, B front]
- Viewer A draws a row of crisp white jagged marks round the crown and a few low on the tail. Viewer B draws none in those places. [viewer: A Back of Head, A Back Detail, B back, B side] The difference is recorded in [references/viewers.md](../references/viewers.md); neither is evidence for the game's highlight.
- Highlight shape, shadow tone and whether the highlight moves with the camera: Not observable. Two in-game hair close-ups from different camera heights, in daylight, would resolve it.

Technique:
- Hair is built from solid clumps, with strand lines and the lighter lock painted on. [inferred]
- One recreation reports that shine marks painted in the hair textures mask a real-time specular highlight. [breakdown: S4] The white marks in viewer A would fit such a mask shown as plain colour; this is unverified. See candidate C17 in [aesthetics/_candidates.md](../aesthetics/_candidates.md).

### 5. Skin: tone, shading bands, rim light

Observation:
- Base tone is very pale and warm, about `#E2D1C2` on the forehead and `#E5D7CB` on the cheek. [viewer: B front] Viewer A agrees, at about `#EDD9CD`. [viewer: A Front]
- Skin shows only on the face, the ears and the neck. Blouse, gloves, tights and boots cover everything else. [viewer: B front, B back]
- Skin takes about 2% of the figure's area from the front. [viewer: B front]
- Shading bands and rim light: Not observable. In-game shots in direct sun and in shade would resolve it.

Technique: Unverified. See candidates C9, C10 and C12 in [aesthetics/_candidates.md](../aesthetics/_candidates.md).

### 6. Outlines and inner lines

Observation:
- Outlines: Not observable. Neither viewer draws one. [viewer: A Front, B front] In-game front, side and back shots at two distances would resolve it.
- Lines drawn onto the surface:
  - Seams: two vertical seams and a button placket on the blouse, a seam along each sleeve, seams on the corset, thin dark seams on the gloves. [viewer: B outfit front]
  - Creases: small darker fold shapes beside the blouse buttons and one wavy fold line on each boot cuff. The same shapes show under both viewers' lighting. [viewer: B outfit front, A Face, B front]
  - Pleats: darker stripes on a grey fan-shaped panel at the back of the waist. [viewer: B back, A Back Detail]
  - Hair: darker strand lines along the clumps. [viewer: B back]
  - Face: brows, lashes, crease line and lip line, as covered in Axes 2 and 3. [viewer: A Face]
- Flat shapes drawn onto the surface:
  - A grey-lilac scroll pattern on the short cape. [viewer: B outfit front, B back]
  - Gold scrollwork and a gold border on the banner, on both of its faces. [viewer: B front, B back]
  - A pale emblem on the jabot and paler stripes on the bow under the brooch. [viewer: B outfit front]
  - Pale gold line art on the cuffs and tan scrolls on the front of the skirt. [viewer: B outfit front]
  - A dark-on-dark pointed shape at the bottom of the corset. [viewer: B outfit front]
- Knee creases: none visible on the tights. [viewer: B front, B back]

Technique: The surface lines and flat shapes are painted into the base-colour texture. [inferred] The outline method is unverified; the two recreations opened for Amber use different methods. [breakdown: S3, S4]

### 7. Clothing: structure, layering, trim, how pieces end

Observation:
- Hat: a tall blue-violet crown with a paler V-shaped piping line, and a near-black brim folded into three points. A gold ornament sits on each side of the brim. A pale lavender plume arcs over the crown and trails behind, and shorter saturated blue feathers sit at the back. [viewer: B front, B side, B back]
- Neck: a tall charcoal collar with gold four-point stars joined by a gold line, over a white ruffled inner collar. [viewer: B outfit front]
- Blouse: white, close-fitting, with silver diamond-shaped buttons down the placket. [viewer: B outfit front]
- Neckwear: an oval purple gem in a curved gold frame sits on a blue-violet bow. Below it hangs a two-layer jabot: a blue-violet front with a pale emblem and a small cyan diamond, over a darker pleated layer with a gold edge. [viewer: B outfit front, A Face]
- Corset: charcoal, from under the bust to the hips, with two round embossed gold buttons on each side, a slate-blue centre panel crossed by dark straps, and a pointed lower edge. [viewer: B outfit front]
- Short cape: blue-violet, worn over both shoulders, ending in a point on each side at elbow level. Each point carries a dark-blue raised knot shape, and a brighter blue under-layer with a jagged edge shows below it. [viewer: B outfit front]
- Shoulder boards: a flat gold bar on each shoulder. Below each, on the cape, a row of gold diamonds and a row of long gold kite-shaped drops. [viewer: B outfit front, A Face]
- Sleeves: charcoal and close-fitting, ending in a large white turned-back cuff with a band of open gold diamonds along its upper edge. [viewer: B outfit front]
- Gloves: white, with a gold ornament at the wrist. [viewer: B outfit front, B back]
- Skirt: charcoal, short and fitted, with two slits at the front. The right slit shows a strap with a silver buckle and a silver diamond stud that runs down to the garter. The left slit shows a bright blue lining. [viewer: B outfit front]
- Left side only: a drape in several scalloped layers of pale to mid periwinkle, and over it a long dark blue-violet banner that splits into two pointed tails. Each tail ends in a row of four gold tassels, each topped by a gold diamond bead. The banner reaches the ankle. [viewer: B back, B front, A 3/4 Back Detail]
- Legs: sheer grey-mauve tights from skirt to boot. A black garter band with faceted studs sits on each thigh, with an ornate centre piece that ends in a long downward spike. [viewer: B outfit front, B front]
- Boots: ankle boots with a near-black pointed toe section, a white upper section with gold studs, a wide folded white cuff with a gold ornament on its outer side, and a thin gold heel and gold sole edge. [viewer: A Footwear, B side]
- How pieces end: every edge is marked by contrast. The banner ends in a gold border and tassels, the sleeves in white cuffs with a gold band, the cape in dark knot shapes over a brighter lining, the skirt slit in a blue lining, the boots in a white cuff and gold trim. No edge is frayed or faded. [viewer: B outfit front, B front, B back]

Technique: Large forms, trims, drops and tassels are geometry; seams and patterns are painted. [inferred] One recreation says hand-painted shadows are baked into the character textures at seams and folds. [breakdown: S4] Whether the crossed straps on the corset panel are modelled or painted is unverified; a close-up at a raking angle would resolve it.

### 8. Detail and ornament

Observation:
- Detail clusters: the hat; the neck, chest and shoulders (collar, brooch, jabot, shoulder boards, cord); the cuffs; the corset buttons and the front of the skirt; the garters; the boots; and the tasselled end of the banner. [viewer: B front, B outfit front, B back]
- Plain areas: the sleeves, the body of the skirt, the tights, the large drape, the body of the short cape apart from its faint pattern, and the length of the hair. [viewer: B front, B back]
- One motif repeats at many sizes, the diamond or four-point star: on the collar, in the rows on the shoulders, as the shoulder drops, in the cuff bands, as blouse buttons, on the skirt front, as garter studs, as the beads above the banner's tassels and on the back of a garter. [viewer: B outfit front, B front, B back]
- A second motif, a three-lobed pointed flower shape, appears on the hat ornaments, the jabot emblem, the bottom of the corset and the boot cuffs. [viewer: B front, B outfit front, B side]
- Hanging pieces recur: shoulder drops, the cord's tassel, the banner's eight tassels, the earrings. [viewer: B front, B back]
- Asymmetry: the body and most garments are mirror-symmetric; these items sit on one side only. [viewer: B front, B back]
  - Right: a braided gold cord that loops from the shoulder board across the front and the back and ends at the hip in a long gold tassel beside a cyan crystal shard; the garter strap in the skirt slit. [viewer: B outfit front, B front, B back]
  - Left: the layered drape and the banner; the lighter-blue hair lock; the blue lining in the skirt slit. [viewer: B front, B back]
  - Across the face: the diagonal lock that covers part of the right eye. [viewer: A Face]
- Gems: the oval purple gem at the collar, painted with a lighter swirl; two cyan teardrops at the upper back, one each side of the spine, each above a large open gold diamond; the cyan crystal shard at the right hip; the blue earring drops; the small cyan diamond on the jabot. [viewer: B outfit front, B back, B front]
- A gold diamond stud sits at the back of the right garter; the banner hides the left one. [viewer: B back]
- Gold pieces carry two or three flat tones, one per facet. [viewer: B outfit front, B back]

Technique: Drops, studs, beads and tassels are simple faceted geometry with one flat tone per facet. [inferred] Which emblems are raised and which are only painted is unverified; a close-up at a raking angle would resolve it.

### 9. Materials

Observation:
- How cloth, metal, the tights, the plume and the gems respond to light: Not observable. In-game close-ups of the shoulder boards, the brooch, the tights and the plume in direct sun, from two camera angles, would resolve it.
- The viewers show only the painting underneath. Gold is painted in two or three flat tones per piece, the purple gem with a lighter swirl, the crystals with lighter and darker facets. [viewer: B outfit front, B back]
- In every view of both viewers the tights are lighter and warmer along the middle of each leg, about `#7D6D72`, and darker toward its outline, about `#60585E`. The tone follows the camera, not the surface. [viewer: A Front, A Side, B front, B back] This is the viewers' rendering and is not evidence for the game.
- The plume reads paler and greyer than the cloth, about `#9CA2B8`. [viewer: B back] Whether it is see-through in-game: Not observable.

Technique: Unverified. One recreation describes metal as a matcap combined with a real-time specular term [breakdown: S4]; the other uses a matcap-style gradient lookup driven by the view and light directions. [breakdown: S3] Neither covers sheer legwear.

### 10. Colour

Observation: Base colours were sampled from B front and B back, the more evenly lit viewer. The viewer still lights the model, so values are approximate. [viewer: B front, B back]

| Role | Where | Approx. base colour | Saturation, value |
|---|---|---|---|
| Dark base: charcoal | Corset, skirt, sleeves, collar | `#3F4048`, `#40414D`, `#3C3C46`, `#333537` | 7–17%, 22–30% |
| Dark base: near-black | Hat brim, boots, garters, hair ribbon | `#31333C`, `#383D42`, `#393C43`, `#434546` | 4–18%, 24–27% |
| Dark base: hair | Front, tail | `#464A60`, `#4E5168` | 25–27%, 38–41% |
| Hair accent | Lighter lock | `#4C5E7F` | 40%, 50% |
| Signature: blue-violet | Hat crown, short cape, banner | `#514F90`, `#524F83`, `#434379` | 40–45%, 47–56% |
| Signature, brighter | Drape, cape lining, jabot | `#5356A0`, `#5B5396`, `#7168A7` | 38–48%, 59–65% |
| Signature, palest | Top layer of the drape | `#9FAADE` | 28%, 87% |
| White | Blouse, cuffs, gloves, boot cuffs | `#E5E4E6`, `#E7E7EB`, `#DCDCE0`, `#DADADE` | 1–2%, 87–92% |
| Tights | Middle of the leg, edge | `#7D6D72`, `#60585E` | 13%, 49%; 8%, 38% |
| Skin | Forehead, cheek | `#E2D1C2`, `#E5D7CB` | 11–14%, 89–90% |
| Gold | Tassels, corset buttons, shoulder boards | `#837464`, `#938576`, `#7A6E62` | 20–24%, 48–58% |
| Accent | Corset centre panel | `#3F4A65` | 38%, 40% |
| Accent | Skirt lining | `#35468F` | 63%, 56% |
| Accent | Hat feathers | `#5068B8` | 57%, 72% |
| Gems | Collar gem, hip crystal, back teardrops, earrings | `#A665D1`, `#2D95B1`, `#5298E3`, `#2666C3` | 52–81%, 69–89% |
| Plume | Hat | `#9CA2B8` | 15%, 72% |

- Area in bind pose, front view: charcoal, near-black and hair 33%, blue-violet 20%, tights 18%, white 16%, gold 8%, skin 2%. Back view: charcoal, near-black and hair 29%, blue-violet 27%, tights 16%, gold 16%, white 10%. [viewer: B front, B back]
- Saturation: the large areas are low to medium. The blue-violet family sits at 38–48%, apart from its palest layer. Only small pieces go higher: the skirt lining, the hat feathers and the gems. [viewer: B front, B back]
- Gold metal is a greyed khaki, darker and less saturated than on Amber and Xilonen. [viewer: B front, B back]
- Black: there is no pure black. The darkest areas sit at 22–27% value. [viewer: B front]
- White: neutral to slightly cool, placed at the neck, chest, wrists, hands and ankles. [viewer: B front]
- Hue: every dark colour leans blue or is close to neutral, hue 200–240°. Hair, cloth and gems stay inside one band from blue through violet to purple; gold and skin are the only warm colours. [viewer: B front, B back]
- Viewer A, sampled as a check, agrees within a few percent: hair `#444869`, hat crown `#494B93`, drape `#5559AF`, skirt `#3C3C4B`, gold `#80705C`, white `#D7D7D9`. [viewer: A Front]
- Iris values other than the top tone were not sampled: Not observable at this size. A close-up would resolve it.
- Lit tone and shadow tone per colour: Not observable. In-game shots of the same pose in direct sun and in shade would resolve it.

Technique: Each material region holds one flat base colour in the texture, with a few painted darker shapes. [inferred] One recreation reports that the game sets shadow colours per character with shadow ramps. [breakdown: S4] Unverified on Clorinde.

### 11. Weapon

Observation: Not observable. No view shows a weapon. Her weapon type is listed as sword. [community: S5] An in-game shot with the weapon in hand, one with it stowed if it stays visible, and the weapon's name would resolve it.

Technique: Not observable, for the same reason.

### 12. Readability

Observation:
- From shape alone, five things identify her: the three-pointed hat with its plume; a slim dark figure with widened, gold-edged shoulders; the long one-sided banner with its row of gold tassels; white cuffs, gloves and boot cuffs at the ends of the limbs; and the thin tail of hair. [viewer: B front, B back]
- From behind, the short cape, the tail of hair and the banner cover most of the body, and gold takes about a sixth of the area. [viewer: B back]
- Neighbouring blocks differ in value: white at about 90%, blue-violet at 47–63%, tights at about 49%, charcoal at 22–30%. [viewer: B front]
- The face sits between a dark hat and dark hair, so the pale face and the white collar below it are the lightest shapes on the upper body. [viewer: B front]
- In motion: Not observable. Three frames of a run cycle would resolve it.
- At a distance: Not observable. An in-game shot with the figure small in frame would resolve it.

Technique: The large blocks are separated by value, inside one cool hue band; white marks the ends of the limbs. [inferred]

### 13. Fit with the world

Observation: Not observable. In-game shots in Fontaine, where her listing places her [community: S5], by day and with the figure small in frame, would resolve it.

Technique: The developer says characters and scenes are rendered in separate passes, and that characters receive real-time and ambient environment light through a 24-hour cycle. [official: S1]

## Comparison

### With other characters

Compared with [amber.md](amber.md) and [xilonen.md](xilonen.md).

Shared:
- Face: smooth, with a small nose point and features painted on. [viewer: A Face]
- Eyes: a thick upper lash band, an iris darker at the top, a grey band on the white, and a painted highlight placed the same way in both eyes. [viewer: A Face]
- Hair: a cap plus solid pointed clumps with painted strand lines and crisp tips. [viewer: B back]
- Painted lines: seams, creases and patterns drawn on the surface. [viewer: B outfit front]
- Gold metal: a desaturated khaki with flat facets. [viewer: B outfit front]
- No pure black. [viewer: B front]
- Detail in clusters with plain areas between, and asymmetry from one-sided accessories on a symmetric body. [viewer: B front, B back]
- Every garment edge marked by contrast. [viewer: B outfit front]
- Palette built like Amber's: a dark base, one colour family, white, and gold. [viewer: B front]
- Height close to both: about 7.0 head-heights against 6.9 and 7.4, with legs a little over half. [viewer: A Side]

Where Clorinde breaks the pattern:
- Eyes: narrow and set wide, 1.3 eye-widths apart against 1.0 on Amber and 0.75 on Xilonen; no upward lash spike; the highlight sits at the bottom of the iris, not the top. [viewer: A Face]
- Hair: long thin locks and one tail, where Amber has fanned locks and Xilonen curled clumps; no root-to-tip gradient; one lock in a second colour. [viewer: B front, B back]
- Headwear: the hat hides the top of the head and part of one eye; neither other character has a hat. [viewer: A Face]
- Skin: about 2% of the area from the front, against 7% on Amber and 35% on Xilonen. [viewer: B front]
- Gold: darker and greyer, about `#837464` against `#BFAB86` and `#AB9873`. [viewer: B front]
- Dark colours lean blue; Amber's lean red and Xilonen's are close to neutral. [viewer: B front]
- Hanging cloth: a short cape, a layered drape and a banner sit on top of the fitted garments; Amber has none and Xilonen has only her coat tails. [viewer: B back]
- Legwear: sheer tights, a material not seen on the other two. [viewer: B front]
- Gold from behind: about 16% of the area, against 4% on Amber. [viewer: B back]

### Game-wide candidates

Supports: C1, C2, C3, C4, C6, C7, C8, C13, C14, C16, C18.

Supports in part: C5, C15.

Breaks: none.

The candidates and their evidence are in [aesthetics/_candidates.md](../aesthetics/_candidates.md).

## Sources

- S1. [Famitsu report (in Japanese) of miHoYo's GDC 2021 talk "'Genshin Impact': Crafting an Anime Style Open World", given by Haoyu Cai](https://www.famitsu.com/news/202107/23228135.html). Covers the character pipeline, separate passes for characters and scenes, the face shadow mask, and real-time and ambient light on characters. A press report of the talk, not the talk itself.
- S2. [miHoYo, Unite Seoul 2020, "From Mobile to Console: Genshin Impact's rendering technology on Console", slides by Zhenzhong Yi](https://image.docswell.com/s/UnityJapan/KWRPQ5-210617-unity-dojo20211mihoyozhenzhongyi). Covers the two rendering pipelines, PC and console against mobile.
- S3. [Adrian Mendez, "Genshin Impact Character Shader Breakdown (Unity URP)"](https://adrianmendez.artstation.com/projects/wJZ4Gg). A recreation in Unity; it does not claim the game uses the same methods.
- S4. [bjayers on ArtStation, "Blender NPR: Recreating the Genshin Impact Shader"](https://bjayers.artstation.com/blog/category/5). A recreation in Blender, mixed with statements about how the game behaves.
- S5. [GenshinBuilds, Clorinde](https://genshin-builds.com/en/character/clorinde). Names Sword of Honor as her default and only listed outfit, lists her weapon type as sword, places her in the Court of Fontaine, and lists her debut banner in version 4.7.
- S6. [MyAnimeList, Clorinde, appearance text credited to the Genshin Impact Wiki](https://myanimelist.net/character/248827). Lists the pieces of her outfit, names the hat a bycocket, and puts the long cape on the left shoulder.

Tool documentation is listed under each brief.

## Open questions

1. Which game version do the viewer models come from?
2. How tall is the head under the hat? The Side view gives 6.7 to 7.3 head-heights. A viewer capture with the hat hidden, if the viewer allows it, would give the figure directly; a higher-resolution side view would narrow it.
3. In-game shots that would lift this doc above Shape only. Record game version, platform and graphics preset with each, because PC and console use a different rendering pipeline from mobile. [official: S2]

   | Shot | Fills |
   |---|---|
   | Front, side and back, full body, idle, flat light | Axes 1, 5, 6 |
   | The same from farther away | Axes 6, 12 |
   | Face close-up, lit from the front and from the side | Axes 2, 3 |
   | Hair close-up from two camera heights, in daylight | Axis 4 |
   | Same pose in direct sun and in shade | Axes 5, 10 |
   | Shoulder boards, brooch, tights and plume in sun, from two angles | Axes 8, 9 |
   | Weapon in hand, weapon stowed, and its name | Axis 11 |
   | Figure small in frame in Fontaine, by day | Axes 12, 13 |
   | Three frames of a run cycle | Axis 12 |

4. Are the white marks on her hair in viewer A painted highlights? Viewer B does not show them. An in-game hair close-up from two angles would show whether they exist and whether they move.
5. Do the tights change tone toward the outline of the leg in-game, as they do in both viewers?
6. Are the crossed straps on the corset panel modelled or painted?
