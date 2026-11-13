# Versions
Game: GunZ: The Duel
Reference version: IJJI
Confidence: Low
Status: draft

Researched 2026-11-13. Confidence is Low because only the build timeline and the hit-registration split are Verified. Differences in movement, cancels and weapon behaviour are mostly Single-source or Unknown. `references/reports/` was empty, so no Research report was used as a map. Mustafa confirmed the reference version on 2026-11-13.

## How to read this doc

- Labels in `code` are the project's version labels. They became final when Mustafa confirmed the reference version on 2026-11-13.
- Evidence tags follow `_conventions.md`. A tag covers the sentence or table row it ends.
- `S` numbers are pages that were opened. `X` numbers are pages that refused to open and were seen only as search-result excerpts. A claim that rests only on `X` sources is marked "excerpt only" and is a lead, not a finding.
- "Lead" means the target's client decides whether a shot hit. "Anti-lead" means the shooter's client decides. [Verified: S4, S11, S13]

## Summary

1. The original game ran as separate regional services on MAIET's client: `KR`, `INT`, `IJJI` then `AERIA`, `JP`, `BR`, `IN`. The North American and European service closed on 31 May 2013. [Verified] The Korean one ended in 2014. [Single-source: S28]
2. Masangsoft relaunched the game in Korea in 2016 (`KR-MS`) and worldwide on Steam on 13 August 2026 (`STEAM`). [Verified]
3. Between 2013 and 2026, players in North America and Europe had only private servers (`PS`), built from leaked files of two client generations, "1.0" (`L10`) and "1.5" (`L15`). [Verified]
4. Hit registration is the one build difference several sources agree on: lead in `IJJI` and `AERIA`, anti-lead added by `PS`, an anti-lead setting from 0 to 100 in `STEAM`. [Verified]
5. No source was found that describes a difference in movement or cancel rules between `KR`, `INT`, `IJJI`, `AERIA`, `L10` and `L15`. Unknown; see "Searched and not found".
6. The documented rule changes all come from Masangsoft's builds: `KR-MS` (a planned rule set without block directly after slash) and `STEAM` (tick rate, weapon weight and ammo, equipment stats, movement handling at high frame rates). [Single-source each]
7. Competitive players have not settled on one build. They use ijji as the yardstick and disagree on lead versus anti-lead. [Community consensus]
8. Reference version: `IJJI`, confirmed by Mustafa on 2026-11-13.

## Builds

### Official services

| Label | Build | Operator | Period | Hit registration | Tag and sources |
|---|---|---|---|---|---|
| `KR` | Korean service, MAIET era | MAIET, published on Netmarble | Start June 2003 (S1) or June 2004 (S2). Ended 2014 (S28) | Unknown | Operator: Verified (S1, S2, S22). Dates: Single-source each, in conflict |
| `INT` | International Edition, also called International GunZ or iGunz. An open beta that never left beta | MAIET | From 2005 (S1 says June 2005; S3 says in beta since 2005). Still running in March 2007, after most players had left for ijji (S3). Shutdown date Unknown | Lead (S3) | Existence: Verified (S1, S3, S22). Dates: Single-source |
| `IJJI` | ijji GunZ, North America and Europe | NHN USA, ijji portal | Closed beta ended 17 Nov 2006. Live 29 Nov 2006. Moved to Aeria March 2012 (S1, S2) | Lead (S11, S13) | Verified |
| `AERIA` | Aeria GunZ, continuation of the ijji service | Aeria Games | March 2012 to 31 May 2013 (S1, S2) | Lead (S13) | Dates: Verified. Hit registration: Single-source |
| `JP` | Japanese service | CJ Internet Japan, Netmarble portal | Open beta, then official service from 21 Oct 2005 (S27). S26 gives 2004 to 2010 | Unknown | Operator: Verified (S22, S26, S27). Dates: Single-source each |
| `BR` | Brazilian service | Level Up! Games | From July 2006 (S1, S2). End Unknown | Unknown | Operator: Verified (S1, S2, S22) |
| `IN` | Indian service, open beta | Level Up! Games | From June 2006 (S1). End Unknown | Unknown | Single-source per field (S1 date, S22 operator) |
| `KR-MS` | Korean relaunch | Masangsoft | 2016 (S1, S28). Still running 30 Sep 2024 (S26). Archived client builds are dated 2016-01-07, 2016-06-02, 2016-07-28 and 2022-12-06 (S30) | Unknown | Relaunch: Verified. Build dates: Single-source |
| `STEAM` | Steam release, marketed as a remaster | Masangsoft | Store page 30 Sep 2024, Korean only (S26). Closed beta 25 to 29 Sep 2025 (S29). Second playtest 11 to 14 Dec 2025 (S9). Third playtest February 2026 (X9, excerpt only). Launch 13 Aug 2026, 17:00 PDT (S6, S8) | Anti-lead setting from 0 to 100 (S9, S12) | Verified |

