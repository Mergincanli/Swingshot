# Viewers

Model viewers used for viewer sheets, and how each differs from the game. Read this before using a viewer sheet. Update it whenever a sheet is checked against an in-game shot.

One `## Viewer name` section per viewer, with these fields:

- Link:
- Views it gives:
- Reliable for:
- Not reliable for:
- Measurements: whether proportions can be measured from it, and why
- Checked against: which in-game shots, in which doc

## phoshco model-viewer

Called viewer A in the character docs. Lines that start with a character's name use the view names of that character's doc; all other tags use those of [characters/amber.md](../characters/amber.md).

- Link: https://phoshco.github.io/model-viewer/amber (Amber's page). No URL is recorded for other characters' pages.
- Views it gives: one sheet of 16 labelled views in bind pose on a red backdrop: Front, 3/4 Front, 1/4 Front, Side, 3/4 Back, 1/4 Back, Back, Face, 1/4 Face, 3/4 Face, Footwear, Front Detail, 3/4 Front Detail, Back Detail, 3/4 Back Detail, Back of Head. [viewer: A Front]
  - Xilonen: the same 16 views on an amber backdrop. The fixed cameras do not adapt to the character: the Footwear view shows no feet, and the four Detail views frame the upper arm, hip and coat. [viewer: A Footwear, A Front Detail]
  - Clorinde: the same 16 views on a violet backdrop. The Footwear view frames the boots and the Detail views the head and upper body. [viewer: A Footwear, A Front Detail]
  - Navia: the same 16 views on an amber backdrop. The Footwear view frames the boots and the Detail views the head, shoulders and hips. The backdrop is close in colour to her yellow skirt, so the skirt's outline is hard to read in the Front view. [viewer: A Footwear, A Front Detail, A Front]
  - Zhongli: the same 16 views on a black backdrop. Near-black parts, such as the gloves and the lapels, are hard to tell from the backdrop. [viewer: A Front]
  - Wriothesley: the same 16 views on a black backdrop. His black arm wraps and gloves are hard to tell from it. [viewer: A Front]
- Reliable for:
  - Outfit construction, ornament placement, asymmetry, painted lines and hair clump layout. All of these matched the back view in-game. [viewer: A Back] [shot: ingame-back] They also matched the front view. [viewer: A Front] [shot: ingame-front]
  - Face and eye construction. Its Face view is the largest face in either viewer, with the iris about 35 px wide. [viewer: A Face]
  - Xilonen: completeness of the outfit. It shows the coat, chest medallion and spiked wrist cuff that the other viewer's captures lack, and the coat is part of her default outfit. [viewer: A Front] [community: [GenshinBuilds](https://genshin-builds.com/eN/character/xilonen)]
- Not reliable for:
  - Pose. It shows the bind pose only. Against the idle pose in-game, that widens the outline of sleeves and hair. [viewer: A Front] [shot: ingame-front]
  - Xilonen: the tail sticks straight out behind, where the other viewer shows it hanging. Which of the two is the model's rest pose is unverified. [viewer: A Side, B side]
  - Outline. It draws none. [viewer: A Front]
  - Shading. It adds soft gradients of its own: on the face, as a pale band across the back of the hair, and as a cool lilac tone, about `#D0CED8`, on one side of the white boots. [viewer: A Face, A Back of Head, A Front] In-game, both boots sample at one flat value across their width. [shot: ingame-front]
  - Colour values. It agrees with the Games Fashion Archive viewer on hue but reads darker. [viewer: A Front, B front] The in-game colours are darker and more saturated than both viewers. [shot: ingame-front]
  - Xilonen: the brightness relation flipped. Here it reads brighter than the other viewer, skin `#F7C4AA` against `#E1B299`, while the hues still agree. Neither viewer is a reference for brightness. [viewer: A Front, B front]
  - Clorinde: no clear offset. Its values sit within a few percent of the other viewer's: hair `#444869` against `#464A60`, hat crown `#494B93` against `#514F90`, skirt `#3C3C4B` against `#40414D`, gold `#80705C` against `#837464`. [viewer: A Front, B front]
  - Navia: no clear offset either: skin `#E8DDD3` against `#E7DBD0`, hat `#3D3D44` against `#343337`, boots `#423D39` against `#443F39`, lit hair `#E8CC9E` against `#E9D2A5`. [viewer: A Front, B front]
  - Zhongli: hues agree. Near-black reads darker here: lapels `#151314` against `#282727`. Other samples sit close: hair `#544B48` against `#4C4643`, trousers `#423A41` against `#3B363B`, forearm `#784C2F` against `#6F4A34`. [viewer: A Front, B front]
  - Wriothesley: hues agree, and the red reads more saturated here: lining `#5D2E3D` against `#4D3037`, tie `#712F3E` against `#6C3842`. Greys sit close: waistcoat `#686672` against `#67636E`, trousers `#878894` against `#7F7F8A`. [viewer: A Front, B front]
  - Hair highlight. A viewer is not evidence for highlights, and the two viewers disagree on them.
    - Clorinde: it draws a row of crisp white jagged marks round the crown of the hair and a few low on the tail; the other viewer draws none there. Both viewers show a thin pale broken line on one front strand. [viewer: A Back of Head, A Back Detail, A 3/4 Face, B back, B front] Which viewer is closer to the game is unverified.
    - Navia: both viewers show lighter marks on the fringe and the ringlets, in the same places. This sheet draws them white with jagged ends; the other viewer draws them as a paler blonde with softer edges. [viewer: A Face, A Back Detail, B front, B back]
    - Zhongli: it draws crisp white jagged marks in a ring round the crown; the other viewer draws none. [viewer: A Face, A Back of Head, B front, B back]
    - Wriothesley: it draws one crisp white jagged mark on the fringe; the other viewer draws none. [viewer: A Face, B front]
  - Sheer legwear. Clorinde: both viewers render the tights lighter along the middle of each leg and darker toward its outline in every view, so the tone follows the camera, not the surface. [viewer: A Front, A Side, B front, B back] Whether the game does the same is unverified.
  - Surfaces turned away from the light. Navia: the inner face of the skirt tails reads as a yellow that fades to cream here and as a dull khaki, about `#937753`, in the other viewer. Both are viewer shading. [viewer: A Front, B front]
  - Linings. Zhongli: it shows the inside of the coat's skirt as golden yellow, about `#C5A14F`; the other viewer shows no yellow in any capture. [viewer: A Front, A 3/4 Back, B front, B side] Which viewer is right is unverified; an in-game shot from behind at three-quarter angle would settle it.
