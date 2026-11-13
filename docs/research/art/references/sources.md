# Sources

Every link the art research relies on, one row each. Never list a page that was not opened.

- Type: official, breakdown or community, matching the evidence tags in the docs.
- Type `tool docs`: a manual or API page for a production tool. Used only in a brief's own source list.

| Source | Type | Used for | Cited in |
|---|---|---|---|
| [Famitsu report of miHoYo's GDC 2021 talk "'Genshin Impact': Crafting an Anime Style Open World"](https://www.famitsu.com/news/202107/23228135.html) | official | Character pipeline; separate render passes for characters and scenes; face shadow mask; real-time and ambient light on characters. A press report of the developer's talk, in Japanese | characters/amber.md |
| [Unite Seoul 2020 slides, "From Mobile to Console: Genshin Impact's rendering technology on Console"](https://image.docswell.com/s/UnityJapan/KWRPQ5-210617-unity-dojo20211mihoyozhenzhongyi) | official | Two rendering pipelines (PC and console; mobile); capsule ambient occlusion for characters. Silent on toon shading and outlines | characters/amber.md |
| [Adrian Mendez, "Genshin Impact Character Shader Breakdown (Unity URP)"](https://adrianmendez.artstation.com/projects/wJZ4Gg) | breakdown | Recreation: light and shadow split, face shadow texture, hair highlight, metal, screen-space outline, edge highlight | characters/amber.md |
| [bjayers, "Blender NPR: Recreating the Genshin Impact Shader"](https://bjayers.artstation.com/blog/category/5) | breakdown | Recreation plus statements about the game: painted shadows in textures, shadow ramps, face light map, hair shine masks, metal, inverted-hull outline, rim light | characters/amber.md |
| [Game8, "How to Get the 5-Star Outrider Outfit"](https://game8.co/games/Genshin-Impact/archives/355423) | community | Name of Amber's default outfit | characters/amber.md |
| [Screen Rant, alternate outfits for Jean, Mona, Rosaria and Amber](https://screenrant.com/genshin-impact-alternate-outfits-jean-mona-rosaria-amber/) | community | What changed between Amber's original outfit and 100% Outrider | characters/amber.md |
| [Blender Manual, Perspective/Orthographic](https://docs.blender.org/manual/en/latest/editors/3dview/navigate/projections.html) | tool docs | Orthographic view for judging proportions | characters/amber.md, Blender brief |
| [Blender Manual, Texture Paint introduction](https://docs.blender.org/manual/en/latest/sculpt_paint/texture_paint/introduction.html) | tool docs | Painting lines and eyes onto the base-colour texture | characters/amber.md, Blender brief |
| [Blender Manual, Mirror Modifier](https://docs.blender.org/manual/en/latest/modeling/modifiers/generate/mirror.html) | tool docs | Symmetric modelling before adding one-sided accessories | characters/amber.md, Blender brief |
| [three.js docs, OrthographicCamera](https://threejs.org/docs/pages/OrthographicCamera.html) | tool docs | Orthographic camera for proportion checks | characters/amber.md, Three.js brief |
| [three.js manual, Color Management](https://threejs.org/manual/pages/color-management.html) | tool docs | sRGB annotation of colour textures | characters/amber.md, Three.js brief |
| [three.js docs, Texture](https://threejs.org/docs/pages/Texture.html) | tool docs | The `colorSpace` property and its default | characters/amber.md, Three.js brief |