`STEAM` is a live build that is still being patched. Write the date with every `STEAM` claim, for example "`STEAM`, patch of 9 Nov 2026".

Other regional services: Unknown. An archive index lists installers named "lggunz beta installer 2005" and "mpogspain gunz 27/08/2007" without saying which services they belonged to, and lists gunz.kaybo1.com among official sites as shut down (S30). What these were is not established. Not searched one by one.

### Leaked files and source

| Label | What it is | Origin | Tag and sources |
|---|---|---|---|
| `L10` | "1.0" generation: server files dated 13 June 2007 and 21 July 2008 (X3), and a source described as leaked around 2007 (S4, S30) | Which regional service it came from: Unknown | Existence: Verified (S4, S30). File dates: excerpt only |
| `L15` | "1.5" generation source, named "Summer 2011", released on RaGEZONE in November 2011 (S30, S34) | One poster dates the 1.5 client to around 2009 or 2010 on ijji (X3) | Existence: Verified (S30, S34). Origin date: excerpt only |

Client generation is a second axis next to the service. When a claim depends on it, write `IJJI (1.0 client)` or `IJJI (1.5 client)`. Installers dated 2007-06-24 and 2008-11-21 are archived as ijji installers (S30). [Single-source; `IJJI`]

### Private servers

| Label | Server | Base | Hit registration | Tag and sources |
|---|---|---|---|---|
| `PS` | The family as a whole, 2007 to today | `L10` or `L15`, usually heavily customised | Mostly anti-lead, with lead still selectable per server or room | Verified (S13, S18, S32, S33) |
| `PS-FGZ` | Freestyle GunZ, created early 2007 | 1.5 client by May 2013 | "Anti-Lead + Lead" | Verified (S13, S18) |
| `PS-RG` | Refined Gunz, a codebase other servers build on | `L10` | Three selectable modes: lead, anti-lead, server-based (unfinished) | Single-source (S4) |
| `PS-IGZ` | International GunZ at igunz.net, with a ranked queue and ladder | Open GunZ, a fork of Refined Gunz kept by the igunz.net developers | Lead and anti-lead (X5, excerpt only) | Base: Single-source (S5). Ranked play: Single-source (S19) |

Other servers named in sources: GunZ: The Last Duel, listed by one wiki as a 2017 North American version run by M2O (S22) and advertised as an ijji replica with lead (X11, excerpt only); RealGunZ, anti-lead on by default and switchable by the room host (S32); gunz.vn, where a room tag turns anti-lead off (S33); DarkGunZ, ArticGamers and Hero Gamers (S2). [`PS`; Single-source each]

### Names that cause confusion

- "International GunZ" and "iGunZ" mean two things: MAIET's 2005 beta (`INT`) and the private server at igunz.net (`PS-IGZ`). [Verified: S3, S5, S19]
- "Classic" in Korea is the name of a `KR-MS` rule set, not the original game (S14). [Single-source]
- "Remastered" is the Steam release (S1, S31). [Verified; `STEAM`]
- GunZ 2: The Second Duel is a separate sequel, not a build of this game (S1). It is out of scope. [Single-source]
- One wiki uses the nicknames KGunZ, IGunZ, JGunZ, InGunZ, NAGunZ and BGunZ for the regional services (S22). [Single-source]

### Date conflicts

- Korean start: June 2003 (S1), June 2004 (S2), the year 2004 (S28).
- `INT` start: June 2005 (S1), February 2005 (X6, excerpt only), in beta since 2005 (S3).
- ijji closed beta end: 17 Nov 2006 (S1), 15 Nov 2006 (X6, excerpt only).
- Move to Aeria: March 2012 (S1, S2); a transfer in July 2012 (X10, excerpt only).
- Korean relaunch day: 17 March 2016 after a test on 7 to 14 January 2016 (X1 and X3, excerpt only). The first archived Masangsoft client is dated 2016-01-07 (S30).

## What differs between builds

### Netcode and hit registration

