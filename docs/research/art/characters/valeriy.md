# Valeriy (Genshin Impact)

Outfit: Steel and Sash, his default and the only outfit listed for him. [community: S5] The sheet carries no outfit name. The listing describes the outfit as made for both frontline combat and formal command duty, and the views show plate armour on one arm and a diagonal sash across a dress coat. [community: S5] [viewer: A Front] No fuller written description was opened.

Game version or shot date: Viewer sheet provided on 13 November 2026. The game version the viewer model comes from is unverified. The listing gives him as available in version 7.2, phase 1, from 4 November 2026. [community: S5]

Confidence: Shape only. One viewer sheet covers the character and there is no in-game shot. With a single viewer, nothing here could be cross-checked against a second viewer's lighting.

Shots used:
- Viewer sheet A: 16 labelled views (Front, 3/4 Front, 1/4 Front, Side, 3/4 Back, 1/4 Back, Back, Face, 1/4 Face, 3/4 Face, Footwear, Front Detail, 3/4 Front Detail, Back Detail, 3/4 Back Detail, Back of Head). Bind pose, black backdrop, viewer lighting. Tagged `[viewer: A <view>]`.

Links and capture details are in [references/shots.md](../references/shots.md). What the viewer gets right and wrong is in [references/viewers.md](../references/viewers.md).

## Production brief: Blender

Partial: shape only. These rules cover the model and its textures. There are no rules yet for outlines, shading bands, highlights, rim light or how materials respond to light.

1. Block out a tall adult build in an orthographic front view at an estimated eight and a half to nine head-heights, with a small head, low flat hair, and a coat whose hem sits a little below the middle of the figure. (Axis 1)
2. Make the two sides of the upper body different shapes: a layered armour shoulder and arm on one side, a mantle with a half-cape that hangs to the knee on the other. (Axis 1)
3. Model the face as a smooth surface whose only clear relief is a small nose tip, and paint brows, lash bands, crease lines and a short mouth line in the face texture. (Axis 2)
4. Paint each eye in Texture Paint as a narrow, half-lidded opening under a thick lash band that ends in a long pointed wing, with an iris that is dark at the top and has a pale crescent along its lower rim. (Axis 3)
5. Build hair from a smooth cap plus thin pointed locks that lie close to the head, and paint strand lines onto them instead of modelling strands. (Axis 4)
6. Draw lattice lines, line art and panel lines as strokes on the base-colour texture in Texture Paint, and keep them out of the mesh. (Axis 6)
7. Edge every garment piece with piping in one pale metal colour, and end hems and collars in a band of dark fur or feather shapes. (Axis 7)
8. Repeat one small motif, here an elongated rhombus, at many sizes from the chest to the shoes, and build studs, drops and clasps from simple faceted shapes. (Axis 8)
9. Model the body, coat, trousers and boots with a Mirror modifier, then add everything one-sided, such as the armour arm, the half-cape, the sash and a pouch, as separate, unmirrored objects. (Axis 8)
10. Give each material region one flat base colour: a dark blue-green for the coat, near-black for boots, belts and fur, one violet for lining, sash and bands, a pale and greyed gold for all piping, and white and silver for the cape's outside and the armour. (Axis 10)

