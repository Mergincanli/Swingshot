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

Called viewer A in [characters/amber.md](../characters/amber.md). The tags below use that doc's view names.

- Link: https://phoshco.github.io/model-viewer/amber (Amber's page; no other page has been used yet)
- Views it gives: one sheet of 16 labelled views in bind pose on a red backdrop: Front, 3/4 Front, 1/4 Front, Side, 3/4 Back, 1/4 Back, Back, Face, 1/4 Face, 3/4 Face, Footwear, Front Detail, 3/4 Front Detail, Back Detail, 3/4 Back Detail, Back of Head. [viewer: A Front]
- Reliable for:
  - Outfit construction, ornament placement, asymmetry, painted lines and hair clump layout. All of these matched the back view in-game. [viewer: A Back] [shot: ingame-back] Provisional: they also matched the front view. [viewer: A Front] [shot: ingame-front]
  - Face and eye construction. Its Face view is the largest face in either viewer, with the iris about 35 px wide. [viewer: A Face]
- Not reliable for:
  - Pose. It shows the bind pose only. Provisional: against the idle pose in-game, that widens the outline of sleeves and hair. [viewer: A Front] [shot: ingame-front]
  - Outline. It draws none. [viewer: A Front]
  - Shading. It adds soft gradients of its own: on the face, as a pale band across the back of the hair, and as a cool lilac tone, about `#D0CED8`, on one side of the white boots. [viewer: A Face, A Back of Head, A Front] Provisional: in-game, both boots sample at one flat value across their width. [shot: ingame-front]
  - Colour values. It agrees with the Games Fashion Archive viewer on hue but reads darker. [viewer: A Front, B front] Provisional: the in-game colours are darker and more saturated than both viewers. [shot: ingame-front]
- Measurements: Yes, as approximate values. Its Front view gave 6.9 head-heights for Amber. [viewer: A Front] Provisional: the in-game still gives at least 6.3 head-heights down to the ankle, with the feet hidden, which does not contradict it. [shot: ingame-front] Whether its camera is orthographic is unverified.
- Checked against: `ingame-back` (confirmed gameplay, HUD in frame) and `ingame-front` (provisional: a YouTube screenshot with no game interface in frame and no video link), in [characters/amber.md](../characters/amber.md). Comparisons that rest on `ingame-front` are marked "Provisional".

## Games Fashion Archive viewer

Called viewer B in [characters/amber.md](../characters/amber.md). The tags below use that doc's view names.

- Link: https://gamesfashionarchive.net/viewer/2058/2 (the page behind Amber's full-figure captures; the page behind the outfit-only captures was not given)
- Views it gives: free captures in bind pose on a white backdrop. The page offers a turntable and a capture tool. [community: the linked page] For Amber it gave the full figure from front and back, and the clothing alone on a blank mannequin from front and back. [viewer: B front, B back, B outfit front, B outfit back]
- Reliable for:
  - Outfit construction, ornament placement, asymmetry, painted lines and hair clump layout. All of these matched the back view in-game. [viewer: B back] [shot: ingame-back] Provisional: they also matched the front view. [viewer: B front] [shot: ingame-front]
  - Clothing detail. The outfit-only captures are the largest view of trims, stitches and emblems in either viewer. [viewer: B outfit front, B outfit back]
  - Approximate base colours. It is the more evenly lit of the two viewers, so Amber's base colours were sampled from it. It still lights the model, and skin samples sit at full brightness, so highlights may be clipped. [viewer: B front, B back]
- Not reliable for:
  - Proportions. See Measurements.
  - Pose. It shows the bind pose only. Provisional: against the idle pose in-game, that widens the outline of sleeves and hair. [viewer: B front] [shot: ingame-front]
  - Outline. It draws none. [viewer: B front]
  - Shading. It adds soft gradients of its own on the face and legs. [viewer: B front] Provisional: in-game, both boots sample at one flat value across their width. [shot: ingame-front]
  - Face. Its lighting shows lip and nose volume. Provisional: the in-game face does not show that volume. [viewer: B front] [shot: ingame-front]
  - Final colours. It reads brighter than the phoshco viewer. [viewer: A Front, B front] Provisional: the in-game colours are darker and more saturated than both viewers. [shot: ingame-front]
- Measurements: No. Its front capture gave 5.7 head-heights for Amber, against 6.9 in the phoshco Front view of the same model. [viewer: B front, A Front] Its camera appears to sit close and look down, which enlarges the head. [inferred]
- Checked against: `ingame-back` (confirmed gameplay, HUD in frame) and `ingame-front` (provisional: a YouTube screenshot with no game interface in frame and no video link), in [characters/amber.md](../characters/amber.md). Comparisons that rest on `ingame-front` are marked "Provisional".