| # | Difference | Builds | Tag | Sources |
|---|---|---|---|---|
| N1 | Combat traffic runs peer to peer between players' clients. | MAIET-era services in general (S1); described for `INT` and `IJJI` (S3, S11) | Verified | S1, S3, S11 |
| N2 | Lead: the target's client registers the hit, so the shooter aims ahead of a moving target, further ahead as ping rises. S4 words the mode as "target does immediate hit registration". | `INT`, `IJJI`, `AERIA` | Verified | S3, S4, S11, S13 |
| N3 | No official MAIET-era service had anti-lead. The post speaks of official servers in general and does not list them. | Official MAIET-era services | Single-source | S13 |
| N4 | Anti-lead: the shooter's client registers the hit at once. Private servers added it and usually kept lead selectable. | `PS` | Verified | S4, S13, S18, S32, S33 |
| N5 | Under lead, aim where the target will be after about twice its ping. | Version unclear | Single-source | S20 |
| N6 | The basic-info update rate is 10 per second in the 1.0 source. Refined Gunz raised it to 33. | `L10`, `PS-RG` | Single-source | S4 |
| N7 | Refined Gunz adds an unfinished third mode: players do not connect to each other and the server registers hits with lag compensation. | `PS-RG` | Single-source | S4 |
| N8 | The Korean service supported NAT, firewalls and shared-IP routers. The International Edition did not. | `KR`, `INT` | Single-source | S3 |
| N9 | Anti-lead is a setting from 0 to 100, added for the second playtest. How the value changes hit registration, its default, and whether it is set per client or per room: Unknown. Masangsoft has not published it. | `STEAM`, from Dec 2025 | Verified that the setting exists | S9, S12 |
| N10 | Tick rate was raised for the second playtest. Value: Unquantified. | `STEAM`, from Dec 2025 | Single-source, developer | S9 |
| N11 | Players describe combat as still peer to peer. No developer statement was found. Official notices name regional match servers (North America West, Europe). | `STEAM`, Sep 2025 to Aug 2026 | Community consensus | S7, S12, S17; X3, X8 |
| N12 | One player's test with anti-lead at 100: kills on a 20 to 30 ping target sometimes come without hit sound or marker, and shots at 100 to 150+ ping targets register less reliably. The tester calls the second part mostly anecdotal. | `STEAM`, post dated 14 Sep, year not shown | Single-source | S12 |
| N13 | Before the first test the developer described the trade-off: with anti-lead the shooter sees hits count, and the target can be hit after reaching cover. A poll of 2,471 votes gave 55% for anti-lead, 40% for a room option and 5% against. | `STEAM`, Jan to Mar 2025 | Single-source each | S10, S25 |

Netcode and hit registration of `KR`, `JP`, `BR`, `IN` and `KR-MS`: Unknown. Searched for: GunZ version history, lead and anti-lead explanations, Korean relaunch notes.

### Movement

| # | Difference | Builds | Tag | Sources |
|---|---|---|---|---|
| M1 | The one source that compares them says the same rules apply to both. | `INT`, `IJJI` | Single-source | S3 |
| M2 | No source describes a difference in dash, wall-run, wall-jump, tumble or air control. The largest technique list found carries no version notes at all (S23). | `KR`, `INT`, `IJJI`, `AERIA`, `L10`, `L15` | Unknown; searched | S23 |
| M3 | The 9 Nov 2026 patch changed how movement data is updated and how frame intervals are handled in "environments running at 200 FPS or higher". What behaved differently before the patch is not stated. | `STEAM`, patch of 9 Nov 2026 | Single-source, developer | S7 |
| M4 | Private-server players treat frame rate as part of the game: advice to cap at 250 or 333, reports that higher values feel slow and floaty, a claim that slowing the client made combos easier on ijji, and a frame limiter added by MAIET around 2011. | `PS`, `IJJI` | Excerpt only | X3, X4, X12 |
| M5 | Camera lock during wall-run was removed for the second playtest. Whether earlier builds lock the camera is not stated. | `STEAM`, from Dec 2025 | Single-source, developer | S9 |
| M6 | Hitboxes: in January 2025 the developer said character models were slightly restructured and hitboxes kept from the previous GunZ. A launch-day reviewer says the male character's larger hitbox no longer gives a benefit. Not reconciled. | `STEAM` | Single-source each | S10, S15 |
| M7 | In the January 2016 Korean plan, shoes add movement speed. | `KR-MS` (plan) | Single-source | S14 |
| M8 | A launch-day reviewer describes the game as feeling slowed down, as if under water. | `STEAM`, 13 Aug 2026 | Single-source | S15 |

### Cancels

