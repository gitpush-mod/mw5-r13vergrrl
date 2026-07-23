# R13verGrrl Voice Lines Recording Script

**Written 2026-07-23** from empirical ground truth extracted directly from PilotOverhaul's shipped `PilotQuirks.pak` — specifically `PO_Adder_DB.uasset` and its `.uexp` companion, which map every event slot MW5's engine fires to a `.wem` audio file with English caption text intact.

**Confidence level:** high. This is straight from a working shipping mod's Persona Dialogue Book (`MWDialogueBookAsset`), which is the exact wiring the game engine uses. Not inferred from filenames. Not guessed. The tag namespace, event slot names, and interruption/cooldown metadata are all confirmed against Adder's binary.

Prior versions of this script (v2, v3, v4) are archived in [`archive/`](archive/) as research artefacts.

---

## Two lore anchors that shape every line

1. **The cat is in the cockpit with her.** Not remembered — present. Cat meow ambience is canonical background wherever it fits. Where the script says `[cat's name]`, Nil substitutes her actual cat's name at record time. Chris will splice real meow layers in during post.
2. **Her canonical mech is a Marauder** — she prefers the old MAD. Player can swap her mech; the lore is that she's most at home with heavy autocannons and comfortable armor.

**Home planet lore:** Adder in PO references "Lothario" as her homeworld (see her Arctic and Forest banter). R13verGrrl's equivalent is up to Nil — anywhere on the frontier that reads Anatolian. Pick a name once and use it consistently across biome lines for continuity. Suggested: "Anatoli" (fictional frontier planet), or lean into a real BattleTech world with Turkish-adjacent culture. Nil's call.

**Personality:** strong-willed, warm, dry-humored, professional under pressure, occasionally clumsy, cares about the crew. Never bitter. Turkish and English mix as native — either can lead.

---

## How this script works

- **45 unique event slots** — every one MW5 fires for a pilot Persona, taken directly from `PO_Adder_DB`. Nothing extra, nothing missing.
- **Target: 2–3 variants per slot** — MW5 randomly picks one file per event fire; more variants = less repetition. Adder ships with anywhere from 1 to 10 variants per slot (median ~4); we're going lean for a v1.0 with fuller coverage in a future patch.
- **Total lines to record:** ~90–130 depending on how many variants she does per slot. Full session (~3–4 hours), or split across two days.
- **Filename convention:** `R13verGrrl_<Slot>_<N>.wav` where `<Slot>` is a short PascalCase key (e.g., `PilotHired`, `CmdAffirmMove`, `TakeDamageLArm`) and `<N>` is the variant number (`001`, `002`, `003`). T4 wiring maps these to MW5's title-case slot names.
- **Reference audio:** Adder's actual lines have been decoded to WAV and placed in `~/OneDrive/Desktop/R13vergrrl Lines/reference-adder-samples/`. Listen before recording adjacent slots — her delivery register (professional, warm, mercenary-grizzled) is a solid baseline. R13verGrrl reads *younger and warmer* than Adder but the same combat-veteran energy.

---

## Recording notes (unchanged from prior drafts)

- **Mic:** USB condenser or better
- **Environment:** quiet room, soft furnishings
- **Monitoring:** headphones (catch clicks, pops, sibilance)
- **Levels:** peaks −3 to −6 dBFS
- **Post:** Chris trims/normalises then applies radio-comm filter chain, then splices in cat meow layers where called for
- **Language mix:** English primary, Turkish flavor optional but strongly encouraged — 1 Turkish word/phrase per line where natural
- **Duration target:** 1.5–4 sec per line. Adder's are mostly 1–3 sec; keep it tight

---

## Tier 1 — Core mission arc (must-record, ~18 lines)

The moments the player will *definitely* hear every mission. Full personality on these.

### C1. Pilot Hired (`DialogueContext.CharacterDialogue.Pilot.Hired`)
**Trigger:** Player hires her at the hiring hall.  
**Slot name (T4 wire):** `Pilot Hired`  
**Adder ref (~3.2 sec):** "Glad to be aboard, Commander. You won't regret this."  
**Delivery:** Warm, confident, first-impression. Smile in the voice.  

- `PilotHired_001.wav`: "Hey, thanks for the offer. Ready when you are, Commander."
- `PilotHired_002.wav` (TR flavor): "Merhaba, Commander. Ready to work." *(merhaba = hello)*

---

