# Painted lines and fold shapes (Genshin Impact)

Status: Established. The finding is on the shape side: lines and darker shapes sit in the same place under two viewers' lighting on four characters. Only one character's lines have been seen in-game so far.

Checked on: Amber, Xilonen, Clorinde, Navia.

Candidates taken in: C1, C2.

This doc covers lines and darker shapes on cloth, skin, boots and gloves. Lines on the face and in the hair, outlines, and shading are other topics.

## Production brief: Blender

1. Paint seams, stitches, creases, pleats and trim edges as thin strokes on the base-colour texture in Texture Paint, and keep them out of the mesh.
2. Draw each line darker than the surface it sits on, and switch to a lighter line only where the surface itself is dark.
3. Mark a bare knee, or a knee in a plain light boot, with two short tapered strokes at the front and two at the back.
4. Paint cloth patterns, embroidery, emblems and marks on the skin as flat shapes on the same texture.
5. Paint folds as a few shapes in one darker tone of the base colour, placed beside fastenings, under overhangs such as a hood or a bust, and along ruffles.
6. Model only the large forms and the main trims, and leave every smaller line and fold to the texture.

Sources for this brief:
- Texture Paint: [Blender Manual, Texture Paint introduction](https://docs.blender.org/manual/en/latest/sculpt_paint/texture_paint/introduction.html)

## Production brief: Three.js / WebGPU

1. Take seams, stitches, creases, pleats and fold shapes from the base-colour map, and add no line or fold of your own in the shader.
2. Set `colorSpace = SRGBColorSpace` on the base-colour texture so the painted tones display as authored.
3. Do not generate inner lines with an edge-detection pass; the seams and creases are already in the map.
4. Do not add decals or extra meshes for cloth patterns, emblems drawn on cloth or marks on the skin; they belong to the same map.
5. Where a painted pattern has to show on both faces of a thin piece of cloth, render that material with `side = DoubleSide` or give the cloth two modelled faces.

Sources for this brief:
- Texture colour space: [three.js manual, Color Management](https://threejs.org/manual/pages/color-management.html) and [three.js docs, Texture](https://threejs.org/docs/pages/Texture.html)
- Material sides: [three.js docs, Material](https://threejs.org/docs/pages/Material.html)

## What holds

Finding: Small lines are not modelled. Seams, stitches, creases, pleats, trim edges and cloth patterns are drawn as thin strokes and flat shapes on the surface, and they stay in place when the viewer's light changes. [doc: amber, axis 6] [doc: xilonen, axis 6] [doc: clorinde, axis 6] [doc: navia, axis 6] On three of the four characters the surface also carries a few darker shapes at folds and overhangs that stay in place in the same way. [doc: amber, axes 7 and 10] [doc: clorinde, axis 6] [doc: navia, axis 6]

Per character:
- Amber: dashed stitches along the sleeves, round the armhole and on the corset seams; seam and edge lines on hood, shorts, pockets and belt; two short tapered strokes at each knee, front and back, on the white boots; a thin dark line beside most gold trim. [doc: amber, axis 6] Darker fold shapes sit on the sleeves and the hood and under the bust. [doc: amber, axes 7 and 10] The knee creases and the corset seam lines stay visible in-game. [shot: ingame-front] [doc: amber, axis 6]
- Xilonen: the same two strokes at each knee, front and back, on bare skin; seam lines on the shorts; weave lines on the white top; printed facets, a zigzag and leopard spots; diamonds and speckles on the skin of the thighs. [doc: xilonen, axis 6] No fold shapes can be made out at the size of her views; this is recorded under C2 in [_candidates.md](_candidates.md). [viewer: Xilonen B front]
- Clorinde: seams on blouse, sleeves, corset and gloves; pleat stripes on a panel at the back of the waist; a scroll pattern on the short cape, scrollwork on both faces of the banner, an emblem on the jabot. [doc: clorinde, axis 6] Small fold shapes sit beside the blouse buttons and one fold line on each boot cuff. [doc: clorinde, axis 6]
- Navia: a lacing pattern down the front of each boot; pleat lines on the chest panel and the front skirt; lace, embroidery scrolls and a cream motif on the skirt. [doc: navia, axis 6] Rows of rounded ruffle shapes in a darker yellow run along the skirt tails. [doc: navia, axis 6]

Range:
- Kinds of line: seams on all four; knee strokes on two; pleat lines on two; stitches drawn as dashes, weave lines, trim-edge lines and lacing on one each. [doc: amber, axis 6] [doc: xilonen, axis 6] [doc: clorinde, axis 6] [doc: navia, axis 6]
- Tone of the lines: darker than the surface in most cases. Xilonen's knee strokes are a red-brown darker than the skin. [doc: xilonen, axis 6] On dark cloth the line turns lighter: cream dashes on Amber's dark corset and a lighter line inside the hem of her shorts. [doc: amber, axis 6]
- Knee strokes: present where the knee is bare or in a plain white boot; none visible on Clorinde's tights or on Navia's dark, patterned boots. [doc: amber, axis 6] [doc: xilonen, axis 6] [doc: clorinde, axis 6] [doc: navia, axis 6]
- Flat shapes: three characters have patterns or body marks drawn on the surface, from printed facets and skin marks on Xilonen to lace, scrolls and tiers of pattern on Navia. [doc: xilonen, axis 6] [doc: clorinde, axis 6] [doc: navia, axis 6] On Amber it is unverified which emblems are flat and which are raised. [doc: amber, axis 8]
- Fold shapes are few and sit where cloth gathers or overhangs: sleeves, hood and under the bust on Amber; beside buttons and on a folded cuff on Clorinde; along ruffles and under skirt tiers on Navia. [doc: amber, axis 7] [doc: clorinde, axis 6] [doc: navia, axes 6 and 10]
- Tone of the fold shapes, as viewer readings only: red `#A63F3F` with `#953C3C` and white `#EAE6E4` with `#CAC5C1` on Amber; yellow `#EFBC69` with `#CD9A4B` on Navia. [doc: amber, axis 10] [doc: navia, axis 10] Each pair keeps the hue and drops in value. Neither viewer is a reference for brightness, as recorded in [references/viewers.md](../references/viewers.md), so the numbers are not targets.

Exceptions:
- None of the four breaks the finding on lines.
- Fold shapes: Xilonen is not observable, not a break. Her views are too small to show any. [viewer: Xilonen B front]
- A darker shape was counted only when it shows in the same place under both viewers' lighting, because both viewers add shading of their own, as recorded in [references/viewers.md](../references/viewers.md). Soft lines on Xilonen's bare back show in one viewer only, are unverified, and are left out. [doc: xilonen, axis 5]

## How it is made

The developer says: nothing was found on painted lines or painted shadows in the two official sources opened. One says only that character models are built to shared standards for tessellation, topology and textures. [official: S1]

Recreations do:
- One recreation states that hand-painted shadows are baked into the character textures at seams, at folds, under the arms and under the neck. [breakdown: S4] That matches where the fold shapes were found.
- On lines, what was taken from the two recreations concerns outlines only: one builds a slightly larger back-facing shell [breakdown: S4], the other finds edges in screen space from depth and normals. [breakdown: S3] Whether either also discusses painted seam lines was not recorded when they were read.
- That the lines are painted into the base-colour texture is our own inference from the viewers: the lines do not move with the light and follow the surface across both viewers. [inferred]

Disagreements: none on this topic. The two recreations disagree on how outlines are made [breakdown: S3, S4], which decides whether the game could also add inner lines of its own on top of the painted ones. That belongs to the outlines topic. Close-ups of a seam in-game at two distances would show whether its width stays fixed to the surface or to the screen.

## Sources

- S1. [Famitsu report (in Japanese) of miHoYo's GDC 2021 talk "'Genshin Impact': Crafting an Anime Style Open World", given by Haoyu Cai](https://www.famitsu.com/news/202107/23228135.html). A press report of the talk. Silent on painted lines and painted shadows.
- S2. [miHoYo, Unite Seoul 2020, "From Mobile to Console: Genshin Impact's rendering technology on Console", slides by Zhenzhong Yi](https://image.docswell.com/s/UnityJapan/KWRPQ5-210617-unity-dojo20211mihoyozhenzhongyi). Opened for this topic and silent on it.
- S3. [Adrian Mendez, "Genshin Impact Character Shader Breakdown (Unity URP)"](https://adrianmendez.artstation.com/projects/wJZ4Gg). A recreation in Unity; screen-space outline from depth and normals.
- S4. [bjayers on ArtStation, "Blender NPR: Recreating the Genshin Impact Shader"](https://bjayers.artstation.com/blog/category/5). A recreation in Blender, mixed with statements about how the game behaves; painted shadows in the textures, inverted-hull outline.
- Character docs: [amber.md](../characters/amber.md), [xilonen.md](../characters/xilonen.md), [clorinde.md](../characters/clorinde.md), [navia.md](../characters/navia.md).
- Viewer limits: [references/viewers.md](../references/viewers.md).

Tool documentation is listed under each brief.

## Open questions

1. Do the painted lines and fold shapes show in-game on the other three characters? Only Amber's knee creases and corset seams have been seen in an in-game shot. Full-body in-game shots in flat light would settle it.
2. How do the painted fold shapes behave in shade: do they stay visible under the game's shadow tone, or merge with it? This waits for the shading topic and for in-game shots of one pose in sun and in shade.
3. Which patterns and emblems are painted, and which are raised geometry? A close-up at a raking angle would show it.
4. Does the game draw any inner line of its own on top of the painted ones? This waits for the outlines topic.
5. Do the two recreations say anything about painted seam lines? Re-reading them for this point would settle it.
6. No male character is covered yet.