| # | Difference | Builds | Tag | Sources |
|---|---|---|---|---|
| C1 | K-style cancels exist in every MAIET-era build, and MAIET left them in. A 2007 guide says MAIET "programmed AROUND" k-Style. | `KR`, `INT`, `IJJI` | Community consensus | S3, S21 |
| C2 | Conflict. (a) In the first months after release the developers shipped a K-style fix and withdrew it after backlash; no date or reference is given (S21). (b) MAIET never patched or rebalanced K-style, and the first intervention was Masangsoft's 2016 relaunch (X1, excerpt only). Not reconciled. | `KR` | Single-source each | S21; X1 |
| C3 | Planned "Masangsoft Server" rule set: block directly after slash removed, which the source labels "BF and DBF" (butterfly and double butterfly); the roughly 400 ms shooting delay after a slash shot made to vary by weapon; 3 seconds of invulnerability after spawn. | `KR-MS` (plan, Jan 2016) | Single-source (fan translation of a developer note) | S14 |
| C4 | Planned "Classic Server" rule set: block directly after slash kept; animation delay after swap weapon reduced to 500 ms. Conflict: a secondhand report says the classic mode increased the swap delay to weaken K-style (S24). | `KR-MS` (plan, Jan 2016) | Single-source each | S14; S24 |
| C5 | What shipped in Korea: board posts describe a free channel where steps are blocked except butterfly and dagger steps and where reload cancelling does not work, and a classic channel where steps work. A wiki describes the reverse: a free channel that allows K-style and a classic channel with changed weight and movement speed. It also says Masangsoft later returned to the old version. The accounts are undated and not reconciled. | `KR-MS`, 2016 onward | Excerpt only | X1, X2 |
| C6 | The developer says K-style is kept ("maintain the iconic K-style gameplay"). No technique-by-technique comparison with earlier builds was found. | `STEAM` | Single-source, developer | S8, S10 |
| C7 | A launch-day reviewer reports that slash range was increased, and that block cannot stun below 30 ping, which he blames on the tick-rate change. | `STEAM`, 13 Aug 2026 | Single-source | S15 |
| C8 | A 20 ms mouse-wheel delay was added for the second playtest. What it gates is not stated. | `STEAM`, from Dec 2025 | Single-source, developer | S9 |
| C9 | No source describes a difference in cancel rules between the two leaked generations. | `L10`, `L15` | Unknown; searched | none |
| C10 | Private servers offer room switches that remove single techniques, such as no flip and no massive. These are room options, not build differences. | `PS` | Verified | S32, S33 |
| C11 | A guide notes that a technique it calls Spawn Shot may have been patched. It gives no date or build. | Version unclear | Excerpt only | X14 |

### Weapon behaviour

| # | Difference | Builds | Tag | Sources |
|---|---|---|---|---|
| W1 | The 1.5 generation added item types (potions, elemental grenades, avatars), modes (Challenge Quest, Duel Tournament, Survival), a new interface and animations. No source describes changed weapon rules. | `L15`, `IJJI (1.5 client)` | Excerpt only | X3 |
| W2 | Weapon stats differ by build. See Values. | `IJJI`, `PS-IGZ`, `STEAM` | Single-source each | S3, S16; X13 |
| W3 | Shotgun spread on igunz.net is fixed, with no guaranteed pellet at the centre: "This spread is completely static." Spread behaviour in MAIET-era builds: Unknown. | `PS-IGZ`, 17 Apr 2025 | Single-source | S19 |
| W4 | Weapons carry type-code names such as AV-Type Shotgun and ZR-Type Revolver instead of the MAIET-era item names. Players still use the old names. | `STEAM` | Single-source, developer | S7, S16 |
| W5 | Weapons were rebalanced by type and weight for launch. Weight and maximum ammo changed again on 9 Nov 2026. | `STEAM` | Single-source, developer | S7, S8 |
| W6 | Equipment stats: the launch press release says stat advantages from progression and equipment were removed and equipment is cosmetic. Players after launch still discuss armour stats and HP and AP totals. Not reconciled. | `STEAM`, Aug 2026 | Single-source each | S8; S16, X8 |
| W7 | Player claims after launch: shotgun damage is higher than in the original, revolvers were made heavier, rockets are weaker and carry one spare magazine. | `STEAM`, Aug 2026 | Single-source each | S15, S16 |
| W8 | January 2016 Korean plan: weapon levels removed; gloves add ammo, rings add maximum weight, torso adds maximum HP, bottoms add AP. | `KR-MS` (plan) | Single-source | S14 |
| W9 | Private servers edit items heavily: about 2,000 items on Freestyle GunZ in 2013. | `PS-FGZ` | Single-source | S18 |

### Values