### C2. Pilot Intro (`DialogueContext.CharacterDialogue.Pilot.Intro`)
**Trigger:** She boots up in the cockpit at mission start.  
**Slot name:** `Pilot Intro`  
**Adder ref (~2.5 sec):** "I just need a 'Mech and a target, Commander."  
**Delivery:** Task-focused, casual, in-cockpit voice.  

- `PilotIntro_001.wav`: "Systems green. Let's earn some C-Bills."
- `PilotIntro_002.wav`: "Marauder's warm. Ready to move, Commander."

---

### C3–C5. Pilot Announcement (`DialogueContext.???`)
**Trigger:** She reports in on-comms — used during scripted moments.  
**Slot name:** `Pilot Announcement 1/2/3`  
**Adder ref:** "Adder here." / "This is Adder." / "Adder reporting."  
**Delivery:** Crisp, radio-style call-sign. Under 1.5 sec each.

- `PilotAnnouncement_001.wav`: "R13ver here."
- `PilotAnnouncement_002.wav`: "This is R13ver."
- `PilotAnnouncement_003.wav`: "R13ver reporting in."

---

### C6–C8. Mission Intro (`DialogueContext.CharacterDialogue.Mission.Intro`)
**Trigger:** First line she speaks after the mission starts.  
**Slot name:** `Mission Intro 1..6` *(Adder has 6 variants — we'll do 3 for MVP)*  
**Adder refs:** "Starting mission time." / "Well, this should be a simple op." / "Check your sightlines and stay sharp." / "Grid's clear...so far, Commander." / "All systems online, let's go hunt them down Commander." / "R.O.E? Tch, I believe that's up to us, Commander."  
**Delivery:** Alert, ready. Slight variation per take — one focused, one slightly wry, one confident.

- `MissionIntro_001.wav`: "Alright, let's move out."
- `MissionIntro_002.wav`: "Grid looks clear. Stay sharp."
- `MissionIntro_003.wav` (dry): "Simple op, huh? Yeah, we'll see."

---

### C9. Spot Enemy — Generic (`DialogueContext.Spot.Enemy`)
**Trigger:** First hostile spotted (any type).  
**Slot name:** `Spot Enemy 1..5`  
**Adder refs:** "I have hostiles on radar." / "Hostiles detected." / "Contact!" / "Tangos on radar." / "Contact, enemy spotted."  
**Delivery:** Alert, flat-professional. Short.

- `SpotEnemy_001.wav`: "Contacts on radar."
- `SpotEnemy_002.wav`: "Tangos incoming."
- `SpotEnemy_003.wav` (Turkish): "Düşman!" *(Enemy!)*

---

### C10. Spot Enemy Mech (`DialogueContext.Spot.Enemy.Mech`)
**Trigger:** First enemy *mech* specifically.  
**Slot name:** `Spot Enemy Mech 1..7`  
**Adder refs:** "Enemy 'Mech ahead." / "Hostile 'Mech ahead." / "Heavy metal on radar." / "Heavy metal spotted." / "Contact! BattleMech!" / "Here we go, BattleMech spotted!" / "'Mech spotted!"  
**Delivery:** Weightier than generic contact — mech-on-mech is the real fight.

- `SpotEnemyMech_001.wav`: "Enemy mech ahead."
- `SpotEnemyMech_002.wav`: "Heavy metal! Big one, too."
- `SpotEnemyMech_003.wav`: "Mech contact — now it's a real fight."

---

### C11. Command Affirmative — Generic (`DialogueContext.Command.Affirmative`)
**Trigger:** Any player order not covered by a more specific ack.  
**Slot name:** `Command Affirmative 1..9`  
**Adder refs:** "Acknowledged." / "Roger." / "Affirmative." / "Order received." / "Wilco." / "Affirm." / "Copy that." / "Oscar Mike." / "On the move."  
**Delivery:** Crisp, professional. **Record 4 — she'll say these constantly, variety kills fatigue.**

- `CmdAffirm_001.wav`: "Copy that."
- `CmdAffirm_002.wav`: "Acknowledged."
- `CmdAffirm_003.wav`: "Roger."
- `CmdAffirm_004.wav` (Turkish): "Anladım." *(Understood.)*

---

### C12. Command Affirmative — Move (`DialogueContext.Command.Affirmative.Move`)
**Slot name:** `Command Affirmative Move 1..7`  
**Adder refs:** "En route to location." / "Heading to location." / "Moving to assigned position." / "Navigating." / (blank in bank) / "On my way." / "Moving."  

- `CmdAffirmMove_001.wav`: "On my way."
- `CmdAffirmMove_002.wav`: "Moving now."
- `CmdAffirmMove_003.wav` (TR): "Yoldayım." *(On my way.)*

---

### C13. Command Affirmative — Attack (`DialogueContext.Command.Affirmative.Attack`)
**Slot name:** `Command Affirmative Attack 1..9`  
**Adder refs:** "On your target." / "Copy target." / "Tango assigned." / "Targeted, on the move." / "Priority target received." / "Target ID received, moving in." / "Got your target." / "Focusing your target." / "Moving on your target."  
**Delivery:** Combat energy — she's already lining it up.

- `CmdAffirmAttack_001.wav`: "Engaging."
- `CmdAffirmAttack_002.wav`: "On your target."
- `CmdAffirmAttack_003.wav` (TR): "Saldırıyorum." *(Attacking.)*

---

### C14. Command Success — Move (`DialogueContext.Command.Success.Move`)
**Trigger:** She *arrives* at the waypoint (not just acks the order).  
**Slot name:** `Command Success Move 1..7`  
**Adder refs:** "Arrived at location." / "Holding at location." / "At the assigned location." / "At the waypoint." / "Holding at your waypoint." / "I'm at your designated position." / "Holding at nav point."  

- `CmdSuccessMove_001.wav`: "In position."
- `CmdSuccessMove_002.wav`: "At the waypoint, holding."

---

### C15. Take Damage — Destroy Component (Generic) (`DialogueContext.TakeDamage.Destroy.Component`)
**Trigger:** A component gets destroyed but no specific body-part slot is available.  
**Slot name:** `Take Damage Destroy Component 1..8`  
**Adder refs:** "Argh. Heavy hit, lost a component!" / "Armor at critical levels, lost a component!" / "Taking heavy damage!" / "I can't sustain damage like this much longer!" / "I'm under heavy fire!" / "Can't keep this up, I'm being torn to scrap here!" / "I'm being torn apart! Damage critical!" / "Mayday! Component lost! Need support here!"  
**Delivery:** Real vocal strain. Adder gets aggressive on these — Nil should too. **Record 3 with escalating severity.**

- `TakeDamage_001.wav`: "Taking heavy hits!"
- `TakeDamage_002.wav` (louder): "Argh! Lost a component!"
- `TakeDamage_003.wav` (strained): "I can't sustain this — need support!"

---

### C16. Kill Blow — Cheer (`DialogueContext.KillBlow.Cheer`)
**Trigger:** She destroys *any* enemy unit.  
**Slot name:** `Kill Blow Cheer 1..3`  
**Adder refs:** "Target destroyed." / "Enemy destroyed." / "Target is down."  
**Delivery:** Cool satisfaction. Under 2 sec. **Record 3 — high frequency.**

- `KillBlow_001.wav`: "Target down."
- `KillBlow_002.wav`: "Got them."
- `KillBlow_003.wav` (TR): "Bitti." *(Done.)*

---

### C17. Kill Blow — Mech Cheer (`DialogueContext.KillBlow.Mech.Cheer`)
**Trigger:** She specifically destroys an enemy *mech* (bigger deal than a vehicle).  
**Slot name:** `Kill Blow Mech Cheer 1..5`  
**Adder refs:** "Enemy 'Mech down." / "Enemy 'Mech destroyed." / "Tango down." / "Add another one to the pile." / "Scrub one."  
**Delivery:** Proud, mercenary-satisfied. Slight smirk.

- `KillBlowMech_001.wav`: "Enemy mech down!"
- `KillBlowMech_002.wav`: "Scratch one mech."
- `KillBlowMech_003.wav`: "That's another one on the pile."

---

### C18. Ejected — Critical (`DialogueContext.Ejected.Critical`)
**Trigger:** Mech critical, ejection sequence.  
**Slot name:** `Ejected Critical` *(single-variant in Adder)*  
**Adder ref (~1.6 sec):** "Damn, that was close!"  
**Delivery:** Sharp, adrenaline, still-alive relief.

- `EjectedCritical_001.wav`: "Punching out! That was close."

---

## Tier 2 — Full command range (~14 lines)

Lance orders MW5 fires when the player commands her. Without these she plays as mute during tactical direction — the most-noticeable gap for anyone who actually uses the lance UI.

### R1. Command Affirmative — Attack Lance (`DialogueContext.Command.Affirmative.Attack.Lance`)
**Slot name:** `Command Affirmative Attack Lance 1..10`  
**Adder refs (top 3):** "Coordinating attack strategy." / "Lance target received." / "Group target received."  

- `CmdAffirmAttackLance_001.wav`: "Lance target confirmed."
- `CmdAffirmAttackLance_002.wav`: "Coordinating fire."

---

### R2. Command Affirmative — Follow (`DialogueContext.Command.Affirmative.Follow`)
**Slot name:** `Command Affirmative Follow 1..8`  
**Adder refs (top 3):** "Oscar Mike to your location." / "Lead the way." / "On your six."  

- `CmdAffirmFollow_001.wav`: "Right behind you."
- `CmdAffirmFollow_002.wav`: "On your six."
- `CmdAffirmFollow_003.wav`: "Lead the way."

---

### R3. Command Affirmative — Follow Lance (`DialogueContext.Command.Affirmative.Follow.Lance`)
**Slot name:** `Command Affirmative Follow Lance 1..5`  
**Adder refs (top 2):** "With you." / "Following your lead, Commander."  

- `CmdAffirmFollowLance_001.wav`: "Lance on you, Commander."
- `CmdAffirmFollowLance_002.wav`: "With you, boss."

---

### R4. Command Affirmative — Move Lance (`DialogueContext.Command.Affirmative.Move.Lance`)
**Slot name:** `Command Affirmative Move Lance 1..10`  
**Adder refs (top 3):** "Group RZ acknowledged." / "Moving as a unit, Commander." / "We're on the move."  

- `CmdAffirmMoveLance_001.wav`: "Lance moving."
- `CmdAffirmMoveLance_002.wav`: "On the move as a group."

---

### R5. Command Affirmative — Hold Fire (`DialogueContext.Command.Affirmative.Hold_Fire`)
**Slot name:** `Command Affirmative Hold Fire 1..5`  
**Adder refs (top 3):** "Holding fire." / "Ceasing fire." / "Weapons hold."  

- `CmdAffirmHoldFire_001.wav`: "Holding fire."
- `CmdAffirmHoldFire_002.wav`: "Weapons hold."

---

### R6. Command Affirmative — Hold Fire Lance (`DialogueContext.Command.Affirmative.Hold_Fire.Lance`)
**Slot name:** `Command Affirmative Hold Fire Lance 1..2`  
**Adder ref:** "All weapons hold!"  

- `CmdAffirmHoldFireLance_001.wav`: "Lance, all weapons hold!"

---

### R7. Command Affirmative — Weapons Free (`DialogueContext.Command.Affirmative.Weapons_Free`)
**Slot name:** `Command Affirmative Weapons Free 1..3`  
**Adder refs:** "Weapons hot." / "Weapons free." / "Hehe, weapon safeties off." *(get playful for R13verGrrl)*  

- `CmdAffirmWeaponsFree_001.wav`: "Weapons hot!"
- `CmdAffirmWeaponsFree_002.wav` (playful): "Finally — safeties off."

---

### R8. Command Negative (`DialogueContext.Command.Negative`)
**Slot name:** `Command Negative 1..3`  
**Adder refs:** "Negative, cannot complete that order." / "Unable to complete that order, Commander." / "Can't fulfill that order, Commander."  

- `CmdNegative_001.wav`: "Negative — can't do that, Commander."
- `CmdNegative_002.wav`: "Unable to comply."

---

### R9. Command Negative — Attack (`DialogueContext.Command.Negative.Attack`)
**Slot name:** `Command Negative Attack 1..3`  
**Adder refs:** "That's an invalid target." / "Sensors won't lock on Commander." / "Negative on that target order."  

- `CmdNegativeAttack_001.wav`: "Can't take that shot."
- `CmdNegativeAttack_002.wav`: "Sensors won't lock."

---

### R10. Command Negative — Move (`DialogueContext.Command.Negative.Move`)
**Slot name:** `Command Negative Move 1..7`  
**Adder refs (top 3):** "I can't make it there." / "That's an invalid location." / "Not possible."  

- `CmdNegativeMove_001.wav`: "Can't get there — path's blocked."
- `CmdNegativeMove_002.wav`: "Negative, route's out."

---

### R11. Spot Enemy — Vehicle (`DialogueContext.Spot.Enemy.Vehicle`)
**Slot name:** `Spot Enemy Vehicle 1..9`  
**Adder refs (top 3):** "Enemy vehicles in the area." / "Mobile units in the area." / "Mobile units within sensor range."  
**Delivery:** Slight relief — vehicles are easier than mechs.

- `SpotEnemyVehicle_001.wav`: "Vehicles inbound. Should be quick."
- `SpotEnemyVehicle_002.wav`: "Enemy armor on radar."

---

### R12. Spot Enemy — VTOL (`DialogueContext.Spot.Enemy.VTOL`)
**Slot name:** `Spot Enemy VTOL 1..6`  
**Adder refs (top 3):** "Airborne hostiles on radar." / "Airborne Hostiles detected." / "Bogey ahead."  
**Delivery:** Slight tension — flyers are annoying.

- `SpotEnemyVTOL_001.wav`: "Airborne hostiles — eyes up!"
- `SpotEnemyVTOL_002.wav`: "Bogey overhead."

---

### R13. Take Damage — Friendly Fire from Commander (`DialogueContext.TakeDamage.Unit.Mech.FriendlyFire.Commander`)
**Trigger:** Player accidentally shoots her.  
**Slot name:** `Take Damage Unit Friendly Fire Commander 1..4`  
**Adder refs:** "Watch that stray fire!" / "Stay in your lane, I just took a hit from you!" / "Check your fire!" / "Blue on blue! Check your damn target!"  
**Delivery:** Annoyed but not vicious. She'll forgive you.

- `TakeDamageFriendlyFire_001.wav`: "Hey! Watch your fire, boss!"
- `TakeDamageFriendlyFire_002.wav`: "Blue on blue! Check your target!"
- `TakeDamageFriendlyFire_003.wav` (dry): "You know I'm on your side, right?"

---

### R14. Kill Blow — Mech Critical Cheer (`DialogueContext.KillBlow.Mech.Critical.Cheer`)
**Trigger:** Enemy mech nearing critical — reactor about to blow.  
**Slot name:** `Kill Blow Mech Critical Cheer 1..3`  
**Adder refs:** "Watch that 'Mech, it's going critical." / "That kill's reactor is about to go." / "Clear that splashed target, it's about to go critical."  

- `KillBlowMechCritical_001.wav`: "That one's going critical — reactor's cooking!"
- `KillBlowMechCritical_002.wav`: "Clear back — that mech's about to blow!"

---

## Tier 3 — Per-component damage (6 lines)

Six body-part destruction callouts. Real vocal strain, ~1.5 sec each. Adder is unambiguous on these — one line each, no variants.

| Slot | Adder ref | R13verGrrl file | Suggested line |
|---|---|---|---|
| `Take Damage Destroy Component LArm` | "Left arm's gone!" | `TakeDamageLArm_001.wav` | "Left arm — gone!" |
| `Take Damage Destroy Component RArm` | "My right arm's gone!" | `TakeDamageRArm_001.wav` | "Right arm's off!" |
| `Take Damage Destroy Component LLeg` | "My left leg's gone! I'm hobbled!" | `TakeDamageLLeg_001.wav` | "Left leg's out — I'm hobbling!" |
| `Take Damage Destroy Component RLeg` | "Right leg disabled, I'm stuck at slow speed!" | `TakeDamageRLeg_001.wav` | "Right leg's blown — moving slow!" |
| `Take Damage Destroy Component LTorso` | "Argh! Left torso destroyed!" | `TakeDamageLTorso_001.wav` | "Argh! Left side's gone!" |
| `Take Damage Destroy Component RTorso` | "My right torso's destroyed!" | `TakeDamageRTorso_001.wav` | "Right torso — shredded!" |

**Note:** DialogueContext for RArm is `DialogueContext.TakeDamage.Destroy.Component.Rarm` (lowercase 'arm' — appears to be a typo in the game engine, per the extracted string dump). Filename on our side uses `RArm` regardless; T4 wiring accounts for the case discrepancy.

---

## Tier 4 — Death and ejection (7 lines)

The dramatic slots. Adder is unrestrained on these — "Damn it, no! Shit, shit, shit!" Take Nil off the leash on delivery.

### D1. Died Pilot (`DialogueContext.Died.Pilot`)
**Slot name:** `Died Pilot`  
**Adder ref (~3.6 sec):** "Damn it, no! Shit, shit, shit!"  
**Delivery:** Full commitment — this is her death cry. Cut short, mid-sentence.

- `DiedPilot_001.wav`: "No — cover me, I'm—" *(cut short by static)*
- `DiedPilot_002.wav` (TR): "Hayır, hayır—!" *(No, no—!)*

### D2. Died Unit Critical (`DialogueContext.Died.Unit.Critical`)
**Slot name:** `Died Unit Critical`  
**Adder ref:** "Curses, my 'Mech's gone crtical, I need to eject!"  
**Delivery:** Urgent, mech-critical announcement — she's about to eject, not dead.

- `DiedUnitCritical_001.wav`: "Mech's gone critical — I'm ejecting!"

### D3. Died Unit Lance (`DialogueContext.Died.Unit.Lance`)
**Trigger:** A lancemate dies.  
**Slot name:** `Died Unit Lance 1..4`  
**Adder refs:** "Blast, we lost a 'Mech!" / "Lancemate down!" / "Damn them, they took down a friendly!" / "Friendly down!"  

- `DiedUnitLance_001.wav`: "Lancemate down!"
- `DiedUnitLance_002.wav`: "We lost one. Damn."

### D4. Died Unit Lance — Last Lancemate Standing (`DialogueContext.Died.Unit.Lance.LastLancemateStanding`)
**Trigger:** Everyone in the lance except her and the player is dead.  
**Slot name:** `Died Unit Lance Last Lancemate Standing 1..3`  
**Adder refs:** "It's down to just the two of us, Commander." / "Just you and me left, Commander." / "Two of us left, take point and I'll cover."  
**Delivery:** Steel-eyed. She's not scared — she's *ready*.

- `DiedLastLancemate_001.wav`: "It's just us, Commander. Let's finish this."
- `DiedLastLancemate_002.wav`: "You and me. Take point, I'll cover."

### D5. Ejected Helpless (`DialogueContext.Ejected.Helpless`)
**Slot name:** `Ejected Helpless 1..4`  
**Adder refs:** "Weapons wiped, I need to eject." / "Fighting effectiveness zeroed, ejecting!" / "My 'Mech's dead, I need to eject." / "No longer effective, ejecting."  
**Delivery:** Defeated tone — she's not scared, she's *done*.

- `EjectedHelpless_001.wav`: "Weapons wiped — punching out."
- `EjectedHelpless_002.wav`: "Mech's dead. Ejecting."

### D6. Ejected Scared (`DialogueContext.Ejected.Scared`)
**Slot name:** `Ejected Scared 1..3`  
**Adder refs:** "Another hit and I'm dead. I need to punch out." / "All systems critical! Ejecting!" / "Reactor containment failure! Damn it, ejecting."  
**Delivery:** Rapid, adrenal, real panic edge. Contrast with D5.

- `EjectedScared_001.wav`: "Reactor's going! Getting out! Getting out!"
- `EjectedScared_002.wav`: "All critical! Punching out — now!"

---

## Tier 5 — Biome banter (13 slots, 2 variants each = ~26 lines)

**The cat's home.** These are the ambient cockpit-chatter lines that fire while she's flying through specific biomes. Cat meow background layer belongs on many of these.

**Adder writes these as a mercenary observing her environment** — often referencing home ("Reminds me a bit of Lothario"), work colleagues ("Any bets on how long Fahad's gonna complain about sand"), professional considerations ("Those flat tops will make excellent firing positions"). Nil should do the same — reference "her Anatolian frontier home" (Chris/Nil name it), reference known R13verGrrl characters/pets, and keep the cockpit-thinking voice.

### B1. Biome Arctic (`DialogueContext.CharacterDialogue.Biome.Arctic`)
**Slot name:** `Biome Arctic 1..4`  
**Adder ref:** "Cold. Reminds me a bit of Lothario"  
**Delivery:** Reflective, half to the cat.

- `BiomeArctic_001.wav`: "Cold up here. Cockpit heater's not what it used to be."
- `BiomeArctic_002.wav`: "[cat's name], you still warm back there?" *(with cat meow post-splice)*

### B2. Biome Arctic Glacial (`DialogueContext.CharacterDialogue.Biome.Arctic.Glacial`)
**Slot name:** `Biome Arctic Glacial 1..4`  
**Adder ref:** "This place is freezing, even for me."  

- `BiomeArcticGlacial_001.wav`: "Even for me, this is cold."
- `BiomeArcticGlacial_002.wav` (Turkish): "Buz gibi." *(Ice-cold.)*

### B3. Biome Canyon (`DialogueContext.CharacterDialogue.Biome.Canyon`)
**Slot name:** `Biome Canyon 1..4`  
**Adder refs:** "Nothing here but dust and tumbleweeds." / "Dust, dust, and more dust. My eyes are blurring this place is so boring."  

- `BiomeCanyon_001.wav`: "Watch the elevation on radar — canyons play tricks."
- `BiomeCanyon_002.wav` (dry): "Dust. So much dust."

### B4. Biome Canyon Lush (`DialogueContext.CharacterDialogue.Biome.Canyon.Lush`)
**Slot name:** `Biome Canyon Lush 1..4`  
**Adder refs:** "How the hell does anything grow in a place like this?" / "Easy to get lost in this damn canyon."  

- `BiomeCanyonLush_001.wav`: "How does anything grow down here?"
- `BiomeCanyonLush_002.wav`: "Watch your bearings — easy to get turned around."

### B5. Biome Earthlike (`DialogueContext.CharacterDialogue.Biome.Earthlike`)
**Slot name:** `Biome Earthlike` *(single variant — no numbered suffix)*  
**Adder ref:** "This place looks familiar. I probably fought here before."  

- `BiomeEarthlike_001.wav`: "Feels like a place I could actually live in."

### B6. Biome Earthlike Desert (`DialogueContext.CharacterDialogue.Biome.Earthlike.Desert`)
**Slot name:** `Biome Earthlike Desert` *(single variant)*  
**Adder ref:** "Any bets on how long Fahad's gonna complain about sand in the actuators?"  

- `BiomeEarthlikeDesert_001.wav`: "I forgot how much I don't miss the sun back home."

### B7. Biome Forest (`DialogueContext.CharacterDialogue.Biome.Forest`)
**Slot name:** `Biome Forest 1..4`  
**Adder refs:** "Forest, trees, wildlife...I'll have to remember this place." / "Damn shame we're about to wreck this place."  

- `BiomeForest_001.wav`: "Beautiful out here. Shame we're not sightseeing."
- `BiomeForest_002.wav`: "Trees. Real cover. That's a nice change."

### B8. Biome Forest Autumn (`DialogueContext.CharacterDialogue.Biome.Forest.Autumn`)
**Slot name:** `Biome Forest Autumn 1..4`  
**Adder refs:** "It's fall here. Good huntin' times now." / "Nice view. Also nice cover."  

- `BiomeForestAutumn_001.wav`: "Fall colors. My grandmother would have loved this."
- `BiomeForestAutumn_002.wav`: "Nice cover in the leaves — use it."

### B9. Biome Forest Summer (`DialogueContext.CharacterDialogue.Biome.Forest.Summer`)
**Slot name:** `Biome Forest Summer 1..4`  
**Adder refs:** "Looks like it's getting hot." / "Reminds me of the place I retired to. Just hotter."  

- `BiomeForestSummer_001.wav`: "Heat's coming up. Watch your cooling."
- `BiomeForestSummer_002.wav`: "Reminds me of summers back home."

### B10. Biome Forest Winter (`DialogueContext.CharacterDialogue.Biome.Forest.Winter`)
**Slot name:** `Biome Forest Winter 1..4`  
**Adder refs:** "This fresh snow could give us fresh 'Mech tracks to follow." / "Pure white snow. Should make our targets stand out by comparison."  

- `BiomeForestWinter_001.wav`: "Fresh snow. Tracks will show."
- `BiomeForestWinter_002.wav`: "Targets will stand out against the white."

### B11. Biome Hostile (`DialogueContext.CharacterDialogue.Biome.Hostile`)
**Slot name:** `Biome Hostile 1..4`  
**Adder refs:** "I know I complained about the glacial planets, but I think I'd rather be back there now." / "Doesn't look like there's many life signs around."  

- `BiomeHostile_001.wav`: "Mama did not raise me to breathe canned air."
- `BiomeHostile_002.wav`: "Let's finish this and get back to a real planet."

### B12. Biome Hostile Moon (`DialogueContext.CharacterDialogue.Biome.Hostile.Moon`)
**Slot name:** `Biome Hostile Moon 1..2`  
**Adder refs:** "The lack of noise is grating." / "This low atmosphere is really messing up my reactions."  

- `BiomeHostileMoon_001.wav`: "Low gravity — watch your recoil."
- `BiomeHostileMoon_002.wav`: "Too quiet up here."

### B13. Biome Hostile Sulfurous + Volcanic (grouped — 3 slots, 3 lines)
| Slot | Adder ref | R13verGrrl file | Suggested |
|---|---|---|---|
| `Biome Hostile Sulfurous 1..2` | "This has to be the worst battlefield I've ever been on." | `BiomeHostileSulfurous_001.wav` | "This air is going to eat the seals off my cockpit." |
| `Biome Hostile Volcanic` (single) | "Are our enemies actively trying to find the worst places to fight?" | `BiomeHostileVolcanic_001.wav` | "Really? Volcanoes? Who picks these contracts?" |

---

## Tier 6 — Kill Blow richer variants (5 lines)

More flavor on kills. Adder splits these by *who* got the kill and *how*.

| Slot | Adder ref | R13verGrrl file | Suggested |
|---|---|---|---|
| `Kill Blow Mech Critical Congrats` (fires when a lancemate kills a critical mech) | "Nice one, though you coulda left some salvage for us." | `KillBlowMechCriticalCongrats_001.wav` | "Nice one — though you left me no salvage." |
| `Kill Blow Mech Critical Congrats Commander` (fires when the *player* kills a critical mech) | "Commander, you gonna leave any salvage for later?" | `KillBlowMechCriticalCongratsCmdr_001.wav` | "Boss, save some parts for us next time!" |
| `Kill Blow Mech Head Congrats 1..2` (fires on cockpit-kill of a mech) | "Nice shot, right in the head." / "Headshot. Lot's of salvage left on that one." | `KillBlowMechHeadCongrats_001.wav` | "Headshot — clean kill, cleaner salvage." |

---

## Tier 7 — Tactical marking (12 lines)

Marked Target + Firing At Target — fires when using tag/narc weapons. Rare in normal play; skippable if fatigue is real. **Adder's takes are technical and matter-of-fact** ("Marked that target with a Narc.") — Nil can match or riff.

| Slot | Adder ref (first variant) | R13verGrrl file | Suggested |
|---|---|---|---|
| `Marked Target With Narc 1..3` | "Marked that target with a Narc." | `MarkedTargetNarc_001.wav` | "Narc's on 'em." |
| `Marked Target With Tag 1..4` | "Lighting up that hostile with TAG." | `MarkedTargetTag_001.wav` | "Target tagged." |
| `Firing At Target Marked With Narc 1..4` | "Heh, Narc makes this too easy." | `FiringAtNarcTarget_001.wav` | "Firing on the Narc'd one." |
| `Firing At Target Marked With Tag 1..4` | "Firing on the lit target!" | `FiringAtTaggedTarget_001.wav` | "Firing on the tagged target." |

**Record 2 variants of each = 8 lines total for full coverage.**

---

## Total line count & recording plan

| Tier | Slots | Variants (target) | Lines | Est time (2 min/line) |
|---|---|---|---|---|
| **1 — Core mission arc** | 18 | 1-4 | ~35 | 70 min |
| **2 — Full command range** | 14 | 2 | ~28 | 55 min |
| **3 — Per-component damage** | 6 | 1 | 6 | 12 min |
| **4 — Death and ejection** | 6 | 1-2 | ~10 | 20 min |
| **5 — Biome banter** | 13 | 2 | ~26 | 55 min |
| **6 — Kill Blow variants** | 3 | 1 | 3 | 6 min |
| **7 — Tactical marking** | 4 | 2 | 8 | 15 min |
| **TOTAL** | **~65** | | **~116** | **~4 hours** |

**Recommended session structure:**
- Session 1 (~2 hours): Tiers 1 + 3 + 4 — core mission arc, damage callouts, death/eject (~50 lines). Everything the player will absolutely hear.
- Session 2 (~2 hours): Tiers 2 + 5 + 6 + 7 — full command range, biome banter, kill variants, marking (~65 lines). Depth and personality layer.

**Pre-session prep:**
1. Nil listens to `~/OneDrive/Desktop/R13vergrrl Lines/reference-adder-samples/` — 10 samples of Adder covering the emotional range.
2. Nil picks R13verGrrl's homeworld name (equivalent to Adder's "Lothario") — used in Biome Arctic, Forest, Home variants.
3. Nil picks the cat's actual name for `[cat's name]` slots (or Chris confirms via post).

**Post-recording pipeline:**
1. Trim + normalize (Nil, in Audacity)
2. Radio filter chain (Chris)
3. Cat meow layering where called for (Claude, at Chris's direction)
4. Import to Mod Editor as SoundWave assets → wire into `PO_R13verGrrl_DB.uasset`-equivalent Dialogue Book → each event slot references its `.wav` file(s)

---

## Change log

**2026-07-23 — This version.** Full rewrite against ground-truth extracted from `PO_Adder_DB.uasset` and `.uexp` (PilotOverhaul-Eternal, workshop ID 3501217348). Definitive event slot list — no more inference. Every slot name, tag namespace path, and Adder reference line comes directly from the shipping mod's binary.

Prior versions:
- **v4 (2026-07-19 evening)** — Rewrite against `.wem` filenames only (inferred, incomplete). Archived: [`archive/02-voice-lines-script-v4-preresearch.md`](archive/02-voice-lines-script-v4-preresearch.md).
- **v3, v2, v1** — earlier drafts based on partial info + web research. See git history.

---

**Next document:** [`03-references.md`](03-references.md) — annotated sources used across all script versions.
