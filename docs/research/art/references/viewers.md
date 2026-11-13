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

Called viewer A in the character docs. Lines that start with "Xilonen:" use the view names of [characters/xilonen.md](../characters/xilonen.md); all other tags use those of [characters/amber.md](../characters/amber.md).

- Link: https://phoshco.github.io/model-viewer/amber (Amber's page). No URL is recorded for other characters' pages.
- Views it gives: one sheet of 16 labelled views in bind pose on a red backdrop: Front, 3/4 Front, 1/4 Front, Side, 3/4 Back, 1/4 Back, Back, Face, 1/4 Face, 3/4 Face, Footwear, Front Detail, 3/4 Front Detail, Back Detail, 3/4 Back Detail, Back of Head. [viewer: A Front]
  - Xilonen: the same 16 views on an amber backdrop. The fixed cameras do not adapt to the character: the Footwear view shows no feet, and the four Detail views frame the upper arm, hip and coat. [viewer: A Footwear, A Front Detail]
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
- Measurements: Yes, as approximate values. Its Front view gave 6.9 head-heights for Amber. [viewer: A Front] The in-game still gives at least 6.3 head-heights down to the ankle, with the feet hidden, which does not contradict it. [shot: ingame-front] Whether its camera is orthographic is unverified.
  - Xilonen: 7.4 head-heights including platform shoes. [viewer: A Front]
- Checked against: `ingame-front` and `ingame-back`, YouTube playthrough footage captured by Mustafa, in [characters/amber.md](../characters/amber.md). Xilonen has no in-game shot yet, so her lines compare the two viewers with each other only.

## Games Fashion Archive viewer

Called viewer B in the character docs. Lines that start with "Xilonen:" use the view names of [characters/xilonen.md](../characters/xilonen.md); all other tags use those of [characters/amber.md](../characters/amber.md).

- Link: https://gamesfashionarchive.net/viewer/2058/2 (the page behind Amber's full-figure captures). No URL is recorded for her outfit-only captures or for other characters' pages.
- Views it gives: free captures in bind pose on a white backdrop. The page offers a turntable and a capture tool. [community: the linked page] For Amber it gave the full figure from front and back, and the clothing alone on a blank mannequin from front and back. [viewer: B front, B back, B outfit front, B outfit back]
  - Xilonen: full figure from front, side and back. [viewer: B front, B side, B back]
- Reliable for:
  - Outfit construction, ornament placement, asymmetry, painted lines and hair clump layout. All of these matched the back view in-game. [viewer: B back] [shot: ingame-back] They also matched the front view. [viewer: B front] [shot: ingame-front]
  - Clothing detail. The outfit-only captures are the largest view of trims, stitches and emblems in either viewer. [viewer: B outfit front, B outfit back]
  - Approximate base colours. It is the more evenly lit of the two viewers, so Amber's base colours were sampled from it. It still lights the model, and skin samples sit at full brightness, so highlights may be clipped. [viewer: B front, B back]
  - Xilonen: what an outer layer hides. Its coat-off captures show the back and the inner garments that the coat covers in the phoshco sheet. [viewer: B back, A Back]
- Not reliable for:
  - Proportions. See Measurements.
  - Xilonen: completeness of the outfit. Its captures lack the coat, the chest medallion and the spiked wrist cuff that the phoshco sheet shows. Whether that is a state of the model or a choice made in the viewer is unverified. [viewer: B front, A Front]
  - Pose. It shows the bind pose only. Against the idle pose in-game, that widens the outline of sleeves and hair. [viewer: B front] [shot: ingame-front]
  - Xilonen: the arms stay in bind pose while the tail hangs in a curve. [viewer: B front, B side]
  - Outline. It draws none. [viewer: B front]
  - Shading. It adds soft gradients of its own on the face and legs. [viewer: B front] In-game, both boots sample at one flat value across their width. [shot: ingame-front]
  - Face. Its lighting shows lip and nose volume. The in-game face does not show that volume. [viewer: B front] [shot: ingame-front]
  - Final colours. It reads brighter than the phoshco viewer. [viewer: A Front, B front] The in-game colours are darker and more saturated than both viewers. [shot: ingame-front]
- Measurements: No. Its front capture gave 5.7 head-heights for Amber, against 6.9 in the phoshco Front view of the same model. [viewer: B front, A Front] Its camera appears to sit close and look down, which enlarges the head. [inferred]
  - Xilonen: 6.5 head-heights against 7.4 in the phoshco Front view. [viewer: B front, A Front] Its figures came out at about 0.83 and 0.87 of the phoshco ones for the two characters, so the error runs in the same direction each time. [inferred]
- Checked against: `ingame-front` and `ingame-back`, YouTube playthrough footage captured by Mustafa, in [characters/amber.md](../characters/amber.md). Xilonen has no in-game shot yet, so her lines compare the two viewers with each other only.