| Value | Number | Build | Source |
|---|---|---|---|
| Shooting-animation delay in a slash shot | 400 ms. The translator says this passage is unclear | `KR`, as inherited by `KR-MS` | S14 |
| Planned animation delay after swap weapon | 500 ms | `KR-MS` classic rule set (plan) | S14 |
| Planned invulnerability after spawn | 3 s | `KR-MS` Masangsoft rule set (plan) | S14 |
| Basic-info update rate | 10 per second; 33 per second | `L10`; `PS-RG` | S4 |
| Lead distance | About twice the target's ping | Version unclear | S20 |
| Anti-lead setting range | 0 to 100 | `STEAM` | S9 |
| Tick rate | Unquantified | `STEAM` | S9 |
| Frame rate named in the movement patch | 200 FPS and above | `STEAM`, 9 Nov 2026 | S7 |
| Avenger shotgun | Damage 10, delay 1200, unit not stated | `IJJI`, March 2007 | S3 |
| Avenger shotgun damage | 12 lowered to 11 | `PS-IGZ`, 2017 | X13, excerpt only |
| High-end shotgun | Damage 13 with 6 shells now, against damage 8 with 5 shells for the 2004 game. Player claim | `STEAM`, Aug 2026 | S16 |
| HP and AP | Default 125 and 100 in vanilla rooms | `PS` (gunz.vn) | S33 |
| HP and AP | 190 and 150. Player claim; the same player expects 110 to 140 | `STEAM`, Aug 2026 | S16 |
| Weapon weight | ZR-Type Revolver x2 35 to 30; AV-Type Shotgun 35 to 30 | `STEAM`, 9 Nov 2026 | S7 |
| Maximum ammo | RP-Type Pistol 85 to 120; LN-Type SMG 160 to 220; AV-Type Shotgun 18 to 21; NC-Type Rifle 180 to 210; GL-Type Rocket 10 to 12 | `STEAM`, 9 Nov 2026 | S7 |
| League pre-season format | 4 versus 4 elimination, first to 5 points, 5-minute rounds. Labelled a test | `STEAM`, from 9 Nov 2026 | S7 |

S3 holds a full weapon table for `IJJI` in March 2007. It belongs in `systems/ranged.md`, not here.

## Which build competitive players treat as the reference

Not settled. No source names one build as the standard for competitive play.

1. Players use ijji as the yardstick when they describe other builds. A private server states its rates relative to ijji (S18). A 2007 guide says everyone moved to ijji's version (S3). Steam posters date their experience by ijji (S11, S16). Servers and reviewers recommend a build by saying it plays like ijji (X8, X11, excerpt only). [Community consensus; `IJJI`]
2. From June 2013 to August 2026 there was no official service for North America and Europe, so competitive play in English ran on private servers (S1, S2). Those mostly ran anti-lead, usually with lead selectable (S13, S18, S32, S33). [Verified; `PS`]
3. Veterans disagree on lead versus anti-lead. In one Steam thread, posters who played both eras argue each side: some call anti-lead simply better and say lead was only ever a workaround for peer-to-peer connections; others say lead can be learned, makes movement count for more than aim, and avoids deaths behind cover (S11). The developer's poll split 55, 40 and 5 (S25). [Verified that the split exists; `IJJI`, `PS`, `STEAM`]
4. Private servers are not one build. They sit on different bases and change items, stats, spread and rates (S4, S5, S18, S19, S33). [Verified; `PS`]
5. Competitive play now also runs on `STEAM`: clan tournaments since August 2026 and a league pre-season since 9 November 2026 (S7, S31). Launch reviews are split. Some call it worse than private servers (S15); one says it feels like ijji (X8, excerpt only). [Single-source each; `STEAM`]
6. A statement from a ladder, a tournament organiser or recognised top players that names a reference build: Unknown. Searched for: competitive GunZ standard build, lead versus anti-lead on Reddit, private server closest to ijji. No Reddit page was returned by any search.

## Reference version

`IJJI`, confirmed by Mustafa on 2026-11-13. It is read as ijji GunZ with its own hit registration, which is lead. Use `IJJI (1.0 client)` or `IJJI (1.5 client)` only where a claim depends on the client generation.

Reasoning, in the order `_conventions.md` sets:

1. Competitive consensus. There is none on a single build. The nearest thing to it is that players measure every other build against ijji.
2. Original international release. Taken literally this is `INT`, MAIET's 2005 beta. It never left beta, most players had left it by March 2007, and the one source that compares the two says the same rules apply (S3). A wiki page seen only as an excerpt calls it a very limited version with player-versus-player matches and basic items (X7). Almost nothing documents `INT` on its own. `IJJI` is the first full international service, and it is the build the dated English guide found describes (S3). On the evidence so far, choosing `IJJI` over `INT` changes the label and not the content.
3. Steam release. `STEAM` comes third and is recorded as a difference in each doc.

What the choice means for the other docs: each doc describes `IJJI`. Anti-lead on `PS`, the `KR-MS` rule sets and the `STEAM` changes go under "Version differences".

Two facts to keep in mind when using it:

- The ijji service moved to Aeria in 2012 and Aeria closed it in 2013. `IJJI` can be checked only through period guides, period footage and private-server recreations.
- `STEAM` is an official build that can be opened today (S6). It is also still changing: movement handling and weapon values were patched four days before this doc was written (S7).

## Importance to audience