Sources for this brief:
- Orthographic view: [Blender Manual, Perspective/Orthographic](https://docs.blender.org/manual/en/latest/editors/3dview/navigate/projections.html)
- Texture Paint: [Blender Manual, Texture Paint introduction](https://docs.blender.org/manual/en/latest/sculpt_paint/texture_paint/introduction.html)
- Mirror modifier: [Blender Manual, Mirror Modifier](https://docs.blender.org/manual/en/latest/modeling/modifiers/generate/mirror.html)

## Production brief: Three.js / WebGPU

Partial: shape only. The model and textures are authored elsewhere; these rules cover what the runtime must keep intact. There are no rules yet for shading, outlines or lighting.

1. Check proportions through an `OrthographicCamera`, because the viewer's Front and Side views gave 9.0 and 8.3 head-heights for the same model. (Axis 1)
2. Set `colorSpace = SRGBColorSpace` on every base-colour texture so the flat colours display as authored. (Axis 10)
3. Take lattice lines, line art and panel lines from the base-colour map, and do not generate them with an edge-detection pass. (Axis 6)
4. Keep the iris painting in the eye's base-colour map, and do not add a specular or reflection highlight to the eye material. (Axis 3)
5. Render hair locks and fur shapes as opaque geometry with no alpha fade at the tips. (Axis 4)
6. Render both faces of a hanging cape, with `side = DoubleSide` or with modelled inner faces, because its outside and its lining carry different colours and patterns. (Axis 7)

Sources for this brief:
- Orthographic camera: [three.js docs, OrthographicCamera](https://threejs.org/docs/pages/OrthographicCamera.html)
- Texture colour space: [three.js manual, Color Management](https://threejs.org/manual/pages/color-management.html) and [three.js docs, Texture](https://threejs.org/docs/pages/Texture.html)
- Material sides: [three.js docs, Material](https://threejs.org/docs/pages/Material.html)

## Dissection

Left and right are the character's own. Measurements and colour values are approximate.

### 1. Silhouette and proportions

Observation:
- Height is between 8.3 and 9.0 head-heights from the top of the hair to the soles. The Front view gives about 9.0 (head about 62 px, figure 555 px). [viewer: A Front] The Side view gives about 8.3 (head about 31 px, figure 256 px). [viewer: A Side]
- The head is small in both views, so one pixel on the chin moves the count by 0.15 to 0.3. A larger full-body view would narrow it. [inferred]
- The hair lies flat on the skull and adds little height. [viewer: A Front, A Side]
- Across the armour shoulder and the mantle the upper body is about 2.5 heads wide (158 px); at the belt it is about 1.5 heads (92 px). [viewer: A Front]
- Where the legs part: Not observable. The coat covers it. [viewer: A Front] A view of the body without the outfit would resolve it; none is expected.
- The coat's hem sits about 62% of the way down the figure, the knee guards start at about 68%, and the cape's fur hem reaches about 70%. [viewer: A Front]
- The outline is different on each side. On the left a layered armour shoulder stands up above the shoulder line and the arm is cased in plate. On the right a feather mantle sits on the shoulder and a half-cape hangs from it to the knee. [viewer: A Front, A Back]
- From the side the cape hangs behind the body as one long flat shape, wider at the bottom. [viewer: A Side]
- The coat is fitted at the chest, belted at the waist and flares a little toward its hem. [viewer: A Front]
- The legs are straight and slim, in tall boots that end in heavy shoes. [viewer: A Front, A Footwear]
- Every view shows the bind pose. [viewer: A Front]

Technique: Proportions belong to the mesh. [inferred] The developer describes character models as built from three-view drawings to shared standards for tessellation, topology and textures. [official: S1]

### 2. Head and face construction

Observation:
- The face is a smooth surface with little modelled relief. The nose is a small point with no bridge line or nostrils. [viewer: A Face, A Side]
- The mouth is a short line with barely raised lips and no lip colour. [viewer: A Face]
- The face is long and narrow, with a pointed chin and no visible jaw angle. [viewer: A Face, A 3/4 Face]
- The eye line sits about 59% of the way down from the top of the hair to the chin. [viewer: A Front]
- The eyes are narrow and close together: the gap between them is about 0.8 of an eye-width. [viewer: A Face]
- Eyebrows are thin dark lines that slope down toward the nose. [viewer: A Face]
- Fringe locks fall between and across the eyes. [viewer: A Face]
- The ears are covered by the side locks. [viewer: A Face]
- Whether brows or eyes show through the hair in-game: Not observable. An in-game face close-up would resolve it.
- Face shading: Not observable. In-game face shots lit from the front and from the side would resolve it.

Technique:
- Brows, lash bands, crease lines and the mouth line are painted in the face texture. [inferred]
- The developer says faces use a dedicated shadow mask that responds to light direction, because standard shading could not give the wanted face. [official: S1] Two recreations describe it as a face shadow texture [breakdown: S3] and a custom face light map. [breakdown: S4]

### 3. Eyes

Observation:
- The eye opening is very narrow: its height under the lash is about a fifth of the eye's width, the lowest measured so far. [viewer: A Face]
- Upper lash: a thick black band that ends in a long pointed wing at the outer corner. No upward spike rises from it. [viewer: A Face]
- A thin crease line sits above the lash. [viewer: A Face]
- The white of the eye reads grey. [viewer: A Face]
- Iris: violet, dark at the top, with a pale lilac crescent along its lower rim. [viewer: A Face]
- No separate white highlight can be made out. The pale crescent sits in the same place in both eyes. [viewer: A Face]
- The iris is about 12 px wide in the largest view, so pupil shape and finer detail are Not observable. An in-game face close-up would resolve it.

Technique: Iris and lashes are painted in a texture. [inferred] Whether the game shades the eyes or adds a moving highlight: Not observable. In-game face close-ups from two angles would resolve it.

### 4. Hair: shape language, clumps, highlight, shadow

Observation:
- A smooth cap covers the skull, parted near the centre. [viewer: A Face, A Back of Head]
- The fringe is a row of thin pointed locks that reach the eyes, with a few crossing the bridge of the nose. [viewer: A Face]
- Side locks reach the jaw and end in points. The back is short and tapers at the nape. [viewer: A Face, A Back of Head]
- The locks lie close to the head; none stands up or flicks out far. [viewer: A Front, A Side]
- Thin darker lines run along the locks. There are no individual strands. [viewer: A Face, A Back of Head]
- Clump edges are crisp, with no fade at the tips. [viewer: A Face]
- Base colour is a slate grey, about `#737683`. No root-to-tip gradient can be made out. [viewer: A Front]
- The sheet draws a row of crisp white jagged marks across the fringe at one height. [viewer: A Face] With one viewer this cannot be checked; it is not evidence for the game's highlight.
- Highlight shape, shadow tone and whether the highlight moves with the camera: Not observable. Two in-game hair close-ups from different camera heights, in daylight, would resolve it.

Technique:
- Hair is built from solid clumps, with strand lines painted on. [inferred]
- One recreation reports that shine marks painted in the hair textures mask a real-time specular highlight. [breakdown: S4] The white marks in the sheet would fit such a mask shown as plain colour; this is unverified. See candidate C17 in [aesthetics/_candidates.md](../aesthetics/_candidates.md).

### 5. Skin: tone, shading bands, rim light

Observation:
- Base tone is very pale with a pink cast, about `#ECD5CF`. [viewer: A Front]
- Skin shows only on the face and a short length of neck. A glove covers the right hand and armour the left. [viewer: A Front]
- Skin takes about 1% of the figure's area from the front. [viewer: A Front]
- Shading bands and rim light: Not observable. In-game shots in direct sun and in shade would resolve it.

Technique: Unverified. See candidates C9, C10 and C12 in [aesthetics/_candidates.md](../aesthetics/_candidates.md).

### 6. Outlines and inner lines

Observation:
- Outlines: Not observable. The viewer draws none. [viewer: A Front] In-game front, side and back shots at two distances would resolve it.
- Lines drawn onto the surface:
  - Lattice: a diamond lattice of darker lines over the cape's lining. [viewer: A Front, A 3/4 Front Detail]
  - Line art: pale gold line drawings on the cape's outside. [viewer: A Back, A Back Detail]
  - Panel lines: long curved lines down the front of each boot. [viewer: A Front, A Footwear]
  - Seams: lines down the coat's front panels. [viewer: A Front]
  - Hair: darker strand lines along the locks. [viewer: A Back of Head]
  - Face: brows, lashes, crease line and mouth line, as covered in Axes 2 and 3. [viewer: A Face]
- Flat shapes drawn onto the surface:
  - An angular crest pattern in a lighter tone on the side of the coat's skirt. [viewer: A Side]
  - Pale blue and black rhombi on the cape's outside. [viewer: A Back]
  - Stripes on the sash. [viewer: A Face, A Front Detail]
- Darker fold shapes: Not observable. With one viewer, a painted shape cannot be told from the viewer's own shading. A second viewer's capture would resolve it.
- Knee creases: none visible; guards cover the knees. [viewer: A Front]

Technique: Surface lines and flat shapes: see [Painted lines and fold shapes](../aesthetics/painted-lines-and-fold-shapes.md). The outline method is unverified; the two recreations opened for Amber use different methods. [breakdown: S3, S4]

### 7. Clothing: structure, layering, trim, how pieces end

Observation:
- Collar: a tall standing collar edged in pale gold, over a white ribbed inner collar and a dark undershirt. [viewer: A Face]
- Coat: dark blue-green, double-breasted, fitted at the chest and reaching the lower thigh. Its front edges, seams and hem are piped in pale gold, and the front overlap ends lower on one side than the other. [viewer: A Front, A Face]
- Sash: a lilac band with a yellow and a red stripe runs from the right shoulder to the left hip, fixed with a round silver button. [viewer: A Face, A Front Detail]
- Belt: two black belts set with pale gold rhombus studs. A pouch with a tassel hangs at the left hip. [viewer: A Front, A Front Detail]
- Right arm: a coat sleeve ending in a large turned-back cuff with pale gold bands, and a black glove. [viewer: A Front]
- Left arm: plate armour from shoulder to fingers. The shoulder piece is built from stacked silver plates; the arm is cased in silver segments with black gaps between them. [viewer: A Front, A 3/4 Back Detail]
- Right shoulder: a mantle of dark blue-green feather shapes with a pale gold fringed board. [viewer: A Front, A 3/4 Front Detail]
- Cape: a half-cape hangs from the right shoulder to the knee. Its outside is cream-white with pale gold line art; its lining is lilac with a lattice and pale gold rhombus studs. It has a pale gold border and a band of dark fur along the hem, and a second band of dark fur crosses it at the upper back. [viewer: A Front, A Back, A Back Detail]
- Back: the feather mantle runs across the upper back with a few silver points set in it. A violet band with pale gold bars hangs down the centre of the back to the hem. Pale gold cords loop across the upper back and hang with tassels on the left side. [viewer: A Back, A Back of Head, A Back Detail]
- Trousers: slate grey, visible between the coat's hem and the knee guards. A lilac tab with a pale gold rhombus hangs at the centre front below the coat. [viewer: A Front]
- Knees: a pale gold crown-shaped guard with a silver point on each knee, set on a cuff of dark blue-green feather shapes. [viewer: A Front]
- Boots: near-black and tall, ending in heavy shoes with a pale gold double band at the ankle and silver-white plates at heel and sole. [viewer: A Front, A Footwear]
- How pieces end: every edge is marked by contrast. Coat, collar, cuff, cape and belt pouch are all piped in pale gold; the cape, the mantle and the boot tops end in dark fur or feather shapes. [viewer: A Front, A Back]

Technique: Large forms, armour plates, studs, cords and tassels are geometry. [inferred] Lattice lines and line art: see [Painted lines and fold shapes](../aesthetics/painted-lines-and-fold-shapes.md). Whether the fur and feather bands are solid pointed shapes or flat cut-out pieces is unverified; a close-up would resolve it.

### 8. Detail and ornament

Observation:
- Detail clusters: the collar; the chest, with an ornament on each side and the sash between; the armour arm; the belt and pouch; the cuff of the right sleeve; the knee guards; the shoes; and on the back the mantle, the cords and the patterned lower corner of the cape. [viewer: A Front, A Back]
- Plain areas: the coat between its piping lines, the trousers, the boots, the upper half of the cape's outside, and the hair. [viewer: A Front, A Back]
- One motif repeats at many sizes, the elongated rhombus: in the chest ornaments, as three drops on the left chest, as belt studs, as studs on the cape's lining, on the tab below the coat, in the knee guards, and in pale blue and black on the cape's outside. [viewer: A Face, A Front, A Back]
- Asymmetry: the body, coat, trousers and boots are mirror-symmetric. Almost everything worn over them is one-sided. [viewer: A Front, A Back]
  - Left: the armour shoulder and arm, with a small violet gem on the forearm, which a press piece also places on his left armguard [community: S6]; a lilac panel with three pale gold rhombus drops on the chest; the belt pouch; the cords and tassels on the back. [viewer: A Front, A 3/4 Back, A Back Detail]
  - Right: the feather mantle's fringed board and the half-cape; a large pale gold open-work ornament on the chest with a crimson pleated fan behind it and a chain of silver beads hanging below; two silver-blue pointed clasps on straps at the thigh; the gloved hand. [viewer: A Face, A Front]
  - Across the body: the sash, and the uneven front hem of the coat. [viewer: A Front]
- Gems: small. A violet gem on the left forearm armour and pale blue rhombi on the cape. [viewer: A 3/4 Back, A Back]
- Pale gold pieces carry two or three flat tones, one per facet. [viewer: A Face]

Technique: Plates, studs, drops and clasps are simple faceted geometry with one flat tone per facet. [inferred] Which line art is raised and which is only painted is unverified; a close-up at a raking angle would resolve it.

### 9. Materials

Observation:
- How cloth, plate armour, fur and the sash respond to light: Not observable. In-game close-ups of the armour shoulder, the chest ornament, the cape's fur hem and the sash in direct sun, from two camera angles, would resolve it.
- The sheet shows only the painting underneath, under its own lighting. The armour is painted in a few flat greys per plate, and the pale gold in two or three flat tones per piece. [viewer: A Face, A 3/4 Back Detail]

Technique: Unverified. One recreation describes metal as a matcap combined with a real-time specular term [breakdown: S4]; the other uses a matcap-style gradient lookup driven by the view and light directions. [breakdown: S3] Neither covers fur.

### 10. Colour

Observation: Base colours were sampled from viewer A, the only viewer for this character. On other characters it agrees with the second viewer on hue and is not a reference for brightness, so the values are viewer readings. [viewer: A Front, A Back]

| Role | Where | Approx. base colour | Saturation, value |
|---|---|---|---|
| Base: dark blue-green | Coat at chest, coat near hem, mantle | `#4B5968`, `#2C3B4E`, `#37424F` | 28–44%, 31–41% |
| Base: near-black | Belt, boots, cape fur | `#36393A`, `#38393E`, `#3C3C3E` | 3–10%, 23–24% |
| Slate grey | Hair, trousers | `#737683`, `#4C4E5C` | 12–17%, 36–51% |
| Signature: violet | Cape lining, sash, back band, tab | `#717094`, `#8281A7`, `#7D7DA6`, `#63649F`, `#736FA9` | 22–38%, 58–66% |
| Pale gold | Piping, studs, knee guards, ankle bands | `#B0AE9C`, `#A19C8B`, `#BCB9A4`, `#B9B8A1` | 11–14%, 63–74% |
| Silver | Armour, knee points, sole plates | `#A8AAAC`, `#B1B4B7`, `#ACAFB2`, `#AAB5BB` | 2–9%, 67–73% |
| Cream-white | Cape outside | `#CCC8C7` | 2%, 80% |
| Pale blue | Rhombi on the cape | `#CFD5E5` | 10%, 90% |
| Sash stripe | Yellow | `#F3D196` | 38%, 95% |
| Crimson | Fan behind the chest ornament | `#AA6588` | 41%, 67% |
| Skin | Face | `#ECD5CF` | 12%, 93% |

- Area in bind pose, front view: dark blue-green 30%; near-black 22%; pale gold 11%; violet 10%; silver, white and cream 8%; slate grey 8%; skin 1%; sash stripes under 1%. About 9% could not be assigned, mostly blended edge pixels. Back view: silver, white and cream 28%; near-black 18%; pale gold 16%; dark blue-green 15%; violet 9%; slate grey 5%. [viewer: A Front, A Back]
- Structure: a dark blue-green and near-black base; one violet for lining, sash and bands; pale gold piping on every piece; white and silver on the cape's outside and the armour; two small warm notes in the sash and the chest ornament. [viewer: A Front, A Back]
- Hue: almost everything sits between blue-green and violet, about 200–245°. The pale gold, at about 50°, and the sash's yellow and red are the only warm colours. [viewer: A Front]
- Saturation: low throughout. The coat sits at 28–44%, the violet at 22–38%, the gold at 11–14%. [viewer: A Front]
- Gold is paler and greyer than on any of the other six characters. [viewer: A Front]
- Front and back differ: from the front the figure is dark with a violet lining; from behind the cream-white cape is the largest area. [viewer: A Front, A Back]
- Black: no sample is pure black. The darkest areas read 23–24% in this viewer. [viewer: A Front]
- The sash's red stripe and the iris were not sampled: Not observable at this size. A close-up would resolve it.
- Lit tone and shadow tone per colour: Not observable. In-game shots of the same pose in direct sun and in shade would resolve it.

Technique: Each material region holds one flat base colour in the texture. [inferred] One recreation reports that the game sets shadow colours per character with shadow ramps. [breakdown: S4] Unverified on Valeriy.

### 11. Weapon

Observation: Not observable. No view shows a weapon. His weapon type is listed as sword. [community: S5] An in-game shot with the weapon in hand, one with it stowed if it stays visible, and the weapon's name would resolve it.

Technique: Not observable, for the same reason.

### 12. Readability

Observation:
- From shape alone, five things identify him: a small head with flat grey hair; one silver armour arm with a raised shoulder; a half-cape with a fur hem on the other side; a diagonal sash across a dark, gold-piped coat; and pale guards on the knees of dark boots. [viewer: A Front, A Back]
- The two sides never match, so the figure reads differently from the left, the right, the front and the back. From behind, the cream-white cape and the violet band are the largest shapes. [viewer: A Front, A Back, A Side]
- Pale gold piping draws the edges of every piece against the dark base. [viewer: A Front]
- Value steps: cape outside at about 80%, armour at about 70%, violet at about 60%, coat at 31–41%, boots at about 24%. [viewer: A Front, A Back]
- In motion: Not observable. Three frames of a run cycle would resolve it.
- At a distance: Not observable. An in-game shot with the figure small in frame would resolve it.

Technique: Light, cool shapes are placed off-centre on a dark base, and thin pale lines separate the dark pieces from each other. [inferred]

### 13. Fit with the world

Observation: Not observable. In-game shots in Snezhnaya, the nation he is reported to serve [community: S6], with the figure small in frame, would resolve it.

Technique: The developer says characters and scenes are rendered in separate passes, and that characters receive real-time and ambient environment light through a 24-hour cycle. [official: S1]

## Comparison

### With other characters

Compared with [zhongli.md](zhongli.md), [wriothesley.md](wriothesley.md) and [clorinde.md](clorinde.md).

Shared:
- Face: smooth, with a small nose point and features painted on. [viewer: A Face]
- Eyes: a thick upper lash band and an iris darker at the top. [viewer: A Face]
- Hair: a cap plus solid pointed locks with painted strand lines and crisp tips. [viewer: A Back of Head]
- Painted lines and patterns on the surface. [viewer: A Front, A Back]
- Gold as a pale, desaturated tone with flat facets. [viewer: A Face]
- Detail in clusters with plain areas between. [viewer: A Front]
- Every garment edge marked by contrast. [viewer: A Front, A Back]
- With Zhongli and Wriothesley: a long face, no lip colour, no upward lash spike, no separate eye highlight at this size, and a build well above seven head-heights. [viewer: A Face, A Front]
- With Clorinde: a cool palette inside one hue band, shoulder boards with fringe, cords with tassels, and a long piece of cloth hanging on one side. [viewer: A Front, A Back]
- With Wriothesley: front and back that read differently, and fur built from large pointed shapes. [viewer: A Front, A Back]

Where Valeriy breaks the pattern:
- Asymmetry: the strongest so far. One arm is armour and the other shoulder carries a cape, so the outline itself is one-sided, not just the accessories. [viewer: A Front]
- Hair: flat and close to the head, with thin locks; the others have locks that stand out or hang free. [viewer: A Front, A Side]
- Eyes: the narrowest opening measured so far, with thin brows where the other two men have thick ones. [viewer: A Face]
- Gold: about 11% of the front view and 16% of the back, used as piping on every piece, where the others keep it to ornament. [viewer: A Front, A Back]
- Plate armour: a hard-surface piece larger than any on the other six. [viewer: A Front]
- Build: the highest head count so far, 8.3 to 9.0, helped by flat hair. [viewer: A Front, A Side]

### Game-wide candidates

Supports: C1, C3, C6, C7, C13, C14, C16.

Supports in part: C5, C8, C15.

Breaks: C18, on head-heights.

The candidates and their evidence are in [aesthetics/_candidates.md](../aesthetics/_candidates.md).

## Sources

- S1. [Famitsu report (in Japanese) of miHoYo's GDC 2021 talk "'Genshin Impact': Crafting an Anime Style Open World", given by Haoyu Cai](https://www.famitsu.com/news/202107/23228135.html). Covers the character pipeline, separate passes for characters and scenes, the face shadow mask, and real-time and ambient light on characters. A press report of the talk, not the talk itself.
- S2. [miHoYo, Unite Seoul 2020, "From Mobile to Console: Genshin Impact's rendering technology on Console", slides by Zhenzhong Yi](https://image.docswell.com/s/UnityJapan/KWRPQ5-210617-unity-dojo20211mihoyozhenzhongyi). Covers the two rendering pipelines, PC and console against mobile.
- S3. [Adrian Mendez, "Genshin Impact Character Shader Breakdown (Unity URP)"](https://adrianmendez.artstation.com/projects/wJZ4Gg). A recreation in Unity; it does not claim the game uses the same methods.
- S4. [bjayers on ArtStation, "Blender NPR: Recreating the Genshin Impact Shader"](https://bjayers.artstation.com/blog/category/5). A recreation in Blender, mixed with statements about how the game behaves.
- S5. [GenshinBuilds, Valeriy](https://genshin-builds.com/en/character/valeriy). Names Steel and Sash as his default and only listed outfit, describes its purpose, lists his weapon type as sword, and gives him as available in version 7.2, phase 1.
- S6. [AllThings.How, "Valeriy in Genshin Impact 7.2: Electro Element, Role, and Release Window"](https://allthings.how/valeriy-in-genshin-impact-7-2-electro-element-role-and-release-window/). Describes him as an officer of Snezhnaya and places a gem on his left armguard. Written before his release.

Tool documentation is listed under each brief.

## Open questions

1. Which game version does the viewer model come from?
2. How many head-heights is he? The Front and Side views give 9.0 and 8.3. A larger full-body view, or a capture from the second viewer, would narrow it.
3. A second viewer's captures (front, side, back) would allow the cross-checks this doc lacks: base colours under more even light, painted fold shapes, and the hair marks.
4. In-game shots that would lift this doc above Shape only. Record game version, platform and graphics preset with each, because PC and console use a different rendering pipeline from mobile. [official: S2]

   | Shot | Fills |
   |---|---|
   | Front, side and back, full body, idle, flat light | Axes 1, 5, 6 |
   | The same from farther away | Axes 6, 12 |
   | Face close-up, lit from the front and from the side | Axes 2, 3 |
   | Hair close-up from two camera heights, in daylight | Axis 4 |
   | Same pose in direct sun and in shade | Axes 5, 10 |
   | Armour shoulder, chest ornament, cape's fur hem and sash in sun, from two angles | Axes 8, 9 |
   | Weapon in hand, weapon stowed, and its name | Axis 11 |
   | Figure small in frame in Snezhnaya | Axes 12, 13 |
   | Three frames of a run cycle | Axis 12 |

5. Are the fur and feather bands solid shapes or flat cut-out pieces?
