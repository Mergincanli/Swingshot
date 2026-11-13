# GunZ: The Duel: A Map of Its Combat Versions, Play Styles, Systems and Techniques

Competitive players have not settled on one reference build of GunZ: The Duel as of November 2026. Masangsoft's Steam remaster, released on 13 August 2026,\[1\]\[2\] is the only build with official tournaments. Veteran players still point to Freestyle GunZ and other private servers as the "authentic" game.\[3\] Almost every detailed technique description in circulation was written about the ijji-era international client (2006–2013), and no source found states frame counts for any cancel.

## TL;DR
- **Versions:** There are four layers: the original Korean service (2003, Netmarble); regional international releases (2006: ijji/NHN USA in North America, then Aeria Games from 2012 until closure on 31 May 2013, plus Level Up! in Brazil and India); private servers built on leaked 1.0 (around 2007) and 1.5 source (Freestyle GunZ, International GunZ, Refined GunZ, Dark GunZ and others); and Masangsoft's Steam remaster (13 Aug 2026). The netcode is the best-documented mechanical difference: official GunZ was peer-to-peer with "lead", while private servers and the remaster added "anti-lead" or server-side hit registration.
- **Styles:** K-Style (sword or kodachi cancels) and D-Style (dagger) are the two styles every source accepts. E-Style (gun-focused, "European" or "Evade") and M-Style ("Monk Style", later renamed "Divine Gates") are real names, but players dispute whether they are styles at all. "Monk style" is not a mishearing: it was named after a player called Monk. Gladiator is a melee-only subset of K-Style.
- **Inventory and gaps:** Every technique is a chain of a few cancel types: guard (block) cancel, switch cancel, slash cancel, reload cancel, jump cancel, wall-hang cancel and gravity cancel. Frame windows are Unquantified everywhere. The only numbers found are millisecond weapon delay values in leaked or community `zitem.xml` files, a 12-pellet shotgun count, and a 400 ms slash-shot figure from a 2016 Masangsoft test plan.

## 1. Versions

### 1.1 Build-by-build

**Original Korean service (MAIET / Netmarble, 2003 →)**
- **Who and when:** MAIET Entertainment developed the game and Netmarble published it in Korea. Wikipedia's infobox gives the Korean release as June 2003.\[4\] *(Single-source; Korean build.)*
- **Mechanics:** K-Style ("Korean Style") is said to be named after techniques that first developed in the Korean version.\[5\] *(Community consensus; Korean build.)* An alternative origin story is covered in §2.
- **Not found:** Any documented difference in movement, cancel timing, netcode or balance between the Korean build and the international builds. Searched StrategyWiki, Wikipedia and Fandom pages, GameFAQs, and private-server histories.

**International / regional releases (2006–2013)**
- **Dates and operators (Wikipedia):** NA and EU in November 2006, Brazil in July 2006 and India in June 2006. Publishers were Aeria Games (NA) and Level Up! Games (BR).\[4\] *(Single-source; regional builds.)*
- **ijji GunZ (NHN USA):** Closed beta ended on 17 Nov 2006 and the service went live on 29 Nov 2006 with clan wars and quest mode. The game moved to Aeria Games in March 2012. Aeria closed it on 31 May 2013.\[4\] *(Verified, based on Wikipedia plus the archived ijji and Aeria notices it cites; international build.)*
- **Other services:** A fan-maintained server history (relaying the GunZ Fandom list) also names International GunZ (MAIET), Japan (Netmarble) and Kaybo, all undated.\[6\] *(Single-source.)*\[7\]\[8\]
- **Netcode:** Most of the game ran peer-to-peer, with clients connecting to each other rather than to a central server.\[4\]\[9\] *(Verified: Wikipedia, the Refined GunZ README and the APEX: The Duel server page all say so; official builds.)* A Steam user states that "none of the official GunZ 1 servers ever had anti-lead".\[10\] *(Single-source; official builds.)*
- **Not found:** Region-specific mechanical changes for Japan, Brazil, India or Europe.

**Leaked-source eras ("1.0" and "1.5")**
- Refined GunZ describes itself as "based on the leaked Gunz 1.0 source from around 2007".\[11\] *(Single-source; 1.0 builds.)*\[12\]
- A RaGEZONE poster says GunZ 1.5 source "was leaked here onto RaGEZONE" about a decade earlier, and that it was only the "Stable" branch of MAIET's repository.\[13\] *(Single-source.)*
- A server developer says 1.5 has "security fixes" but lower framerates because of how maps are drawn.\[14\] *(Single-source.)*
- **Not found:** Movement, cancel or balance differences between 1.0 and 1.5.

**Freestyle GunZ (FGunZ)**
- **Who and when:** The site claims "15+ years" of operation.\[15\] A fan site's server check on 2026-09-04 found clan-war results logged the same day. Its last "Game Update" post was dated 6 Nov 2024 and covered a new launcher, tickrate work and sniper changes.\[6\] *(Single-source; FGunZ.)*
- **Netcode:** A Steam user says FGunZ "uses anti-lead".\[10\] *(Single-source; FGunZ.)*
- **Content:** It is heavily customised, with extra maps, modes and weapons.\[6\]\[10\] *(Community consensus; FGunZ.)*
- **Not found:** FGunZ-specific cancel-timing changes.

**International GunZ (iGunZ)**
- **Who and when:** The site is active, with news posts dated 17 Apr, 23 Apr and 11 May 2025. Its live counter showed 0 players when checked.\[16\]
- **Spread:** On 17 Apr 2025 it switched shotgun spread to "completely static. There is no guaranteed bullet at the center". The stated reason was that the original spread "was extremely RNG".\[16\] *(Single-source; iGunZ.)*
- **Other changes:** In April 2025, input handling moved to its own thread and the server made "slight network adjustments". In May 2025, medkits were reverted to "healing 20 each".\[16\] *(Single-source; iGunZ.)*
- **Code lineage:** Its developers updated the Open GunZ source, which was forked from Refined GunZ.\[17\] *(Verified across two GitHub repositories; iGunZ/Open GunZ.)*\[18\]\[19\]

**Refined GunZ (developer "Crawly"/Asunaya; open-source; 1.0-based)**
- **Netcode:** It offers three modes:
  - Server-based, marked "unfinished", with lag compensation done on the server.
  - "Peer to Peer Antilead", where the attacker does immediate hit registration.
  - "Peer to Peer Lead", where the target does immediate hit registration.
- **Update rate:** The "basic info update rate per second" was raised from 10 to 33.
- **Other:** It includes "Gladiator changes" and can play back replays from official versions V4–V11, Freestyle GunZ V7–V10 and Dark GunZ V6.
- *(Single-source: the README, with a RaGEZONE mirror counting as the same source; Refined GunZ.)*\[7\]\[20\] The specific gladiator changes are Not found, because they sit on a page that requires login.

**Dark GunZ and Universe GunZ**
- Dark GunZ appears only as a replay format (V6) that Refined GunZ supports. *(Single-source.)*
- Universe GunZ appears on a server list as "a unique, online Third Person Shooter (TPS) similar to GunZ".\[21\] The GunZ Fandom list, as relayed by a fan site, warns about its operator.\[6\] *(Single-source.)*
- **Not found:** Mechanical changes for either server.