- Lead versus anti-lead: Essential to the feel. It is the build difference veterans argue about most, and both sides tie it to how much movement and aim are worth (S11).
- Sword cancels being present, above all block directly after slash: Essential to the feel. When the Korean plan to remove it became known, a player doubted anyone would play a version without the game's famous exploits (S14), and the developer names K-style as what defines the game (S8, S10).
- Frame-rate effects: not rated. Too little of the evidence could be opened.
- Regional differences between `KR`, `JP`, `BR` and `IN`: not rated. No player discussion was found.

## Open questions

1. Which regional service did the leaked 1.0 files come from? Check: read the first posts of the RaGEZONE release threads for the June 2007 and July 2008 files (X3) and paste the text. Read only; nothing from leaked files belongs in this repo (README).
2. Did the change from the 1.0 to the 1.5 client alter any movement, cancel or weapon rule? Check: ask on a private-server Discord that runs both generations, or film the same technique on a 1.0-based and a 1.5-based server.
3. Did MAIET ever ship and withdraw a K-style fix (C2)? Check: open the NamuWiki page (X1) and paste the K-style section with its footnotes 2 and 3.
4. What did the Korean relaunch ship, and what do its channels do today (C5)? Check: the same NamuWiki page, and the three Korean board posts (X2).
5. How does the `STEAM` anti-lead setting work, what is its default, and is it set per client or per room (N9)? Check: screenshot the setting in the Steam client's options and in the room-creation screen.
6. What is the `STEAM` tick rate, and what was it before (N10)? Check: ask in the official Discord's developer-notes channel.
7. Which techniques behave differently on `STEAM` than on `IJJI` (C6, C7, M6)? Text cannot settle this. Check: film slash range, block stun and one butterfly on `STEAM`, and compare with a period ijji clip of the same technique.
8. How does frame rate change movement and cancels on `IJJI`, and which caps did official clients have (M4)? Check: open the RaGEZONE threads on the MAIET frame limiter and on the ProMode project (X3) and paste the posts; on `STEAM`, film one dash chain at 60 FPS and at 240 FPS.
9. Exact dates: Korean start (2003 or 2004), `INT` start and shutdown, `BR` and `IN` shutdown.
10. Did `INT` and `IJJI` differ in any rule in scope? Only S3 addresses it.
11. The full `STEAM` patch history. The Steam news pages opened here showed only the launch week and the 9 Nov 2026 patch; notes of 14 Sep and 5 Oct 2026 appeared as excerpts. The news page also lists patch notes dated 30 Oct 2026 and 2 Nov 2026, which were not read for this doc. Check: scroll the Steam news hub in a browser and paste every line on movement, cancels, hit registration or weapon values.
12. Do today's top competitive players name a reference build? Check: ask in the clan-war or ladder channels of the largest Discord servers, and record who said what.
13. Was any technique patched out of a MAIET-era build? One guide hints at Spawn Shot (C11). Check: open the GameFAQs guide (X14) and paste what it says about patches.

## Sources

### Opened

