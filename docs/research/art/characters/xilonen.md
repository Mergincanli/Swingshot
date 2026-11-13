# Xilonen (Genshin Impact)

Outfit: Gold-Draped Gorge, her default and the only outfit listed for her. [community: S5] The listing describes it as a golden coat over short inner garments. [community: S5] Viewer sheet A shows exactly that. [viewer: A Front] Viewer captures B show the same inner garments without the coat, the chest medallion and the spiked wrist cuff. [viewer: B front] Which of the two is her standing look in-game is unverified; an in-game shot would settle it.

Game version or shot date: Viewer captures provided on 13 November 2026. The game version the viewer models come from is unverified. The character was added in version 5.1. [community: S5]

Confidence: Shape only. Two viewer sheets cover the character and there is no in-game shot.

Shots used:
- Viewer sheet A: 16 labelled views (Front, 3/4 Front, 1/4 Front, Side, 3/4 Back, 1/4 Back, Back, Face, 1/4 Face, 3/4 Face, Footwear, Front Detail, 3/4 Front Detail, Back Detail, 3/4 Back Detail, Back of Head). Bind pose, amber backdrop, viewer lighting, coat on. The Footwear view shows no feet. Tagged `[viewer: A <view>]`.
- Viewer captures B: three captures (front, side, back). White backdrop, viewer lighting, coat off, arms in bind pose, tail hanging. Tagged `[viewer: B <view>]`.

Links and capture details are in [references/shots.md](../references/shots.md). What each viewer gets right and wrong is in [references/viewers.md](../references/viewers.md).

## Production brief: Blender

Partial: shape only. These rules cover the model and its textures. There are no rules yet for outlines, shading bands, highlights, rim light or how materials respond to light.

1. Block out a tall build in an orthographic front view: about 7.4 head-heights including platform shoes, shoulders about 1.2 heads wide, waist about 0.6, and legs a little over half the height. (Axis 1)
2. Model the face as a smooth surface whose only clear relief is a small nose tip and slightly raised lips, and paint brows, lash lines, lip colour and a small highlight dot on the nose tip in the face texture. (Axis 2)
3. Paint each eye in Texture Paint with a thick lash band, an iris that is darker at the top than at the bottom, a pupil mark and one highlight placed identically in both eyes. (Axis 3)
4. Build hair from a smooth cap plus thick, curled clumps with hooked, pointed tips, model braids as their own geometry, and paint strand lines and the root-to-tip colour gradient instead of modelling strands. (Axis 4)
5. Shape fur on ears and tail as a few large jagged points, and paint its bands with zigzag borders instead of modelling fine fur. (Axis 4)
6. Draw knee creases, seams, strand lines and flat body marks as thin strokes and flat shapes on the base-colour texture in Texture Paint, and keep them out of the mesh. (Axis 6)
7. Mark every garment edge with contrast: a trim band, a hard colour change, or a frayed fringe built from jagged pieces in a lighter colour. (Axis 7)
8. Build studs, plates and pendants from simple faceted shapes such as pyramids and diamonds, and repeat two or three such motifs across the whole design at different sizes. (Axis 8)
9. Model the body with a Mirror modifier, then add everything that exists on one side only, such as a single sleeve or a thigh strap, as separate, unmirrored objects. (Axis 8)
10. Give each material region one flat base colour, keep metal a desaturated khaki-gold at about 33–47% saturation, and let cloth, hair and gems carry the saturated colours. (Axis 10)