**Other active servers in 2026 (marketing pages, low reliability)**
- **APEX: The Duel** claims "server-validated PvP hits" with "bounded rewind based on measured ping" and "untouched K-Style". It was in closed beta on EU West.\[9\]
- **RealGunZ** advertises ranked duels, clan war and a Vulkan renderer.\[22\]\[23\]
- **Target GunZ** and **Streak GunZ** advertise ladders and tournaments.\[21\]\[24\]
- **M2O Gaming's "GunZ: The Last Duel"**, run by Monk, calls itself an "ijji-replica".\[21\]\[25\]
- *(Single-source each; server pages.)*

**Steam release / "GunZ: The Duel Remastered" (Masangsoft)**
- **Who:** Masangsoft acquired the rights to GunZ: The Duel and GunZ 2 in 2016.\[4\] *(Verified.)*
- **When:** The store page appeared in 2024 (Steam app 3139440).\[4\] Test phases:
  - Closed beta, 25–29 Sep 2025, PvP only.\[26\]
  - Second global playtest, 11–14 Dec 2025.\[27\]
  - A further playtest at Steam PvP Fest.
  - Fourth beta, concluded 12 May 2026.\[28\]
  - Final playtest, 22–26 Jul 2026.\[29\]
- **Launch:** Global launch on 13 Aug 2026 at 17:00 PDT, which is 14 Aug KST.\[30\] *(Verified, from the Steam store page, Masangsoft's press release and trade press.)* Wikipedia gives 14 August, which is the same moment in Korean time.\[4\]
- **Netcode:** The December 2025 playtest changelog lists "Improved tick rate", "anti-lead configuration (0–100)" and "smoother network performance".\[27\]\[31\]\[32\] *(Verified through the press release and two outlets.)* Before that, the game director had said anti-lead "would ensure that attackers see their shots register accurately on their screens" but might make players "feel they are hit even when they have successfully taken cover".\[33\] *(Verified.)* gunz-online.net ("Anti-Lead System Vote Results Are In", 22 Mar 2025) reports a community poll of 2,471 votes: "Yes, it's necessary – 1,369 votes (55%)", "It should be an option when creating a room – 985 votes (40%)" and "No, it's not necessary – 117 votes (5%)". *(Single-source.)*
- **Movement and animation:**
  - The December 2025 playtest removed the camera lock during wall running.\[27\]\[31\] *(Verified.)*
  - Masangsoft says the remaster preserves "the classic feel and controls".\[2\] *(Developer statement.)*
  - A 24 Aug 2026 patch fixed female dagger animations being interrupted when jump-attacking after a charged dagger attack. *(Single-source: a fan-site summary of patch notes.)*\[8\]
  - A Steam user review complains of "overhauling the animations to allow female models to yoyo with shotguns". *(Single-source; unverified.)*\[34\]
- **Weapon balance:** Two fan sites disagree. gunztheduel.online, which tracks the official patch notes, says that as of the 2026-09-01 notes "no patch has changed a weapon's damage, delay, spread or ammo". gunz.com.br's homepage says instead that "The relaunch removed pay-to-win and rebalanced every weapon". *(Disagreement, each Single-source; Steam.)* The 14 Sep 2026 patch addressed client stuttering and map issues. *(Single-source: the Steam news feed.)*\[34\]
- **Cancel timing:** No source found states that the remaster changed any cancel window. *(Not found; searched Steam patch notes, playtest changelogs and Masangsoft notices.)*

**GunZ 2: The Second Duel (MAIET, 2011 Korea beta; Steam 2014)**
- This is a separate sequel. It was meant to be closer to what the developers "originally planned" for the first game.\[4\] *(Single-source; GunZ 2.)*\[4\]
- TV Tropes says MAIET left K-Style in GunZ 1 and made it "an official feature" of GunZ 2.\[35\] *(Single-source.)*
- GunZ 2's later netcode change to anti-lead drew complaints about melee hitting "from 10 feet away".\[36\] *(Single-source; GunZ 2 only.)*

### 1.2 Which version is the competitive reference today?

The evidence conflicts:
- **For the Steam remaster:** Masangsoft ran Clan Battle Tournament Season 1 on its Triumph platform, with registration from 31 Aug to 7 Sep 2026.\[37\] *(Verified: Masangsoft board.)* gunz.com.br (1 Oct 2026) reports that Season 1 ended on 20 Sep and that "The first official GunZ: The Duel clan tournament ended with Expert beating Focus 2-0 in the final… The result is recorded on the company's own platform, but no announcement was ever published to players." *(Single-source.)* Season 2 was announced on 3–5 Nov 2026 and then postponed "until further notice" on 9 Nov 2026 for "additional technical reviews and improvements".\[37\]\[38\] *(Verified: Masangsoft board and Steam.)*
- **Against the Steam remaster:** A top-rated Steam review says players who want "a more authentic experience" are "better off just playing on one of the private servers like Freestyle or FxP GunZ".\[3\] *(Single-source.)* The remaster's all-time rating is "Mixed" (43% positive of 1,085 English reviews).\[1\] gunz.com.br's 1 Oct 2026 post reports "the player base fell 66%", with "An average of 353 concurrent players". Raijin.gg gives a separate figure for October 2026: 265 average daily players, a peak of 433, down 38.3%. *(Single-source each; the two trackers disagree.)*
- **Private-server activity:** FGunZ logs clan wars daily, and iGunZ publishes clan ladders.\[6\]\[16\] *(Single-source each.)*
- **Not found:** Any named 2025–2026 tournament on FGunZ, iGunZ, Duelists, APEX or RealGunZ, and any statement from a known top player naming a reference build.

**Reading of the evidence:** No version is settled. Because of that, the rest of this report uses the order the brief sets as a fallback: the original international (ijji) release first, then Steam. Most technique sources describe the ijji-era client in any case.

## 2. Play Styles

**K-Style**
- **Other names:** Korean Style; Katana Style.
- **Weapons:** Sword or kodachi, usually paired with two shotguns.\[39\]\[40\] *(Verified: StrategyWiki, Fandom, gunz.com.br; ijji era and Steam.)*
- **Core techniques:** Slash Shot, Half Step and Butterfly, built on slash cancelling.\[39\] *(Verified.)*
- **Purpose:** Cancelling animations into one another so the player keeps moving while landing slashes and shots. StrategyWiki calls the uncancelled game "slow paced and tedious".\[41\] *(Community consensus.)*
- **How common:** The dominant style, described as "arguably the most popular".\[35\] *(Community consensus.)*
- **Naming conflict:** Sources disagree on where the name comes from:
  - The Korean version of the game (StrategyWiki).\[5\]
  - "a player called Korean or something similar" (Fandom).\[42\]
  - A player called "Kraise (Korean)" (Monk's own forum guide).\[43\]

  Each origin story is single-source. The weapon-based backronym "Katana Style" also appears (Fandom).\[39\]
- **Sub-tiers:** StrategyWiki splits K-Style into "Normal", "Advanced" (relies on reload cancelling) and "Professional" (uses animation freeze and gravity cancelling).\[41\] *(Single-source.)*

**D-Style**
- **Other names:** Dagger Style.
- **Weapon:** Dagger, plus guns.
- **Core techniques:** Yo-yo dashing and swap cancelling. Fandom says it requires "several frame perfect inputs" but gives no numbers.\[39\] *(Verified as a style; the "frame perfect" claim is Single-source and Unquantified.)*
- **Purpose:** Rush mobility.
- **How common:** "Not as popular as K-Style".\[42\] *(Community consensus.)*
- **Relationship to K-Style:** One GameFAQs poster calls it "a branch of k-style", noting that sword users can do dagger techniques but daggers "cannot do common sword techniques".\[44\] *(Single-source.)*

**E-Style**
- **Other names:** European Style; Evade Style.\[42\]
- **Weapons:** Mostly guns (rifles, pistols, revolvers, grenades), with tumbling and aiming.\[5\]
- **Purpose:** Playing at range with tactics and positioning, like a conventional shooter.\[35\] *(Community consensus.)*
- **Disputed:** One GameFAQs poster says "E-style doesn't exist; it has no techniques".\[44\] Fandom says the "philosophy" view is "untrue".\[42\] The style is rare and has no defining techniques. *(Disagreement reported; ijji era.)*

**Gladiator**
- Fandom describes it as a "subdivision of k-style that solely focuses on melee combat",\[39\] tied to Gladiator rooms. *(Single-source; ijji era.)* Refined GunZ made unspecified "Gladiator changes". *(Single-source.)*

**M-Style ("Monk Style", later "Divine Gates")**
- **Real, not a mishearing.** It is named after a player called Monk.\[43\]\[45\]\[46\] *(Verified: a 2008 GameFAQs thread, a YouTube video titled "M-Style is a GunZ playstyle created by Monk", and Monk's 2020 forum guide.)*
- **Renamed:** A video titled "Monk Style Update" states it "is now called Divine Gates", with "Monk Style" kept only for Monk's own swordplay.\[47\] *(Single-source.)*
- **Mechanics:**
  - A set of K-Style sword techniques "that uses at least two equal keys", meaning remapped duplicate bindings.\[45\] *(Community consensus.)*
  - "Animation Freeze is only a feature of Monk Style".\[43\] *(Single-source: Monk's guide.)*
  - The YouTube description claims "as many as 10 hits per second".\[46\] *(Single-source; Unquantified beyond that claim.)*
  - Named techniques include "Turtle Gate".\[45\] *(Single-source.)*
- **Disputed:** One GameFAQs poster says "There is no M-style… simply uses remapped keys" and calls it useful only in gladiator.\[44\] Another says it gets flagged as cheating.\[48\] *(Disagreement reported; ijji era.)*

**Other named styles**
- **H-Style:** "Hybrid" (automatic weapons other than shotguns) or "Half Style".\[44\]\[49\] The style itself is Single-source and Disputed, and the "Half Style" reading is Single-source.
- **Y-style:** Name only.\[48\] *(Single-source.)*
- A 2026 Steam user post uses "KS/DS/ES/MS" as "the Four Great Styles". *(Single-source; Steam.)*\[8\]\[50\]

**Regional styles:** No solid evidence of lesser-known regional styles turned up in one focused pass. Searched for M-style, Monk style and E/H/Y-style threads, Brazilian and Vietnamese server guides, and style lists.

## 3. Inventory

### 3(a) Underlying systems

Unless noted, descriptions apply to the ijji-era international client.

- **Movement:**
  - Players can run on walls, flip off them, wall-hang, tumble (double-tap direction), dash in any horizontal direction in mid-air, and safefall after being launched.\[4\]\[41\] *(Verified: Wikipedia, StrategyWiki.)*
  - "Super Dash": after "roughly 1.5 seconds" of falling, the animation freezes and the player can dash indefinitely.\[41\] *(Single-source: StrategyWiki.)*
  - The Steam remaster removed the camera lock during wall runs.\[27\] *(Verified; Steam.)*
- **Animation cancelling:** StrategyWiki lists seven cancel types. Each is Single-source from StrategyWiki, with guard and switch cancelling corroborated by gunz.com.br and Fandom:
  - **Guard:** block cancels a slash at any point.\[41\]
  - **Switch:** a weapon switch cancels an air slash. A ground slash locks switching until it ends, according to gunz.com.br.\[51\]
  - **Slash:** a slash cancels the locked state of a wall jump or dash.\[41\]
  - **Reload:** tapping reload cancels the switch delay after firing.\[41\]
  - **Jump:** cancels the delay after a dash.\[41\]
  - **Wall-hang:** cancels the locked state after a wall run or wall jump.\[41\]
  - **Gravity:** a slash at the top of a jump or near landing "cancel[s] gravity", enabling a late or blind dash.\[41\]

  All windows are Unquantified.
- **Melee:**
  - Weapons are swords, kodachis and daggers. There is a ground combo, a charged Massive Strike, and a launch.
  - Kodachi combos are faster. Daggers stab and lunge and cannot block. *(Community consensus.)*
  - A Masangsoft-era comment in `zitem.xml` says melee delay values include the base attack animation length.\[52\] *(Single-source: a Refined GunZ repo copy.)*
  - A blog says a missed Massive Strike leaves the user immobile for "about 1.5 seconds".\[53\] *(Single-source; ijji era.)*
- **Blocking melee and bullets:**
  - Swords block bullets.\[4\] *(Verified: Wikipedia, multiple guides.)*
  - Blocking covers only the upper body, so shots to the feet get through. Flipping into a defender cancels their defence in the air.\[5\] *(Single-source: StrategyWiki.)*
  - Slashing into a blocker can trigger a "counter massive".\[53\] *(Single-source: a blog.)*
  - Rocket launchers are "unblockable". *(Single-source.)*
  - Blocking windows: Unquantified.
- **Ranged weapons:**
  - Classes are shotgun, revolver, pistol, SMG, rifle, machine gun, rocket launcher and grenade.\[5\] *(Verified.)*
  - Weapon delay values in milliseconds are in `zitem.xml`: shotguns 1000–1100 ms with a 3–5 round magazine, fast guns 80–95 ms, and an ijji-era dual pistol at 250 ms.\[52\]\[54\] *(Single-source: the Refined GunZ repo copy plus RaGEZONE; leaked and community data, not the Steam build.)*
  - Shotguns fire 12 pellets.\[55\] *(Verified, but only two independent sources: a fan-site tier list and a RaGEZONE code post.)*\[8\]
  - Original shotgun spread was random ("extremely RNG"), and iGunZ made it static in April 2025.\[16\] *(Single-source; iGunZ.)*
  - Spread angle values: Not found. Searched `zitem.xml` excerpts and spread-code posts.
- **Hit registration and netcode:**
  - Official builds were peer-to-peer with "lead": the target registers hits, so attackers must aim ahead. The GunZ Guide on GitBook ("Lead & Anti Lead") says players must predict an opponent's position "in approximately twice their ping in milliseconds… if a player has a ping of 100 milliseconds, they effectively exist '200 milliseconds in the future'". *(Verified for peer-to-peer and lead; the twice-ping figure is Single-source.)*
  - Private servers added anti-lead, where the attacker registers hits, or server-side lag compensation.\[9\]\[10\] *(Verified: Refined GunZ, APEX, a Steam thread.)*\[7\]
  - The Steam remaster has an anti-lead setting from 0 to 100 and an improved tick rate,\[27\] with the actual tick value Unquantified. *(Verified; Steam.)*

### 3(b) Named techniques

Descriptions apply to the ijji-era international client unless noted. Each line gives the input chain and a short gloss. Tags are listed after each technique. Timings are all Unquantified except where stated.

**K-Style, gun-related**

| Technique | What it is | Tag |
|---|---|---|
| Butterfly (BF) | Jump → dash → slash → block. The block cancels the slash, so you get repeated short slashes while moving and partly protected from bullets.\[41\]\[53\] The basis of many K-Style techniques.\[35\] | Verified (StrategyWiki, Fandom, blog, gunz.com.br) |
| Double Butterfly / "Dan Step" (DBF) | Jump → slash → block → dash → slash → block. Two butterflies in one jump.\[41\] | Verified (StrategyWiki, Fandom) |
| Triple / Quadruple Butterfly | Three or four slash-block pairs in one jump. StrategyWiki says the animation appears frozen in replays.\[41\]\[56\] | Single-source (Quadruple: Fandom) |
| Slash Shot (SS) | Jump → (dash) → slash → switch to gun → shot. The switch cancels an air slash.\[41\] Fans advise holding fire so the shot comes out as soon as it is allowed.\[51\] | Verified. A 2016 Masangsoft test plan cites a "400ms delay for shooting animation"\[57\] (Single-source; planned, not confirmed in any build) |
| Reload Shot (RS) | Shot → tap reload together with the switch to the second gun → shot. The reload cancels the post-shot switch delay.\[41\]\[58\] | Verified (StrategyWiki, blog, gunz.com.br, videos)\[58\]\[59\] |
| Reload Slash Shot (RSS) | A Slash Shot with a reload added at the end.\[58\]\[60\] | Verified (gunz.com.br, Strike GunZ academy, Freestyle video)\[58\]\[61\] |
| Swap Shot / Streaming | Alternate firing two high-delay guns. Also works with medkits.\[41\] | Verified |
| Half Step (HS) / Half Half Step (HHS) | A Slash Shot with a dash while the gun is out. HHS lands and jumps before the dash.\[41\] | Verified (StrategyWiki, Fandom) |
| Gear Tap / Reverse Half Steps | Variants with dash before jump.\[41\] | Single-source |
| Flash Step / Quick Slash | Jump → dash → slash → switch to gun → switch back to sword. Shortens the slash and gives more control over dash direction.\[41\] | Single-source |
| Light Step | Jump → slash → dash. Moves without the dash sound.\[41\] | Verified (StrategyWiki, gunz.com.br) |
| Forbidden Step | Two shots in one jump, with a dash in the second half.\[41\] | Verified (StrategyWiki, Fandom) |
| RHGT, DHS (Double Half Step), GDHS, PPQ / PPQ+, Double Slash Shot, Eighth Step, Wind Step, Stylish Step | Advanced multi-shot or multi-dash chains, several of which use gravity cancel. Several StrategyWiki entries are marked "To be continued".\[41\] | Single-source |
| Insta-kill | Launch → switch → shoot the airborne opponent.\[41\] | Single-source |
| Insta-fall | Launch → block → jump → slash.\[41\] | Single-source |
| Juggle | Repeated launches.\[41\] | Single-source |
| Sword Insta-kill / Butterfly Juggle | Butterfly or slashes from underneath a launched opponent.\[41\] | Single-source |
| Large Massive / Gun Massive | Visual or hidden Massive Strike via switch timing.\[41\] | Single-source |

**K-Style, movement**

| Technique | What it is | Tag |
|---|---|---|
| Wall Climb / Flying / Slash Climb / Wall Cancel | Jump → dash into wall → jump → slash. The slash cancels the wall-flip lock so you can scale walls.\[41\] | Verified (StrategyWiki, Fandom) |
| Quick Slash Climb / Flash Climb | A faster version of wall climbing using weapon switches.\[41\] | Single-source |
| Wall Spring / Propel | Flip off a wall immediately to gain forward momentum.\[41\] | Single-source |
| Multi-Wall Run | A wall run started in mid-air.\[41\] | Single-source |
| Wall Post | Umbrella term for wall-climbing variants.\[41\] | Single-source |
| Silent Jump | Jumping without the jump sound to sneak up on opponents.\[41\] | Single-source |
| Switch Walk | Walking silently while spamming gun switches.\[41\] | Single-source |
| Sliding | Block at the end of a slash so the character slides instead of walking.\[41\] | Single-source |
| Dash Break | Cancel a dash halfway and change direction.\[41\] | Single-source |
| Super Dash | See §3(a). | Single-source |

**K-Style, melee and Gladiator**

| Technique | What it is | Tag |
|---|---|---|
| Double/Triple Slash | Slash → slash → block, which shortens the gap between ground slashes. Stronger with kodachi.\[41\] | Single-source |
| "Bladestorming" | Butterfly-based sword variant attributed to one player.\[41\] | Single-source |

**D-Style**

| Technique | What it is | Tag |
|---|---|---|
| Yo-yo / Yoyo Hop / YoYo Step | Jump and switch to gun at the same moment → dash with the gun out → shot (→ reload). Gender-specific: "Blink Step" is the version female characters can use.\[62\]\[63\] | Verified (GameFAQs Dagger FAQ, Neoseeker, wikifoundry, Fandom). Steam animation change unverified (one review) |
| YoYo Half / Quarter / Dash / Reload | Yo-yo extended with extra dagger dash-stab pairs or a second shot.\[62\]\[63\] | Single-source/Community consensus (wikifoundry, Neoseeker) |
| Dagger Flash | Jump → dash → stab → dash → stab.\[64\] | Single-source (GameFAQs FAQ) |
| Dagger Machine | Listed only by name. | Single-source (GameFAQs FAQ) |
| Dagger Gatling | Listed only by name. | Single-source (GameFAQs FAQ) |
| Massive Dash | Listed only by name. | Single-source (GameFAQs FAQ) |
| Dagger Hop | Listed only by name. | Single-source (GameFAQs FAQ) |
| Wall Stabbing | Jump → stab → dash back to the wall.\[64\] | Single-source |
| Wall Raid | Keep a wall run going by stabbing → jumping.\[62\]\[64\] | Verified (GameFAQs FAQ, Neoseeker) |
| Wall Strike | Climb a wall quickly with jump-off → stab → dash.\[65\] | Single-source |
| Block Tap | Used against blockers.\[62\] | Single-source |

**M-Style**

| Technique | What it is | Tag |
|---|---|---|
| Turtle Gate; Animation Freeze | Listed by name only. | Single-source (GameFAQs quote of the guide; Monk forum) |

## 4. Footage

Descriptions below use only the video titles and descriptions. Timestamps appear only where the description gives them.

- **Butterfly / Slash Shot / Reload Shot overview:**
  - "The 3 Basic K-Style Gunz Moves You Need To Get Started In 2023!": https://www.youtube.com/watch?v=bRr3DaKFoCE. Timestamps from the description: Intro 0:00, Butterfly 0:51, Slash Shot 1:54, Reload Shot 3:00.\[66\]
- **Butterfly:**
  - "Gunz: The Duel - ButterFly (BF) tutorial": https://www.youtube.com/watch?v=ZTqAgywa2tA \[67\]
  - "ijji Gunz Butterfly Tutorial": https://www.youtube.com/watch?v=3afmrNTdAvM \[68\]
  - "Gunz K-style tutorial - Butterfly": https://www.youtube.com/watch?v=OQQeaHl3EwI \[69\]
  - "How to butterfly in gunz": https://www.youtube.com/watch?v=B0w1omeTTD4 \[70\]
  - "Gunz Online How to butterfly": https://www.youtube.com/watch?v=NVtHKPU_Q4U \[71\]
  - "GunZ The Duel Butterfly (BF) Tutorial under 15 seconds": https://www.youtube.com/shorts/V78_XeJRTro \[72\]
  - "GunZ 2 Butterfly Tutorial": https://www.youtube.com/watch?v=BTnmXpDb7Xc. This is GunZ 2 only.\[73\]\[74\]
- **Triple Butterfly:**
  - "GunZ The Duel Triple Butterfly Tutorial (TBF) under 30 seconds": https://www.youtube.com/watch?v=_75kuCcNOhw \[75\]
- **Reload Shot:**
  - "GunZ The Duel: K-Style l Reload Shot Tutorial": https://www.youtube.com/watch?v=FCOPgeLkt38 \[76\]
  - "GunZ: Reload Shot Tutorial": https://www.youtube.com/watch?v=iDWMQbUJLfc. The description says it was recorded on International GunZ, player Kronica.\[77\]
  - "GunZ KStyle - #6. Reload Shot (RS)": https://www.youtube.com/watch?v=_MrJ29WNI20 \[59\]
  - "Gunz Amateur Kstyle Tutorial: Reload shot": https://www.youtube.com/watch?v=tMe1oBGa6pw \[78\]
- **Reload Slash Shot:**
  - "Reload Slash Shot (RSS) Tutorial by Helyom": https://www.youtube.com/watch?v=uF3yc44BoKk. The description says it was recorded on Freestyle GunZ, with the sequence Jump-Dash-Slash-Shotgun-Shoot-Reload-Sword.\[61\]
- **M-Style:**
  - "GunZ: M-Style - Demonstrated by Monk, the master himself": https://www.youtube.com/watch?v=ao1rTYocVj8 \[46\]
  - "GunZ Online - Monk Style Update": https://www.youtube.com/watch?v=wUH2rvt408Y \[47\]
- **Netcode (anti-lead):**
  - "Important Steam GunZ Update": https://www.youtube.com/watch?v=scftd4u6vDM. The description says it covers the developer's anti-lead update.\[79\]
- **Competitive play (Steam):**
  - "GunZ Remastered Clan War Tournament — First Round Matches": https://www.youtube.com/watch?v=ijDUc45wDMA \[80\]
- **Not found (search budget):** Videos covering D-Style or yo-yo, Half Step, Wall Climb and the other advanced steps. gunz.com.br says its guides link a timestamped community video,\[58\] but the URL was not retrievable.

## Caveats
- Almost every technique description comes from fan wikis and forum posts written 2006–2010. They often copy each other, so StrategyWiki and Fandom input chains may share a single origin.
- No source gives frame data. Every cancel window should be treated as Unquantified.
- The `zitem.xml` delay values come from leaked or community copies and may not match the ijji live build or the Steam build.
- The gunz-the-duel.wiki pages were excluded because they read as speculation written before launch. Server pages are marketing and are tagged as low reliability.

## Source table

| Title / URL | Type | Version described | Used for |
|---|---|---|---|
| GunZ: The Duel (Wikipedia), https://en.wikipedia.org/wiki/GunZ:_The_Duel | wiki | Korean, ijji/Aeria, Steam | Release dates, publishers, peer-to-peer netcode, closure |
| GunZ 2 (Wikipedia), https://en.wikipedia.org/wiki/GunZ_2 | wiki | GunZ 2 | Sequel context |
| Ijji (Wikipedia), https://en.wikipedia.org/wiki/Ijji | wiki | ijji | Transfer to Aeria |
| GunZ: The Duel on Steam, https://store.steampowered.com/app/3139440/GunZ_The_Duel/ | developer | Steam | Release date, rating |
| SteamDB app 3139440, https://steamdb.info/app/3139440/ | server page/database | Steam | Developer, anti-cheat |
| Masangsoft board, https://gz.masanggames.com/board | developer | Steam | Clan Battle Tournament Season 1 and 2, postponement |
| Masangsoft site, https://gz.masanggames.com/ | developer | Steam | Launch notice dates |
| Steam Community hub, https://steamcommunity.com/app/3139440 | developer/forum | Steam | Postponement text, user comment |
| Steam hub (curator view), https://steamcommunity.com/app/3139440/?curator_clanid=4777282 | developer/forum | Steam | 14 Sep 2026 patch notes, review on yo-yo animation |
| Steam reviews, https://steamcommunity.com/app/3139440/reviews/?browsefilter=toprated | forum | Steam vs private | "Freestyle or FxP" authenticity statement |
| Steam discussion "Controversial Changes…", https://steamcommunity.com/app/3139440/discussions/0/580555797815193054/ | forum | Steam | "Four Great Styles" naming |
| Games Press – launch, https://www.gamespress.com/en-US/Legendary-Action-Shooter-GunZ-The-Duel-Returns-Launching-Globally-on-S | developer | Steam | Launch time, features |
| Games Press – CBT, https://www.gamespress.com/en-US/Masangsoft-Launches-Closed-Beta-Test-for-GunZ-The-Duel | developer | Steam | CBT dates, PvP-only |
| Games Press – second playtest, https://www.gamespress.com/GunZ-The-Duel-Announces-Second-Global-Playtest | developer | Steam | Tick rate, anti-lead 0–100, wall-run camera |
| COGconnected (launch), https://cogconnected.com/2026/08/gunz-the-duel-makes-a-legendary-comeback-with-its-worldwide-steam-release/ | news | Steam | Launch corroboration |
| COGconnected (CBT), https://cogconnected.com/2025/09/gunz-the-duel-is-launching-a-closed-beta-test-on-steam-this-month/ | news | Steam | CBT corroboration |
| COGconnected (playtest 2), https://cogconnected.com/2025/12/gunz-the-duel-is-launching-its-second-playtest-next-week/ | news | Steam | Changelog corroboration |
| Pinoygamer, https://pinoygamer.ph/articles/classic-third-person-shooter-game-gunz-the-duel-is-set-to-begin-its-second-global-playtest-on-december-11.27024/ | news | Steam | Changelog corroboration |
| MassivelyOP, https://massivelyop.com/2026/08/16/2003-era-korean-shooter-gunz-the-duel-once-again-returns-to-steam/ | news | Steam | Launch date |
| PinoyTechSaga, https://pinoytechsaga.blogspot.com/2025/01/gunz-new-updates-steam-release.html | news/blog | Steam | Director's anti-lead statement |
| gunz-online.net vote results, https://gunz-online.net/gunz-the-duel-anti-lead-system-vote-results-are-in/ | guide/fan news | Steam | Anti-lead poll figures |
| gunztheduel.online private servers, https://gunztheduel.online/guides/private-servers/ | guide | Private and Steam | Server checks, official service history |
| gunztheduel.online tier list, https://gunztheduel.online/tier-list/ | guide | Classic and Steam | Patch timeline, 12 pellets, block and cancel matrix |
| gunz.com.br K-Style basics, https://gunz.com.br/en/guides/k-style-basics/ | guide | Steam | BF, SS, RS overview |
| gunz.com.br Slash Shot, https://gunz.com.br/en/guides/slash-shot/ | guide | Steam | Ground switch lock, held-fire SS |
| gunz.com.br Reload Shot, https://gunz.com.br/en/guides/reload-shot/ | guide | Steam | RS timing correction, RSS |
| gunz.com.br home, https://gunz.com.br/en/ | guide/fan news | Steam | Season 1 result, player decline |
| StrategyWiki K-Style, https://strategywiki.org/wiki/GunZ_The_Duel/Korean-Style_and_Advanced_Techniques | wiki | ijji era | Cancel types, technique list |
| StrategyWiki Gameplay, https://strategywiki.org/wiki/GunZ_The_Duel/Gameplay | wiki | ijji era | Style definitions, block limits |
| GunZ Fandom Tutorials, https://gunz.fandom.com/wiki/Tutorials | wiki | ijji era | K/D/Gladiator taxonomy |
| GunZ Fandom K-Style, https://gunz.fandom.com/wiki/K-Style | wiki | ijji era | Technique inputs |
| GunZ Fandom Game Terms, https://gunz.fandom.com/wiki/Game_Terms | wiki | ijji era | Style names, Evade Style |
| TV Tropes GunZ, https://tvtropes.org/pmwiki/pmwiki.php/VideoGame/GunZ | wiki | ijji / GunZ 2 | Style summaries, GunZ 2 adoption of K-Style |
| Gunz Tips and Tricks blog, http://gunztipsandtricks.blogspot.com/2009/02/gunz-k-style-moves.html | guide | ijji era | BF, SS, RS, Massive recovery |
| Strike GunZ Academy, https://strikegunz.com/academy | server page | Private | Technique list (RSS, TBF) |
| RealGunZ K-Style guide, https://realgunz.net/guides/gunz-kstyle | server page | Private | Low-reliability ping claims |
| RealGunZ wiki page, https://realgunz.net/guides/gunz-the-duel-wikipedia | server page | Private | D-Style technique names |
| GameFAQs Dagger FAQ, https://gamefaqs.gamespot.com/pc/928753-gunz-the-duel/faqs/40434 | guide | ijji era | D-Style technique list |
| Neoseeker D-Style list, https://www.neoseeker.com/forums/25603/t908757-style-training-moves-list/ | forum | ijji era | Yoyo, Wall Raid, Block Tap |
| wikifoundry GunZ D-Style, http://gunzwiki.wikifoundry.com/page/GunZ+D-Style | wiki | ijji era | YoYo, Blink Step |
| wikifoundry Advanced Dstyle, http://gunzwiki.wikifoundry.com/page/Advanced+Dstyle+Guide | wiki | ijji era | Wall Strike |
| wikifoundry Cysote's guide, http://gunzwiki.wikifoundry.com/page/Cysote's+Tactical+Dstyle+Guide | wiki | ijji era | Wall yo-yo |
| GameFAQs "Different Styles?", https://gamefaqs.gamespot.com/boards/928753-gunz-the-duel/42562078 | forum | ijji era | M/E/H-style disputes |
| GameFAQs "What is this M-style?", https://gamefaqs.gamespot.com/boards/928753-gunz-the-duel/41704022 | forum | ijji era | Monk Style definition |
| GameFAQs "E-Style > K-Style", https://gamefaqs.gamespot.com/boards/928753-gunz-the-duel/47052284 | forum | ijji era | E-style, H-Style "Half Style" |
| Monk's M-Style guide, https://forum.gunzduels.com/index.php?/topic/13-official-m-style-divine-gates-guide-released-after-a-long-13-years-of-gunz-history/ | forum | M2O / ijji era | Monk Style origin, animation freeze |
| YouTube M-Style by Monk, https://www.youtube.com/watch?v=ao1rTYocVj8 | video | ijji era | M-Style creator |
| YouTube Monk Style Update, https://www.youtube.com/watch?v=wUH2rvt408Y | video | — | Divine Gates rename |
| GunZ GitBook Lead & Anti Lead, https://gunz.gitbook.io/gunz-guide/how-to-play-gunz/combat-guide/lead-and-anti-lead | guide | Private/general | Lead explanation |
| Steam GunZ 2 "Is Anti-Lead an option?", https://steamcommunity.com/app/242720/discussions/0/558749190684404879/ | forum | Official GunZ 1, FGunZ | No anti-lead on official servers; FGunZ anti-lead |
| Steam GunZ 2 anti-lead thread, https://steamcommunity.com/app/242720/discussions/0/558756256326321895/ | forum | GunZ 2 | GunZ 2 anti-lead melee complaints |
| Steam GunZ 2 M2O thread, https://steamcommunity.com/app/242720/discussions/0/350540973999036596/ | forum | M2O, FGunZ | "ijji-replica" claim, Freestyle opinion |
| Steam GunZ 2 Naver translation, https://steamcommunity.com/app/242720/discussions/0/458605578276300996 | forum | 2016 Masangsoft plan | 400 ms slash-shot figure |
| International GunZ home, https://igunz.net/ | server page | iGunZ | Static spread, medkits, input thread |
| Freestyle GunZ, https://fgunz.net/ | server page | FGunZ | Operating claim |
| APEX: The Duel, https://playapextheduel.com/ | server page | APEX | Server-validated hits claim |
| RealGunZ home, https://realgunz.net/ | server page | RealGunZ | Feature claims |
| Ranked Private Servers list, https://rankedprivateservers.com/category/gunz-the-duel-private-servers | server page | Various | Active server names |
| private-server.ws list, https://private-server.ws/top100/Gunz-Online/ | server page | Various | Universe GunZ description |
| Refined GunZ README, https://github.com/Asunaya/refinedgunz | developer (fan) | Refined GunZ (1.0) | Netcode modes, update rate, replay formats |
| Refined GunZ zitem.xml, https://github.com/Asunaya/RefinedGunz/blob/master/Gunz/XML/zitem.xml | developer (leaked data) | 1.0-era | Weapon delay values in ms |
| RaGEZONE Refined GunZ release, https://forum.ragezone.com/threads/release-refined-gunz-source-public-git-2007-source.1153415/ | forum | Refined GunZ | Mirror of README (same source) |
| Open GunZ source, https://github.com/open-gunz/ogz-source | developer (fan) | Open GunZ / iGunZ | Lineage |
| interlunar source, https://github.com/interlunar/source | developer (fan) | Open GunZ / iGunZ | Lineage corroboration |
| RaGEZONE 1.5 source repo, https://forum.ragezone.com/threads/gunz-1-5-complete-source-repo.1200915/ | forum | 1.5 | 1.5 leak history |
| RaGEZONE 2007 files, https://forum.ragezone.com/threads/2007-gunz-files.1022360/ | forum | 1.0 vs 1.5 | Security and framerate comparison |
| RaGEZONE static spread code, https://forum.ragezone.com/threads/sword-reload-fix-multimonitor-bug-fix-basic-and-crappy-static-spread-code.1225677/ | forum | 1.5 community | 12-pellet shotgun constant |
| RaGEZONE item IDs, https://forum.ragezone.com/f1043/id-items-gunz-705895/ | forum | ijji-era data | Dual pistol and shotgun delay values |
| WhyWolfie GunZ-The-Duel README, https://github.com/WhyWolfie/GunZ-The-Duel | developer (fan) | Various | Server and source lists |
| YouTube 3 Basic K-Style Moves, https://www.youtube.com/watch?v=bRr3DaKFoCE | video | Private/ijji-style | Timestamped BF/SS/RS |
| YouTube BF tutorial, https://www.youtube.com/watch?v=ZTqAgywa2tA | video | — | Butterfly footage |
| YouTube ijji BF, https://www.youtube.com/watch?v=3afmrNTdAvM | video | ijji | Butterfly footage |
| YouTube K-style BF, https://www.youtube.com/watch?v=OQQeaHl3EwI | video | — | Butterfly footage |
| YouTube How to BF, https://www.youtube.com/watch?v=B0w1omeTTD4 | video | — | Butterfly footage |
| YouTube Gunz Online BF, https://www.youtube.com/watch?v=NVtHKPU_Q4U | video | — | Butterfly footage |
| YouTube BF short, https://www.youtube.com/shorts/V78_XeJRTro | video | — | Butterfly footage |
| YouTube TBF short, https://www.youtube.com/watch?v=_75kuCcNOhw | video | — | Triple Butterfly footage |
| YouTube GunZ 2 BF, https://www.youtube.com/watch?v=BTnmXpDb7Xc | video | GunZ 2 | GunZ 2 butterfly |
| YouTube RS tutorial, https://www.youtube.com/watch?v=FCOPgeLkt38 | video | — | Reload Shot footage |
| YouTube RS Kronica, https://www.youtube.com/watch?v=iDWMQbUJLfc | video | iGunZ | Reload Shot footage |
| YouTube KStyle #6 RS, https://www.youtube.com/watch?v=_MrJ29WNI20 | video | — | Reload Shot footage |
| YouTube Amateur RS, https://www.youtube.com/watch?v=tMe1oBGa6pw | video | — | Reload Shot footage |
| YouTube RSS Helyom, https://www.youtube.com/watch?v=uF3yc44BoKk | video | FGunZ | RSS footage |
| YouTube Important Steam GunZ Update, https://www.youtube.com/watch?v=scftd4u6vDM | video | Steam | Anti-lead news |
| YouTube Clan War Tournament, https://www.youtube.com/watch?v=ijDUc45wDMA | video | Steam | Competitive footage |

## Sources

1. [GunZ: The Duel on Steam](https://store.steampowered.com/app/3139440/GunZ_The_Duel/)
2. [2003-era Korean shooter GunZ: The Duel once again returns to Steam](https://massivelyop.com/2026/08/16/2003-era-korean-shooter-gunz-the-duel-once-again-returns-to-steam/)
3. [Steam Community :: GunZ: The Duel](https://steamcommunity.com/app/3139440/reviews/?browsefilter=toprated)
4. [GunZ: The Duel](https://en.wikipedia.org/wiki/GunZ:_The_Duel)
5. [GunZ The Duel/Gameplay — StrategyWiki](https://strategywiki.org/wiki/GunZ_The_Duel/Gameplay)
6. [GunZ Private Servers in 2026: FGunZ, iGunZ, RealGunZ & the Steam Remaster Compared | GunZ Duel Guide](https://gunztheduel.online/guides/private-servers/)
7. [GitHub - Asunaya/RefinedGunz · GitHub](https://github.com/Asunaya/refinedgunz)
8. [GunZ: The Duel Class Tier List (2026) | GunZ Duel Guide](https://gunztheduel.online/tier-list/)
9. [APEX: The Duel — GunZ Private Server 2026](https://playapextheduel.com/)
10. [Is Anti-Lead an option? :: GunZ 2: The Second Duel General Discussions](https://steamcommunity.com/app/242720/discussions/0/558749190684404879/)
11. [GitHub - Asunaya/RefinedGunz](https://github.com/Asunaya/RefinedGunz)
12. [Gunz Server And Client Files](https://swebkeen.netlify.app/mcvdfbzsnvgkaojjbo/gunz-server-and-client-files)
13. [GunZ 1.5 Complete Source Repo](https://forum.ragezone.com/threads/gunz-1-5-complete-source-repo.1200915/)
14. [2007 GunZ Files](https://forum.ragezone.com/threads/2007-gunz-files.1022360/)
15. [Freestyle GunZ - The Duel](https://fgunz.net/)
16. [Home](https://igunz.net/)
17. [GitHub - fxpgunz/gunz-1.0: An attempt to fixes the programmers sin's in Gunz1.0 Spaghetti code. Fixing security horrors and numerous RCE · GitHub](https://github.com/fxpgunz/gunz-1.0)
18. [GitHub - interlunar/source: Open GunZ source · GitHub](https://github.com/interlunar/source)
19. [GitHub - open-gunz/ogz-source: Open GunZ source · GitHub](https://github.com/open-gunz/ogz-source)
20. [\[RELEASE\] Refined GunZ Source - Public Git - 2007 source](https://forum.ragezone.com/f245/release-refined-gunz-source-public-1153415/)
21. [Best Gunz Online Private Servers 2026](https://private-server.ws/top100/Gunz-Online/)
22. [Most Popular Active Private Servers for Playing GunZ 2026](https://realgunz.net/guides/most-popular-active-private-servers-gunz-realgunz)
23. [Real GunZ 3](https://realgunz.net/)
24. [Gunz The Duel Top 100 Private Servers List](https://arenatop100.com/categories/gunz-private-servers)
25. [GunZ 2: The Second Duel](https://steamcommunity.com/app/242720/discussions/0/350540973999036596/?l=tchinese)
26. ["Masangsoft Launches Closed Beta Test for GunZ: The Duel" - Games Press](https://www.gamespress.com/en-US/Masangsoft-Launches-Closed-Beta-Test-for-GunZ-The-Duel)
27. ["GunZ: The Duel Announces Second Global Playtest" - Games Press](https://www.gamespress.com/GunZ-The-Duel-Announces-Second-Global-Playtest)
28. [Fourth Beta Test — Conclusion & What's Next — GunZ The Duel Wiki](https://gunz-the-duel.wiki/updates/fourth-beta/)
29. [Final Pre-Launch Playtest — July 2026 — GunZ The Duel Wiki](https://gunz-the-duel.wiki/updates/final-playtest/)
30. ["Legendary Action Shooter GunZ: The Duel Returns, Launching Globally on Steam August 13" - Games Press](https://www.gamespress.com/en-US/Legendary-Action-Shooter-GunZ-The-Duel-Returns-Launching-Globally-on-S)
31. [GunZ: The Duel Is Launching Its Second Playtest Next Week - COGconnected](https://cogconnected.com/2025/12/gunz-the-duel-is-launching-its-second-playtest-next-week/)
32. [Classic third-person shooter game GunZ: The Duel, is set to begin its second global playtest on December 11](https://pinoygamer.ph/articles/classic-third-person-shooter-game-gunz-the-duel-is-set-to-begin-its-second-global-playtest-on-december-11.27024/)
33. [GunZ dev unveils new updates prior to its Steam release](https://pinoytechsaga.blogspot.com/2025/01/gunz-new-updates-steam-release.html)
34. [Steam Community :: GunZ: The Duel](https://steamcommunity.com/app/3139440/?curator_clanid=4777282)
35. [GunZ (Video Game) - TV Tropes](https://tvtropes.org/pmwiki/pmwiki.php/VideoGame/GunZ)
36. [GunZ 2: The Second Duel](https://steamcommunity.com/app/242720/discussions/0/558756256326321895/?l=italian)
37. [GunZ: The Duel](https://gz.masanggames.com/board)
38. [Steam Community :: GunZ: The Duel](https://steamcommunity.com/app/3139440)
39. [Tutorials](https://gunz.fandom.com/wiki/Tutorials)
40. [GunZ: The Duel Relaunch - Complete Beginner's Guide - GamesFuze](https://gamesfuze.com/guides/gunz-the-duel-relaunch-complete-beginners-guide/)
41. [GunZ The Duel/Korean-Style and Advanced Techniques — StrategyWiki](https://strategywiki.org/wiki/GunZ_The_Duel/Korean-Style_and_Advanced_Techniques)
42. [Game Terms](https://gunz.fandom.com/wiki/Game_Terms)
43. [Official M-Style (Divine Gates) Guide Released after a long 13 Years of GunZ History! - Game Guide/And Style Discussions - GunZ : The Duel - Forum M2O Gaming Network](https://forum.gunzduels.com/index.php?/topic/13-official-m-style-divine-gates-guide-released-after-a-long-13-years-of-gunz-history/)
44. [Different Styles? - GunZ The Duel](https://gamefaqs.gamespot.com/boards/928753-gunz-the-duel/42562078?page=1)
45. [What is this M-style? New bunch of glitches for gameplay? - GunZ The Duel](https://gamefaqs.gamespot.com/boards/928753-gunz-the-duel/41704022)
46. [GunZ: M-Style - Demonstrated by Monk, the master himself. TanukichiTV.Com - YouTube](https://www.youtube.com/watch?v=ao1rTYocVj8)
47. [GunZ Online - Monk Style Update - YouTube](https://www.youtube.com/watch?v=wUH2rvt408Y)
48. [Different Styles? - GunZ The Duel - GameFAQs](https://gamefaqs.gamespot.com/boards/928753-gunz-the-duel/42562078)
49. [E-Style \> K-Style - GunZ The Duel - GameFAQs](https://gamefaqs.gamespot.com/boards/928753-gunz-the-duel/47052284)
50. [Controversial Changes I'd make so GunZ stands the Test of Time :: GunZ: The Duel General Discussions](https://steamcommunity.com/app/3139440/discussions/0/580555797815193054/)
51. [Slash Shot (SS): sword and shotgun in one motion — GunZ Brasil](https://gunz.com.br/en/guides/slash-shot/)
52. [RefinedGunz/Gunz/XML/zitem.xml at master · Asunaya/RefinedGunz · GitHub](https://github.com/Asunaya/RefinedGunz/blob/master/Gunz/XML/zitem.xml)
53. [Gunz Tips and Tricks: GunZ K-Style Moves](http://gunztipsandtricks.blogspot.com/2009/02/gunz-k-style-moves.html)
54. [ID items gunz? - RaGEZONE - The OG MMO development community](https://forum.ragezone.com/f1043/id-items-gunz-705895/)
55. [Sword Reload Fix, Multimonitor bug fix, Basic and crappy static spread code](https://forum.ragezone.com/threads/sword-reload-fix-multimonitor-bug-fix-basic-and-crappy-static-spread-code.1225677/)
56. [K-Style](https://gunz.fandom.com/wiki/K-Style)
57. [GunZ 2: The Second Duel](https://steamcommunity.com/app/242720/discussions/0/458605578276300996?l=spanish)
58. [Reload Shot (RS): two shots in the time of one — GunZ Brasil](https://gunz.com.br/en/guides/reload-shot/)
59. [GunZ KStyle - #6. Reload Shot (RS) - YouTube](https://www.youtube.com/watch?v=_MrJ29WNI20)
60. [GunZ Academy — K-Style Moves Tutorial](https://strikegunz.com/academy)
61. [Reload Slash Shot (RSS) Tutorial by Helyom - YouTube](https://www.youtube.com/watch?v=uF3yc44BoKk)
62. [D-Style Training / Moves List. - Gunz: The Duel Forum - Neoseeker Forums](https://www.neoseeker.com/forums/25603/t908757-style-training-moves-list/)
63. [GunZ D-Style](http://gunzwiki.wikifoundry.com/page/GunZ+D-Style)
64. [GunZ The Duel - Dagger FAQ - PC - By ParadigmShift89 - GameFAQs](https://gamefaqs.gamespot.com/pc/928753-gunz-the-duel/faqs/40434)
65. [Advanced Dstyle Guide](http://gunzwiki.wikifoundry.com/page/Advanced+Dstyle+Guide)
66. [The 3 Basic K-Style Gunz Moves You Need To Get Started In 2023! - YouTube](https://www.youtube.com/watch?v=bRr3DaKFoCE)
67. [Gunz: The Duel - ButterFly (BF) tutorial - YouTube](https://www.youtube.com/watch?v=ZTqAgywa2tA)
68. [ijji Gunz Butterfly Tutorial - YouTube](https://www.youtube.com/watch?v=3afmrNTdAvM)
69. [Gunz K-style tutorial - Butterfly](https://www.youtube.com/watch?v=OQQeaHl3EwI)
70. [How to butterfly in gunz - YouTube](https://www.youtube.com/watch?v=B0w1omeTTD4)
71. [Gunz Online How to butterfly - YouTube](https://www.youtube.com/watch?v=NVtHKPU_Q4U)
72. [GunZ The Duel Butterfly (BF) Tutorial under 15 seconds #gunztheduel #gunz #fyp #shorts - YouTube](https://www.youtube.com/shorts/V78_XeJRTro)
73. [GunZ 2 Butterfly Tutorial - YouTube](https://www.youtube.com/watch?v=BTnmXpDb7Xc)
74. [GunZ 2: The Second Duel](https://steamcommunity.com/app/242720/discussions/0/558748822642704242)
75. [GunZ The Duel Triple Butterfly Tutorial (TBF) under 30 seconds #gunz #gunztheduel #fyp #shorts - YouTube](https://www.youtube.com/watch?v=_75kuCcNOhw)
76. [GunZ The Duel: K-Style l Reload Shot Tutorial - YouTube](https://www.youtube.com/watch?v=FCOPgeLkt38)
77. [GunZ: Reload Shot Tutorial](https://www.youtube.com/watch?v=iDWMQbUJLfc)
78. [Gunz Amateur Kstyle Tutorial: Reload shot - YouTube](https://www.youtube.com/watch?v=tMe1oBGa6pw)
79. [Important Steam GunZ Update - YouTube](https://www.youtube.com/watch?v=scftd4u6vDM&pp=0gcJCfwAo7VqN5tD)
80. [GunZ Remastered Clan War Tournament — First Round Matches - YouTube](https://www.youtube.com/watch?v=ijDUc45wDMA)