| ID | Source | Build it describes | Used for |
|---|---|---|---|
| S1 | Wikipedia, "GunZ: The Duel". https://en.wikipedia.org/wiki/GunZ:_The_Duel | all | Release dates, operators, peer-to-peer statement, closure, Masangsoft, Steam |
| S2 | MMOHuts, "GunZ: The Duel" review, published 15 Mar 2015. https://mmohuts.com/review/gunz-the-duel | `KR`, `IJJI`, `AERIA`, `BR`, `PS` | Operators and dates, private servers named |
| S3 | Kistrael, "Gunz the Duel: ijji Edition Guide" v0.9, 18 Mar 2007, mirror. http://dogecandy.com/walkthroughs/gunz-the-duel-2/ | `IJJI`, `INT`, `KR` | State of `INT` in 2007, same rules claim, lead shooting, NAT support, MAIET's stance, weapon table |
| S4 | Refined Gunz README. https://github.com/Asunaya/refinedgunz | `L10`, `PS-RG` | 1.0 source, three netcode modes, update rate |
| S5 | Open GunZ README. https://github.com/TriForceX/OpenGunZ | `PS-IGZ` | Fork lineage of igunz.net |
| S6 | Steam store page, GunZ: The Duel. https://store.steampowered.com/app/3139440/GunZ_The_Duel/ | `STEAM` | Release date, developer, publisher |
| S7 | Steam community hub and news list, read 2026-11-13. https://steamcommunity.com/app/3139440 and https://steamcommunity.com/app/3139440/allnews/ | `STEAM` | Patch of 9 Nov 2026, league format, launch-week notices, match server regions |
| S8 | Masangsoft press release, 5 Aug 2026, on Game Developer. https://www.gamedeveloper.com/press-release/legendary-action-shooter-gunz-the-duel-returns-launching-globally-on-steam-august-13 | `STEAM` | Launch date, rebalance, equipment stats, K-style kept |
| S9 | Masangsoft press release, 1 Dec 2025, on Games Press. https://www.gamespress.com/GunZ-The-Duel-Announces-Second-Global-Playtest | `STEAM` | Tick rate, anti-lead setting, wall-run camera, mouse-wheel delay |
| S10 | PinoyTechSaga, 8 Jan 2025, relaying the developer's Discord notes. https://pinoytechsaga.blogspot.com/2025/01/gunz-new-updates-steam-release.html | `STEAM` | Anti-lead trade-off, engine kept, hitboxes, K-style kept |
| S11 | Steam discussion, "MUST DOs FOR MASANG", 6 Nov 2024 to 4 Feb 2025. https://steamcommunity.com/app/3139440/discussions/0/4637112519824028470/ | `IJJI`, `PS`, `STEAM` | Veterans on lead and anti-lead, original netcode |
| S12 | Steam discussion, "How Antilead works", dated 14 Sep, no year shown. https://steamcommunity.com/app/3139440/discussions/0/563667940587736552/ | `STEAM` | Anti-lead slider, player test |
| S13 | Steam discussion in the GunZ 2 forum, "Is Anti-Lead an option?", 27 Feb 2014. https://steamcommunity.com/app/242720/discussions/0/558749190684404879/ | `IJJI`, `AERIA`, `PS` | No anti-lead on official servers, receiver-side registration |
| S14 | Steam discussion in the GunZ 2 forum, "Known Masangsoft plan for Gunz and Gunz 2", 5 Jan 2016. https://steamcommunity.com/app/242720/discussions/0/458605578276300996 | `KR-MS` | Two planned rule sets, delays |
| S15 | Steam reviews, top rated, 13 to 14 Aug 2026. https://steamcommunity.com/app/3139440/reviews/?browsefilter=toprated | `STEAM` | Launch-day player reports |
| S16 | Steam discussion, "ShotGunZ: The Duel...", page 3, 21 to 23 Aug 2026. https://steamcommunity.com/app/3139440/discussions/0/587309530805829446/?l=english&ctp=3 | `STEAM` | Player claims on weapon values |
| S17 | Steam discussion, "I hope they fix the how easy it is to hack", 25 to 27 Sep 2025. https://steamcommunity.com/app/3139440/discussions/0/595161023680590106/?l=italian | `STEAM` | Peer-to-peer described by players |
| S18 | RaGEZONE, Freestyle GunZ advertisement, 5 May 2013. https://forum.ragezone.com/threads/gunz-freestyle-gunz-gunz-1-5-anti-lead-24-7-online-no-lag-more.929466/ | `PS-FGZ` | 1.5 client, anti-lead and lead, creation year |
| S19 | igunz.net home page, update notes of April and May 2025. https://igunz.net/ | `PS-IGZ` | Ranked queue, static spread |
| S20 | GunZ Guide on GitBook, "Lead & Anti Lead". https://gunz.gitbook.io/gunz-guide/how-to-play-gunz/combat-guide/lead-and-anti-lead | unclear | Lead distance |
| S21 | GunZ Wiki on Fandom, "K-Style". https://gunz.fandom.com/wiki/K-Style | unclear | Withdrawn fix claim |
| S22 | GunZ Wiki on Fandom, "GunZ: The Duel". https://gunz.fandom.com/wiki/GunZ:_The_Duel | all | Regional versions and operators |
| S23 | StrategyWiki, "Korean-Style and Advanced Techniques". https://strategywiki.org/wiki/GunZ_The_Duel/Korean-Style_and_Advanced_Techniques | unclear | Checked for version notes; it has none |
| S24 | CritPoints, "Gunz 1 to 2", 11 Mar 2016. https://critpoints.net/2016/03/11/gunz-1-to-2/ | `KR-MS` | Conflicting swap-delay report |
| S25 | gunz-online.net, anti-lead vote results, 22 Mar 2025. Site ownership not stated. https://gunz-online.net/gunz-the-duel-anti-lead-system-vote-results-are-in/ | `STEAM` | Poll numbers |
| S26 | Game*Spark, 30 Sep 2024. https://www.gamespark.jp/article/2024/09/30/145570.html | `STEAM`, `JP`, `KR-MS` | Store page date, Japanese service, Korean service running |
| S27 | 4Gamer, 21 Oct 2005. https://www.4gamer.net/news/history/2005.10/20051021160758detail.html | `JP` | Japanese official launch |
| S28 | MMO Culture, GunZ tag page. https://backend.mmoculture.com/tag/gunz | `KR`, `KR-MS` | Korean service 2004 to 2014, relaunch |
| S29 | COGconnected, 17 Sep 2025. https://cogconnected.com/?p=372320 | `STEAM` | Closed beta dates |
| S30 | WhyWolfie, GunZ-The-Duel archive index on GitHub. https://github.com/WhyWolfie/GunZ-The-Duel | `IJJI`, `KR-MS`, `L10`, `L15` | Dated installers and client builds, sources listed |
| S31 | Official site; gz.masanggames.com redirects to it. https://gz.ludenus.com/ | `STEAM` | "Remastered", tournaments, launch notice |
| S32 | RealGunZ, its own page on private servers. https://realgunz.net/guides/most-popular-active-private-servers-gunz-realgunz | `PS` | Anti-lead default, room tags |
| S33 | gunz.vn server info. https://gunz.vn/gunz/info | `PS` | Room tags, default HP and AP |
| S34 | Repost of emisand's source build guide, 20 Nov 2011. https://tutorialprivateserver.blogspot.com/2011/11/build-gunz-source-code.html | `L15` | 1.5 source release |