Sources for this brief:
- Orthographic view: [Blender Manual, Perspective/Orthographic](https://docs.blender.org/manual/en/latest/editors/3dview/navigate/projections.html)
- Texture Paint: [Blender Manual, Texture Paint introduction](https://docs.blender.org/manual/en/latest/sculpt_paint/texture_paint/introduction.html)
- Mirror modifier: [Blender Manual, Mirror Modifier](https://docs.blender.org/manual/en/latest/modeling/modifiers/generate/mirror.html)

## Production brief: Three.js / WebGPU

Partial: shape only. The model and textures are authored elsewhere; these rules cover what the runtime must keep intact. There are no rules yet for shading, outlines or lighting.

1. Check proportions through an `OrthographicCamera`, because the two viewers' perspective cameras gave 7.4 and 6.5 head-heights for the same model. (Axis 1)
2. Set `colorSpace = SRGBColorSpace` on every base-colour texture so the flat colours display as authored. (Axis 10)
3. Take knee creases, seams, strand lines and body marks from the base-colour map, and do not generate them with an edge-detection pass. (Axis 6)
4. Keep the eye highlight in the eye's base-colour map, and do not add a specular or reflection highlight to the eye material. (Axis 3)
5. Render see-through cloth panels with `transparent = true` and an `opacity` below 1, so the skin behind them stays visible. (Axis 7)
6. Render hair clumps and braids as opaque geometry with no alpha fade at the tips. (Axis 4)

Sources for this brief:
- Orthographic camera: [three.js docs, OrthographicCamera](https://threejs.org/docs/pages/OrthographicCamera.html)
- Texture colour space: [three.js manual, Color Management](https://threejs.org/manual/pages/color-management.html) and [three.js docs, Texture](https://threejs.org/docs/pages/Texture.html)
- Transparency: [three.js docs, Material](https://threejs.org/docs/pages/Material.html)

## Dissection

Left and right are the character's own. Measurements and colour values are approximate.

### 1. Silhouette and proportions

Observation:
- Height is about 7.4 head-heights from the top of the hair to the underside of the platform shoes (head 102 px, figure 756 px). [viewer: A Front]
- The same measure gives 6.5 in B front (head 170 px, figure 1098 px). [viewer: B front] That capture is not used for proportions, as recorded in [references/viewers.md](../references/viewers.md).
- Shoulders are about 1.2 heads wide, the waist about 0.6 and the hips about 1.1. [viewer: A Front]
- Legs, crotch to sole with the platform, take about 56% of the height. [viewer: A Front]
- Two animal ears stand on top of the head. Their tips reach about the height of the hair's top, so they widen the head's outline more than they raise it. [viewer: A Front, B front]
- The hair is a wavy mass that ends at the top of the shoulder blades, with a looped curl standing out on the right side of the head. [viewer: B back, B front]
- A long tail leaves the lower back. Hanging, it reaches the ankles; at its base it is about two-thirds as wide as a thigh. [viewer: B back, B side]
- The tail's pose differs between viewers: it sticks straight out behind in viewer A and hangs in a curve in viewer B. [viewer: A Side, B side]
- The legs are bare from the shorts to mid-calf and end in platform sandals with a high, thin heel. [viewer: B side, B front]
- With the coat on, the outline changes: fur puffs widen both shoulders past the upper arms, and long pointed coat tails fall to mid-calf on both sides of the legs. [viewer: A Front, A Back]
- Without the coat, the outline is narrow and close to the body, broken only by ears, hair, tail and one sleeved arm. [viewer: B front]

Technique: Proportions belong to the mesh. [inferred] The developer describes character models as built from three-view drawings to shared standards for tessellation, topology and textures. [official: S1]

### 2. Head and face construction

Observation:
- The face is a smooth surface with little modelled relief. The nose is a small point with no bridge line or nostrils. [viewer: B side, A Face]
- The lips are slightly raised and painted in a dusky rose that is darker on the upper lip. [viewer: A Face, B front]
- A small pale dot sits on the tip of the nose in both viewers. [viewer: A Face, B front]
- The chin is small and pointed and the jaw has no visible angle. [viewer: A Face, A 3/4 Face]
- The eyes sit low: their centre is about two-thirds of the way down from hair top to chin. [viewer: A Front, A Face]
- Each eye, lash wings included, is about a third of the face width. The gap between the eyes is about three-quarters of one eye-width. [viewer: A Face]
- Eyebrows are short, tapered strokes in a pale khaki close to the hair colour. They stay visible beside the fringe. [viewer: A Face, B front]
- The animal ears are upright and rounded, with a dark outer rim and a pale inner face with jagged tufts and orange patches. Their backs are dark with orange-tan markings and carry a gold triangular plate. [viewer: B front, B back]
- No human ears are visible in any view. [viewer: A Face, B side]
- Whether brows or eyes show through the hair in-game: Not observable. An in-game face close-up would resolve it.
- Face shading: Not observable. In-game face shots lit from the front and from the side would resolve it.

Technique:
- Brows, lash lines, lip colour and the nose dot are painted in the face texture: the dot sits in the same place under both viewers' lighting. [inferred]
- The developer says faces use a dedicated shadow mask that responds to light direction, because standard shading could not give the wanted face. [official: S1] Two recreations describe it as a face shadow texture [breakdown: S3] and a custom face light map. [breakdown: S4]

### 3. Eyes

Observation:
- Upper lash: a thick band in two colours, red-brown on the inner half and dark teal on the outer half, ending in a spiky teal wing. One upward spike rises near the middle of the band. [viewer: A Face, B front]
- Lower lash: a thin teal line with small spikes at the outer corner and a violet tint beneath it. [viewer: A Face, B front]
- A soft brown shadow and a thin crease line sit above the upper lash. [viewer: B front]
- The white of the eye has a grey band under the upper lash. [viewer: A Face, B front]
- Iris: green, darker and bluer at the top, bright yellow-green at the bottom, with a scalloped border between the two tones. The upper lash covers its top. [viewer: A Face, B front]
- Pupil: a narrow vertical slit. [viewer: A Face, B front]
- Each iris has one small white highlight dot at the top centre, in the same place in both eyes and unchanged across three camera angles. [viewer: A Face, A 1/4 Face, A 3/4 Face]
- The eye opening is flat: its height is about 0.35 of the eye's width. [viewer: A Face]
- The iris is about 20 px wide in the largest view, so finer detail is Not observable. An in-game face close-up would resolve it.

Technique: Iris, lashes and highlight are painted in a texture, since the highlight does not move with the viewer's camera. [inferred] Whether the game shades the eyes or adds a moving highlight: Not observable. In-game face close-ups from two angles would resolve it.

### 4. Hair: shape language, clumps, highlight, shadow

Observation:
- A smooth cap covers the skull, parted off-centre, with a short tuft standing up at the parting. [viewer: B front, A Face]
- The fringe is four or five large swept locks. The largest crosses the forehead toward the right eye. [viewer: A Face, B front]
- The sides and back are ten to twelve thick, wavy clumps that end in hooked, pointed tips. [viewer: B back, B front]
- Thin darker lines run along the clumps. There are no individual strands. [viewer: B back]
- Clump edges are crisp, with no fade at the tips. [viewer: B back]
- Two braided strands run round the back of the head and meet at its centre. [viewer: B back, A Back of Head]
- One thin braid in turquoise and pink hangs in front of the right shoulder to the waist, with a gold bead near its end. [viewer: A Front, B side]
- Base colour runs through three stops from root to tip: grey-cream `#CAC3B5`, pale yellow `#DBC285`, then orange `#A86929`. The upper two-thirds are pale; the lower third turns yellow, then orange. [viewer: B front, B back] Viewer A shows the same stops in the same places. [viewer: A Back of Head]
- Small flat marks sit on the hair: a yellow triangle over a pale diamond on the right of the fringe, and a row of five on the back of the head, left of centre. [viewer: B front, B back] Whether they are ornaments or painted highlights is unverified.
- Fur on the ears and tail follows the same shape language: the ear tufts and the tail's tip are a few large jagged points, and the tail's bands have zigzag borders. [viewer: B front, B side]
- Highlight shape, shadow tone and whether the highlight moves with the camera: Not observable. Two in-game hair close-ups from different camera heights, in daylight, would resolve it.

Technique:
- Hair is built from solid clumps, with braids modelled as geometry and strand lines and the colour gradient painted on. [inferred]
- One recreation reports that shine marks painted in the hair textures mask a real-time specular highlight. [breakdown: S4] If the flat marks on her hair are such shine marks, they would be part of that system; this is unverified.

### 5. Skin: tone, shading bands, rim light

Observation:
- Base tone is a warm tan, about `#E1B299` on belly, arm, thigh, shin and back. [viewer: B front, B back] Viewer A agrees on hue and reads brighter, about `#F7C4AA`. [viewer: A Front]
- Skin is the largest single area without the coat: face, shoulders, the whole back, the midriff, the left arm and the legs from shorts to mid-calf. [viewer: B front, B back]
- Marks on the skin: two short strokes at each knee, front and back; a row of five gold diamonds across the left thigh; scattered gold speckles on both thighs. [viewer: B front, B back]
- Nails on hands and feet are dark. The toes are modelled one by one. [viewer: B front]
- Soft darker lines mark the spine and shoulder blades on the bare back. [viewer: B back] Whether they are painted or come from the viewer's lighting is unverified.
- Shading bands and rim light: Not observable. In-game shots in direct sun and in shade would resolve it.

Technique: Knee strokes, thigh diamonds and speckles are painted in the skin texture. [inferred] Shading: unverified. See candidates C9 and C10 in [aesthetics/_candidates.md](../aesthetics/_candidates.md).

### 6. Outlines and inner lines

Observation:
- Outlines: Not observable. Neither viewer draws one. [viewer: A Front, B front] In-game front, side and back shots at two distances would resolve it.
- Lines drawn onto the surface:
  - Creases: two short tapered strokes at each knee, front and back, in a red-brown darker than the skin. [viewer: B front, B back]
  - Hair: darker strand lines along clumps and braids. [viewer: B back]
  - Seams: the fly, waistband and pocket lines of the shorts. [viewer: B front, B back]
  - Weave: grey lines between the bands of the white top. [viewer: B front]
  - Pattern: triangular facets on the black sleeve, and a darker zigzag on the right front of the shorts. [viewer: B front]
  - Face: brows, lashes, crease line and lips, as covered in Axes 2 and 3. [viewer: A Face]
- Flat shapes drawn onto the surface: the thigh diamonds, the speckles, the tail's spots and bands, and the leopard print on the sleeve cuff. [viewer: B front, B back]

Technique: The surface lines and flat shapes are painted into the base-colour texture. [inferred] The outline method is unverified; the two recreations opened for Amber use different methods. [breakdown: S3, S4]

### 7. Clothing: structure, layering, trim, how pieces end

Observation:
- Top: a short white piece built from broad bands wrapped across each other, with dark teal lining at the centre and white straps crossing under it and round the ribs. [viewer: B front, B side]
- Neck: black straps run from the top to a black choker. Between them sits a dark triangular panel that the skin shows through. [viewer: A Face, B front] A white twisted cord hangs below the choker. [viewer: A Face]
- Back: bare from the neck to the shorts except for the white straps. [viewer: B back]
- Shorts: dark teal, high-waisted and short. They have a cut-out with a strap on the right hip, an open panel at the centre back above the tail, a rip on the left front and slashes at the back hem. [viewer: B front, B back]
- Belt: two rows of silver pyramid studs round the waist, crossed at the front by a faceted navy sash and a silver plate set left of centre. [viewer: B front, B side]
- Right arm: a black fingerless sleeve from below the armband to the wrist, with a slit near its top, lacing along the forearm and a flared leopard-print cuff. [viewer: B front, B side]
- Left arm: bare, with bangles at the wrist. [viewer: B front]
- Both upper arms carry a dark band. [viewer: B front]
- Feet: white wraps from mid-calf to ankle under a gold plate at the shin, thin black straps crossing the foot, a studded teal strap over the toes, and a black platform sole with a high, thin heel. [viewer: B front, B side, B back]
- Coat: worn off the shoulders, held at the upper arms and across the upper back. It has black fur puffs at both shoulders, yellow panels with a diamond lattice over the upper arms and upper back, and long open tails to mid-calf. [viewer: A Front, A Back, A Back of Head]
- Coat faces: the inside is orange-brown with chevron bands in orange, yellow, cream and teal near the hem. The outside is dark purple-brown with gold edging and zigzag lines, two long cream tails and red points near the hem. [viewer: A Front, A Back]
- How pieces end: every edge is marked by contrast. The shorts end in a frayed white fringe, the sleeve in a printed cuff, the wraps in gold plates, the coat tails in points with hanging pendants. [viewer: B front, A Front] The fringe and rips are irregular edges, unlike the clean trim bands on Amber.

Technique: Large forms, trims, fringe pieces and pendants are geometry; weave lines and patterns are painted. [inferred] Whether the fringe is solid geometry or flat cut-out pieces is unverified; a close-up would resolve it.

### 8. Detail and ornament

Observation:
- Detail clusters: the head (ears, ear plates, hair ornament, braids), the neck and chest, the wrists and hands, the belt line and shorts, and the shins and feet. [viewer: B front, A Front]
- Plain areas: the bare skin of the midriff, back, left upper arm and upper legs, and the pale upper part of the hair. [viewer: B front, B back]
- Three motifs repeat at different sizes: [viewer: B front, B back, A Front]
  - Pyramid studs: silver on the belt, the neck chain and the ankle crossing; teal on the toe strap and the left back of the shorts; gold spikes on the wrist cuff. [viewer: B front, B back, A Front]
  - Diamonds: gold studs on both armbands, the row on the left thigh, black cut-outs in the shin wraps, a gold column down the back of each calf, the marks on the hair, the coat's lattice and pendants. [viewer: B front, B back, A Front]
  - Zigzag bolts: gold on the belt plate and on a black patch at the right back of the shorts, darker teal on the right front of the shorts, a gold hair ornament at the left ear, a gold piece on the right hand, and the coat's edging. [viewer: B front, B back, B side, A Back]
- Asymmetry: almost every accessory sits on one side only. [viewer: B front, B back]
  - Right: the black sleeve, the hanging braid, the looped curl, the hip cut-out, a thigh strap with a hanging gold bar, the zigzag on the shorts' front, the bolt patch at the back. [viewer: B front, B back, B side]
  - Left: the bangles and, in viewer A, a gold cuff with large spikes; the gold ornament at the ear; the rip in the shorts; the thigh diamonds; the teal studs at the back; the belt plate. [viewer: B front, B back, A Front]
- Head ornaments: a teal triangular plate in a dark frame at the base of each ear, and a dark navy feather-shaped drop under each ear. [viewer: B front]
- Chest: a square gold medallion set on its corner, with a fretted border and a round orange gem carrying a symbol, hung from the choker on a chain of silver pyramid studs. Present in viewer A, absent in viewer B. [viewer: A Face, B front]
- Gems: the orange chest gem, and one teal diamond low on the back of each calf. [viewer: A Face, B back]
- Hands: rings on most fingers. [viewer: B side]
- Tail: orange-tan with ring-shaped brown spots, then alternating dark-brown and cream bands, then a dark tuft. [viewer: B back, B side]
- Coat: gold brackets with orange wedge shapes below the lattice at the back, gold studs along the edges, and gold chevron-and-diamond pendants hanging from the points of the tails. [viewer: A Back Detail, A Front]
- Studs and plates carry three or four flat tones, one per facet. [viewer: B front]

Technique: Studs, plates and pendants are simple faceted geometry with one flat tone per facet. [inferred] Which facets are modelled and which are only painted is unverified; a close-up at a raking angle would resolve it.

### 9. Materials

Observation:
- How cloth, metal, leather, fur, the sheer panel and the gem respond to light: Not observable. In-game close-ups of the belt studs, gold plates, chest gem, fur and neck panel in direct sun, from two camera angles, would resolve it.
- The viewers show only the painting underneath. Silver studs and gold plates are painted in three or four flat tones per piece. The fur is one flat dark grey with a jagged edge. The chest gem is painted with a symbol and a lighter rim. [viewer: B front, A Face, A Front]
- The neck panel is see-through in both viewers. [viewer: A Face, B front] How the game renders it: Not observable.

Technique: Unverified. One recreation describes metal as a matcap combined with a real-time specular term [breakdown: S4]; the other uses a matcap-style gradient lookup driven by the view and light directions. [breakdown: S3]

### 10. Colour

Observation: Base colours were sampled from B front and B back, the more evenly lit viewer. The viewer still lights the model, so values are approximate. [viewer: B front, B back] Coat colours exist only in viewer A and were sampled there. [viewer: A Front]

| Role | Where | Approx. base colour | Saturation, value |
|---|---|---|---|
| Largest area, coat off | Skin | `#E1B299` | 32%, 88% |
| Hair | Root, middle, tip | `#CAC3B5`, `#DBC285`, `#A86929` | 10%, 39%, 76%; 79%, 86%, 66% |
| White | Shin wraps, top, fringe | `#DFE0DC`, `#C4C6C3`, `#C1C8CC` | 2–5%, 78–88% |
| Dark teal | Shorts | `#3B5358` | 33%, 35% |
| Teal accents | Toe straps, ear plates, studs | `#2D6763`, `#296D6C`, `#2E5A56` | 49–62%, 35–43% |
| Turquoise | Braid | `#5EADA1` | 46%, 68% |
| Near-black | Sleeve, choker, platform | `#363431`, `#403D3A`, `#37393C` | 8–9%, 21–25% |
| Navy | Sash | `#414E63` | 34%, 39% |
| Silver | Belt studs | `#7B7D7E` | 2%, 49% |
| Gold | Shin plates, thigh marks | `#AB9873`, `#BFA165` | 33–47%, 67–75% |
| Orange-tan | Sleeve cuff, tail | `#A9773B`, `#A2825A` | 44–65%, 64–66% |
| Tail bands | Cream, dark | `#D8D0C5`, `#5B4E46` | 9%, 85%; 23%, 36% |
| Coat, viewer A | Yellow, lining, teal | `#E6C357`, `#C18236`, `#1D7A66` | 62–76%, 48–90% |
| Coat, viewer A | Fur, dark edge | `#404040`, `#342F2D` | 0–13%, 20–25% |
| Gem, viewer A | Chest gem | `#DE9F28` | 82%, 87% |

- Area with the coat off, front view: skin 35%, whites and pale hair 23%, dark neutrals 12%, gold, tan and brown 11%, teal 9%, yellow and orange hair 8%. Back view: skin 36%, dark neutrals 15%, pale-yellow hair 11%, tail and gold browns 11%, white 10%, teal 8%, orange 7%. [viewer: B front, B back]
- Area with the coat on: Not observable as numbers. The coat adds large yellow, orange-brown and dark panels. [viewer: A Front, A Back] A viewer capture of the full outfit on a plain backdrop would allow a count.
- Saturation: several hues are strongly saturated at once: the orange hair tips, the yellow and orange-brown coat, the teal accents and the orange gem. The skin sits at about 32%. [viewer: B front, A Front]
- Gold metal is a desaturated khaki, the same family as on Amber. The saturated yellow belongs to cloth, not metal. [viewer: B front, A Front]
- Black: there is no pure black. The darkest areas sit at 20–25% value and are close to neutral. [viewer: B front, A Front]
- White: neutral to slightly cool, used for the top, the shin wraps and the fringe. [viewer: B front]
- Viewer A, sampled as a check, agrees on hue: skin `#F7C4AA`, hair root `#DBD7C8`, shorts `#34535A`, sleeve `#3A3633`. [viewer: A Front]
- Iris and braid-pink values were not sampled: Not observable at this size. A close-up would resolve it.
- Lit tone and shadow tone per colour: Not observable. In-game shots of the same pose in direct sun and in shade would resolve it.

Technique: Each material region holds one flat base colour in the texture; the hair gradient is painted. [inferred] One recreation reports that the game sets shadow colours per character with shadow ramps. [breakdown: S4] Unverified on Xilonen.

### 11. Weapon

Observation: Not observable. No view shows a weapon. An in-game shot with the weapon in hand, one with it stowed if it stays visible, and the weapon's name would resolve it.

Technique: Not observable, for the same reason.

### 12. Readability

Observation:
- From shape alone, five things identify her: the animal ears, pale wavy hair that turns orange at the tips, the long tail, long bare legs on platform shoes, and one black sleeved arm. [viewer: B front, B back]
- With the coat on, the fur shoulders and the long pointed tails become the largest shapes, and yellow becomes a main colour. [viewer: A Front, A Back]
- From behind without the coat, the hair gradient and the banded tail carry the identity. [viewer: B back]
- Value steps are smaller than on Amber: skin at about 88% sits between white at 78–88% and dark teal at 35%. Hue does more of the separating. [viewer: B front]
- In motion: Not observable. Three frames of a run cycle would resolve it.
- At a distance: Not observable. An in-game shot with the figure small in frame would resolve it.

Technique: The large blocks are separated by hue and by a few dark anchors: sleeve, shorts and shoes. [inferred]

### 13. Fit with the world

Observation: Not observable. In-game shots in Natlan, her home region [community: S6], by day and with the figure small in frame, would resolve it.

Technique: The developer says characters and scenes are rendered in separate passes, and that characters receive real-time and ambient environment light through a 24-hour cycle. [official: S1]

## Comparison

### With other characters

Compared with [amber.md](amber.md), the only other doc.

Shared:
- Face: smooth, with a small nose point and features painted on. [viewer: A Face]
- Eyes: a thick upper lash band with a wing and one upward spike, an iris darker at the top, a grey band on the white, and painted highlights placed the same way in both eyes. [viewer: A Face]
- Hair: a cap plus thick pointed clumps, painted strand lines, and a painted root-to-tip colour shift. [viewer: B back]
- Painted lines: the same two short strokes at each knee, front and back. Amber has them on boots, Xilonen on bare skin. [viewer: B front, B back]
- Gold metal: a desaturated khaki with flat facets, `#AB9873` here against `#BFAB86` on Amber. [viewer: B front]
- No pure black. [viewer: B front]
- Detail in clusters with plain areas between, and asymmetry from one-sided accessories. [viewer: B front]

Where Xilonen breaks the pattern:
- Build: 7.4 head-heights against 6.9, with shoulders about 1.2 heads wide against 1.0. [viewer: A Front]
- Eyes: flatter and closer together, with slit pupils and lashes in two colours. [viewer: A Face]
- Lips: coloured and slightly raised; Amber has a line only. [viewer: A Face]
- Hair: more clumps, curled, with hooked tips, modelled braids and a three-stop gradient; Amber has straight locks and a slight shift. [viewer: B back]
- Edges: frayed fringe and rips; Amber has clean trim bands only. [viewer: B front]
- Palette: skin is the largest area and several saturated hues sit side by side; Amber has a dark base and one saturated colour. [viewer: B front, A Front]
- Asymmetry: more than a dozen one-sided items against four on Amber. [viewer: B front, B back]
- Body: animal ears and a tail change the outline; Amber has no body feature beyond the human figure. [viewer: B back]

### Game-wide candidates

Supports: C1, C3, C4, C5, C6, C7, C13, C14, C15, C16, C18.

Breaks: C8.

The candidates and their evidence are in [aesthetics/_candidates.md](../aesthetics/_candidates.md).

## Sources

- S1. [Famitsu report (in Japanese) of miHoYo's GDC 2021 talk "'Genshin Impact': Crafting an Anime Style Open World", given by Haoyu Cai](https://www.famitsu.com/news/202107/23228135.html). Covers the character pipeline, separate passes for characters and scenes, the face shadow mask, and real-time and ambient light on characters. A press report of the talk, not the talk itself.
- S2. [miHoYo, Unite Seoul 2020, "From Mobile to Console: Genshin Impact's rendering technology on Console", slides by Zhenzhong Yi](https://image.docswell.com/s/UnityJapan/KWRPQ5-210617-unity-dojo20211mihoyozhenzhongyi). Covers the two rendering pipelines, PC and console against mobile.
- S3. [Adrian Mendez, "Genshin Impact Character Shader Breakdown (Unity URP)"](https://adrianmendez.artstation.com/projects/wJZ4Gg). A recreation in Unity; it does not claim the game uses the same methods.
- S4. [bjayers on ArtStation, "Blender NPR: Recreating the Genshin Impact Shader"](https://bjayers.artstation.com/blog/category/5). A recreation in Blender, mixed with statements about how the game behaves.
- S5. [GenshinBuilds, Xilonen](https://genshin-builds.com/eN/character/xilonen). Names Gold-Draped Gorge as her default and only listed outfit, describes it as a golden coat over short inner garments, and lists her debut in version 5.1.
- S6. [RPG Site, "HoYoVerse teases Xilonen ahead of Genshin Impact 5.1"](https://www.rpgsite.net/news/16411-hoyoverse-teases-xilonen-ahead-genshin-impact-51-in-new-series-trailers). States that she is from Natlan.

Tool documentation is listed under each brief.

## Open questions

1. Is the coat on or off in her standing in-game look? The outfit includes it, and viewer B shows her without it, together with the chest medallion and the spiked cuff. An in-game shot would settle it.
2. Which game version do the viewer models come from?
3. In-game shots that would lift this doc above Shape only. Record game version, platform and graphics preset with each, because PC and console use a different rendering pipeline from mobile. [official: S2]

   | Shot | Fills |
   |---|---|
   | Front, side and back, full body, idle, flat light | Axes 1, 5, 6 |
   | The same from farther away | Axes 6, 12 |
   | Face close-up, lit from the front and from the side | Axes 2, 3 |
   | Hair close-up from two camera heights, in daylight | Axis 4 |
   | Same pose in direct sun and in shade | Axes 5, 10 |
   | Belt studs, gold plates, chest gem, fur and neck panel in sun, from two angles | Axes 8, 9 |
   | Weapon in hand, weapon stowed, and its name | Axis 11 |
   | Figure small in frame in Natlan, by day | Axes 12, 13 |
   | Three frames of a run cycle | Axis 12 |

4. Are the flat marks on her hair ornaments, or painted highlights? A hair close-up from two angles would show whether they move.
5. Are the soft lines on her back painted, or added by viewer B's lighting? An in-game shot of her back in flat light would show it.