- Measurements: Yes, as approximate values. Its Front view gave 6.9 head-heights for Amber. [viewer: A Front] The in-game still gives at least 6.3 head-heights down to the ankle, with the feet hidden, which does not contradict it. [shot: ingame-front] Its camera is not orthographic; see Navia's line below.
  - Xilonen: 7.4 head-heights including platform shoes. [viewer: A Front]
  - Clorinde: about 7.0 head-heights, between 6.7 and 7.3, measured in the Side view because the hat hides the top of the head from the front. [viewer: A Side] The Front view is drawn about 2.27 times larger than the Side view (chin to sole 573 px against 252 px), not the 2.12 that the panel sizes suggest, so a length cannot be carried from one panel to another by panel size. [viewer: A Front, A Side]
  - Navia: the hat hides the top of the head in every view, so head-heights cannot be measured, only estimated at about 7.3, between 6.9 and 8.1. Lengths below the chin measure normally. The Front view is drawn about 2.31 times larger than the Side view (chin to sole 589 px against 254.5 px). [viewer: A Front, A Side]
  - Navia: the camera has perspective; it is not orthographic. The tips of her skirt tails, which stand well behind the body, sit 76% of the way down the figure in the Front view, 82% in the Side view and 91% in the Back view. [viewer: A Front, A Side, A Back] Parts in the body's own plane can be compared between views; parts that stand in front of or behind it read smaller and higher when they are farther from the camera, and larger and lower when they are nearer. Her hair measures 2.4 heads wide in the Front view and 2.7 in the Back view, her skirt tails 2.7 and 3.3. [viewer: A Front, A Back]
  - Zhongli: about 8.4 head-heights, between 8.2 and 8.6. His head is about 76 px tall in the Front view, so 2 px on the chin moves the count by 0.2; on small heads the count is coarse. [viewer: A Front]
  - Wriothesley: about 7.7 head-heights, between 7.5 and 7.9. Tall hair and thick soles both enter the count. [viewer: A Front]
- Checked against: `ingame-front` and `ingame-back`, YouTube playthrough footage captured by Mustafa, in [characters/amber.md](../characters/amber.md). No other character has an in-game shot yet, so their lines compare the two viewers with each other only.

## Games Fashion Archive viewer

Called viewer B in the character docs. Lines that start with a character's name use the view names of that character's doc; all other tags use those of [characters/amber.md](../characters/amber.md).

- Link: https://gamesfashionarchive.net/viewer/2058/2 (the page behind Amber's full-figure captures). No URL is recorded for her outfit-only captures or for other characters' pages.
- Views it gives: free captures in bind pose on a white backdrop. The page offers a turntable and a capture tool. [community: the linked page] For Amber it gave the full figure from front and back, and the clothing alone on a blank mannequin from front and back. [viewer: B front, B back, B outfit front, B outfit back]
  - Xilonen: full figure from front, side and back. [viewer: B front, B side, B back]
  - Clorinde: full figure from front, side and back, and the clothing alone from the front. [viewer: B front, B side, B back, B outfit front]
  - Navia: full figure from front, side and back. [viewer: B front, B side, B back]
  - Zhongli: full figure from front, side and back, on a pale grey backdrop. [viewer: B front, B side, B back]
  - Wriothesley: full figure from front, side and back, on a pale grey backdrop. The captures include a floor shadow, which has to be left out when areas are counted. [viewer: B front, B back]