### Not opened, seen as search excerpts only

These refused the fetch. Do not file them in `references/sources.md` until someone has opened them.

| ID | Page | What the excerpt said |
|---|---|---|
| X1 | NamuWiki, Korean-language article on GunZ: The Duel. https://namu.wiki/w/%EA%B1%B4%EC%A6%88%20%EB%8D%94%20%EB%93%80%EC%96%BC | Korean service history, relaunch dates, channels, no K-style patch under MAIET, return to the old version |
| X2 | Masangsoft Korean board posts: gz.masanggames.co.kr/GZ_BOARD5/1529266, www.masanggames.co.kr/GZ_BOARD3/1686267, nx.masanggames.co.kr/GZ_BOARD3/2826060 | Which channel allows steps, reload shot in each channel |
| X3 | RaGEZONE threads: release index, "GunZ 1.5 Client", "Gunz 1.5 Client & Server Files [CLEAN]", "2007 GunZ Files", "Gunz 21 July 2008 Full Server Files", "MAIET finally added a FPS limiter to GunZ", "GunZ Challenge ProMode", "K-Gunz Is back", "[STEAM GUNZ] Steam GunZ Private Server Developement Blog" | Dated file builds, what 1.5 contains, frame limiter, underclocking claim, January 2016 test dates, peer-to-peer combat layer in the Steam client |
| X4 | Universe GunZ forum, thread 2346 (now redirects to the home page) | Frame-rate advice of 250 and 333 |
| X5 | International GunZ on X, 3 Apr 2020. https://x.com/iGunZTheDuel/status/1246198794120843264 | Lead and anti-lead both supported |
| X6 | A 2007 copy of the Wikipedia article (xenorr.blogspot.com) and Wikipedia's talk archive 2 | `INT` start February or June 2005, ijji closed beta dates |
| X7 | GunZ Wiki on Fandom, "North-American GunZ" | `INT` described as a very limited version |
| X8 | Steam reviews not shown on the opened page | A review saying it feels like ijji; a review that had expected servers instead of peer to peer; armour stats |
| X9 | Games Press, 2 Feb 2026 | Third playtest at Steam PvP Fest |
| X10 | Wikipedia, "Ijji" | GunZ transferred to Aeria in July 2012 |
| X11 | Gunzduels advertisement in the GunZ 2 Steam forum; RaGEZONE thread on GunZ: The Last Duel | Advertised as an ijji replica, lead only |
| X12 | RealGunZ K-style guide; gunz.com.br reload shot guide | Frame-rate advice |
| X13 | PinoyTechSaga, 2017, on International GunZ | Avenger damage 12 to 11 |
| X14 | GameFAQs, GunZ The Duel FAQ by sulfre | Spawn Shot "may or may not have been patched"; reload shot described as a later discovery |

Could not be opened at all, with no usable excerpt: the MMOFury interview of 2008 cited by Wikipedia (archive blocked), two Neowin news items on International GunZ, the Neoseeker copy of S3.

### Excluded

gunz-the-duel.wiki, gunztheduel.online and the ExitLag blog. They read as generated search-engine pages, give no sources, and one dates the Steam launch to early 2026 against the store page's 13 August 2026.

### Searched and not found

- Patch notes from MAIET, ijji or Aeria that changed movement, cancels, hit registration or weapon timing. Searched for: ijji GunZ patch notes, K-style nerf, reload shot patched, slash and block patched. The only ijji updates found are a shop opening, a quest update and a sound update (S1).
- A description of rule differences between the 1.0 and 1.5 clients. Searched for: GunZ 1.0 vs 1.5 differences k-style, 1.5 client origin.
- A competitive body or top player naming a reference build. Searched for: competitive standard, lead versus anti-lead on Reddit, private server closest to ijji.
- How the `STEAM` anti-lead setting works and the tick-rate value. Searched for: developer note on the anti-lead slider, tick rate.
- Shutdown dates for `INT`, `BR` and `IN`.
- Other regional services (Europe on its own, Taiwan, China, Southeast Asia) were not searched one by one.