- Reliable for:
  - Outfit construction, ornament placement, asymmetry, painted lines and hair clump layout. All of these matched the back view in-game. [viewer: B back] [shot: ingame-back] They also matched the front view. [viewer: B front] [shot: ingame-front]
  - Clothing detail. The outfit-only captures are the largest view of trims, stitches and emblems in either viewer. [viewer: B outfit front, B outfit back]
  - Approximate base colours. It is the more evenly lit of the two viewers, so Amber's base colours were sampled from it. It still lights the model, and skin samples sit at full brightness, so highlights may be clipped. [viewer: B front, B back]
  - Xilonen: what an outer layer hides. Its coat-off captures show the back and the inner garments that the coat covers in the phoshco sheet. [viewer: B back, A Back]
  - Clorinde: clothing detail. The outfit front capture is the largest view of the collar, brooch, corset and skirt ornaments. [viewer: B outfit front]
  - Navia: the back of the outfit and the hat. Its back capture is the largest view of the skirt's tiers, and its side capture of the hat trim and the right forearm. [viewer: B back, B side]
- Not reliable for:
  - Proportions. See Measurements.
  - Xilonen: completeness of the outfit. Its captures lack the coat, the chest medallion and the spiked wrist cuff that the phoshco sheet shows. Whether that is a state of the model or a choice made in the viewer is unverified. [viewer: B front, A Front]
  - Pose. It shows the bind pose only. Against the idle pose in-game, that widens the outline of sleeves and hair. [viewer: B front] [shot: ingame-front]
  - Xilonen: the arms stay in bind pose while the tail hangs in a curve. [viewer: B front, B side]
  - Clorinde: completeness of the outfit front capture. It leaves out the hat, the long drape, the banner and the boots, and shows the arms lowered where the full-figure captures show the bind pose. [viewer: B outfit front, B front]
  - Linings. Zhongli: its captures show no yellow inside the coat's skirt, where the phoshco sheet shows golden yellow. [viewer: B front, B side, A Front] Which viewer is right is unverified.
  - Hair highlight. A viewer is not evidence for highlights, and the two viewers disagree on them.
    - Clorinde: it draws no marks on the crown or the tail, where the phoshco sheet draws white ones. [viewer: B back, B side, A Back of Head]
    - Navia: it draws lighter marks on the fringe and the ringlets as a paler blonde with softer edges, where the phoshco sheet draws them white with jagged ends. [viewer: B front, B back, A Face, A Back Detail]
    - Zhongli: it draws no marks on the crown, where the phoshco sheet draws a ring of white ones. [viewer: B front, B back, A Back of Head]
    - Wriothesley: it draws no mark on the fringe, where the phoshco sheet draws a white one. [viewer: B front, A Face]
  - Outline. It draws none. [viewer: B front]
  - Shading. It adds soft gradients of its own on the face and legs. [viewer: B front] In-game, both boots sample at one flat value across their width. [shot: ingame-front]
  - Face. Its lighting shows lip and nose volume. The in-game face does not show that volume. [viewer: B front] [shot: ingame-front]
  - Final colours. It reads brighter than the phoshco viewer. [viewer: A Front, B front] The in-game colours are darker and more saturated than both viewers. [shot: ingame-front]
- Measurements: No. Its front capture gave 5.7 head-heights for Amber, against 6.9 in the phoshco Front view of the same model. [viewer: B front, A Front] Its camera appears to sit close and look down, which enlarges the head. [inferred]
  - Xilonen: 6.5 head-heights against 7.4 in the phoshco Front view. [viewer: B front, A Front] Its figures came out at about 0.83 and 0.87 of the phoshco ones for the two characters, so the error runs in the same direction each time. [inferred]
  - Clorinde: its side capture gives 6.7 head-heights against about 7.0 in the phoshco Side view, a ratio of about 0.96. [viewer: B side, A Side] Its front capture puts the skirt hem 40% of the way from chin to sole, against 38% in the phoshco Front view. [viewer: B front, A Front] The error runs the same way as on the other two characters and is smaller. [inferred]
  - Navia: its front capture puts the skirt hem 38% of the way from chin to sole, against 37% in the phoshco Front view, which is within measuring error. [viewer: B front, A Front] Its perspective is stronger than the phoshco viewer's: the tips of her skirt tails sit about 74% of the way down the figure in its front capture and about 97% in its back capture. [viewer: B front, B back]
  - Zhongli: 7.6 head-heights against 8.4 in the phoshco Front view, a ratio of about 0.90. [viewer: B front, A Front]
  - Wriothesley: 6.9 head-heights against 7.7 in the phoshco Front view, again a ratio of about 0.90. [viewer: B front, A Front] Over six characters the ratio has run from 0.83 to 0.96, always below 1. [inferred]
- Checked against: `ingame-front` and `ingame-back`, YouTube playthrough footage captured by Mustafa, in [characters/amber.md](../characters/amber.md). No other character has an in-game shot yet, so their lines compare the two viewers with each other only.
