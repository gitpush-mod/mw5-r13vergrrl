# R13verGrrl Voice Lines Recording Script

Complete voice line script for the actor to record. **Rewritten 2026-07-19** against the empirical MW5 event surface after inspecting PilotOverhaul-Eternal's shipping audio bank — see the change-log at the bottom for what shifted.

**Structure:** three tiers — **Core (must-record, ~15 lines)**, **Recommended (record if possible, ~15 lines)**, and **Optional (situational depth, ~15+ lines)**.

**Estimated recording time:** Core ~40 min · Core+Recommended ~75 min · Full set ~2 hours.

**Delivery notes:** R13verGrrl is strong-willed but warm. Confident, dry-humored, professional under pressure, occasionally clumsy. Two lore anchors shape every line:

1. **The cat is in the cockpit with her.** Not remembered — present. Cat meow ambience is canonical background wherever it fits. Where the script says `[cat's name]`, Nil substitutes her cat's actual name at record time.
2. **Her canonical mech is a Marauder.** The player can put her in any chassis; the lore is that she prefers the old MAD. Confidence in cockpit banter reads without needing to name the chassis.

**Randomization:** MW5 fires events by *category* and randomly picks from all `.wav` files present for that event. **Record 2–3 takes per line** — they'll all get used as variants, keeping the pilot from sounding repetitive. Naming convention: `R13verGrrl_<Event>_001.wav`, `_002.wav`, `_003.wav` for takes of the same event.

**Filename mapping to MW5 events:** the wiring at T4 maps each `.wav` to a Persona dialogue-event slot named the same as the shipping convention (e.g., `Biome Arctic`, `Command Affirmative Attack`, `Take Damage Destroy Component LArm`). Filenames in this script use compact underscore form; T4 wires them to the game's title-case-with-spaces slots.

---

## Tier 1 — Core (must-record, 15 lines)

Fires in every mission. Skipping any of these leaves R13verGrrl silent at the most-noticeable moments.

### C1. Pilot Hired
**File:** `R13verGrrl_Hire_001.wav`  
**Event:** `Pilot Hired`  
**Trigger:** Player hires her from the hiring hall  
**Delivery:** Warm, confident, inviting  

**English:** "Hey, thanks for the offer. Name's R13ver. I'm ready to roll whenever you are."  
**Turkish (optional flavor):** "Hazırım!" (I'm ready!)  
**Short alt:** "Hey, thanks for the offer. Ready when you are." → `R13verGrrl_Hire_short_001.wav`

**Notes:** Warm smile. Slight pause before "I'm ready to roll." — this is the first thing the player hears from her.

---

### C2. Pilot Intro (Loadout / Cockpit Boot)
**File:** `R13verGrrl_PilotIntro_001.wav`  
**Event:** `Pilot Intro`  
**Trigger:** When she boots into the cockpit at mission start (before the drop)  
**Delivery:** Task-focused, casual  

**English:** "Systems green. Let's go earn some cbills."  
**Turkish (optional):** "Hazırız." (We're ready.)

**Notes:** Cockpit check moment. Cat meow in background OK.

---

### C3. Mission Intro (First Combat Contact)
**File:** `R13verGrrl_MissionIntro_001.wav`  
**Event:** `Mission Intro`  
**Trigger:** As the mission begins (after briefing, boots hit ground)  
**Delivery:** Alert, ready, professional  

**English:** "Alright, let's move out. Stay sharp out there."  
**Turkish (optional):** "Dikkat!" (Careful!)

**Notes:** Clipped, focused delivery. She's on the clock.

---

### C4. Spot Enemy (Generic)
**File:** `R13verGrrl_SpotEnemy_001.wav`  
**Event:** `Spot Enemy`  
**Trigger:** First hostile spotted on radar (any type)  
**Delivery:** Alert, flat + professional  

**English:** "Contacts on radar. We've got company."  
**Turkish (optional):** "Düşman!" (Enemy!)

**Notes:** Matter-of-fact veteran. Slight edge of tension OK.

---

### C5. Spot Enemy Mech
**File:** `R13verGrrl_SpotEnemyMech_001.wav`  
**Event:** `Spot Enemy Mech`  
**Trigger:** First enemy MECH spotted (fires in addition to C4 if the enemy is a mech)  
**Delivery:** Alert, focused, mech-vs-mech serious  

**English:** "Enemy mech! Now it's a real fight."  
**Turkish (optional):** "Mech geldi." (Mech incoming.)

**Notes:** Different weight than seeing a vehicle — mech-on-mech is the real threat. Read seriously.

---

### C6. Take Damage — Generic
**File:** `R13verGrrl_TakeDamage_001.wav`  
**Event:** `Take Damage Destroy Component`  
**Trigger:** Any component destroyed (generic fallback if the per-part events don't fire)  
**Delivery:** Sharp, reactive, slightly strained  

**English:** "Taking hits! Coming apart out here."  
**Turkish (optional):** "Vurdular!" (They hit me!)

**Notes:** Real urgency. Slight vocal strain. This is one of the most-heard lines in the mod — record 2–3 solid takes for randomization variety.

---

### C7. Kill Blow — Generic Cheer
**File:** `R13verGrrl_KillBlow_001.wav`  
**Event:** `Kill Blow Cheer`  
**Trigger:** She destroys any enemy unit  
**Delivery:** Confident, satisfied, quick  

**English:** "Target down."  
**Turkish (optional):** "Bitti." (Done.)

**Notes:** Under 2 seconds. Cool smirk in the voice. Player hears this a LOT — record 3 takes.

---

### C8. Kill Blow — Mech Cheer
**File:** `R13verGrrl_KillBlowMech_001.wav`  
**Event:** `Kill Blow Mech Cheer`  
**Trigger:** She specifically destroys an enemy MECH (bigger deal than a vehicle)  
**Delivery:** More triumphant, still professional  

**English:** "Scratch one mech! Nice."  
**Turkish (optional):** "İyi vuruş!" (Nice hit!)

**Notes:** A shade prouder than C7. Downing a mech is a real accomplishment.

---

### C9. Command Affirmative (Generic "Copy")
**File:** `R13verGrrl_CmdAffirmative_001.wav`  
**Event:** `Command Affirmative`  
**Trigger:** Any player order not covered by a more specific ack (fallback)  
**Delivery:** Crisp, professional  

**English:** "Copy that."  
**Turkish (optional):** "Anladım." (Understood.)

**Notes:** ~1.5 sec. Workhorse ack. Record 3 takes for variety — she'll say this constantly.

---

### C10. Command Affirmative — Move
**File:** `R13verGrrl_CmdAffirmativeMove_001.wav`  
**Event:** `Command Affirmative Move`  
**Trigger:** Player orders her to a waypoint  
**Delivery:** Alert, task-focused, motion in voice  

**English:** "Moving now."  
**Turkish (optional):** "Yoldayım." (I'm on my way.)

**Notes:** She's already moving. Slight forward energy.

---

### C11. Command Affirmative — Attack
**File:** `R13verGrrl_CmdAffirmativeAttack_001.wav`  
**Event:** `Command Affirmative Attack`  
**Trigger:** Player orders her to attack a specific target  
**Delivery:** Focused, combat-ready  

**English:** "Engaging! Weapons hot."  
**Turkish (optional):** "Saldırıyorum!" (I'm attacking!)

**Notes:** Combat energy — she's already lining up the shot.

---

### C12. Command Affirmative — Follow
**File:** `R13verGrrl_CmdAffirmativeFollow_001.wav`  
**Event:** `Command Affirmative Follow`  
**Trigger:** Player orders her to follow / hold formation  
**Delivery:** Steady, wingman-solid  

**English:** "Right behind you."  
**Turkish (optional):** "Arkandayım." (I've got your back.)

**Notes:** Reassuring. She's the reliable wingman.

---

### C13. Command Negative (Refusal / Can't-Comply)
**File:** `R13verGrrl_CmdNegative_001.wav`  
**Event:** `Command Negative`  
**Trigger:** She can't execute the order (out of range, unable, invalid target)  
**Delivery:** Frustrated but professional  

**English:** "Negative — can't get to that."  
**Turkish (optional):** "Yapamam." (I can't.)

**Notes:** Not defiant — resigned. She wanted to but can't.

---

### C14. Ejected Critical (Ejection Under Fire)
**File:** `R13verGrrl_Ejected_001.wav`  
**Event:** `Ejected Critical`  
**Trigger:** Mech takes critical damage, ejection sequence  
**Delivery:** Sharp, determined, adrenaline  

**English:** "Punching out! See you on the ground."  
**Turkish (optional):** "Atlıyorum!" (I'm jumping!)

**Notes:** ~2-second line. Fight-or-flight, but confident she'll make it.

---

### C15. Died — Pilot KIA
**File:** `R13verGrrl_Died_001.wav`  
**Event:** `Died Pilot`  
**Trigger:** She's killed in action  
**Delivery:** Cut short, mid-sentence — this is a death cry  

**English:** "No — cover me, I'm—" *(cut short by static / clip)*  
**Turkish (optional):** "Hayır—!" (No—!)

**Notes:** ~1 second. Should feel abrupt — the transmission cuts as she's hit. Chris (or Nil in post) can add a hard cut / static burst at the end. Don't clean-fade the trailing consonant; leave it raw.

---

## Tier 2 — Recommended (~15 lines)

Fires frequently. Adds massive personality and combat feel — you'll notice these missing in normal play.

### R1–R5. Biome Banter (5 lines — one per biome family)

These fire when she's operating in a specific biome. **Cat meow ambience is a natural fit here** — she's in her cockpit rambling to the cat while flying.

| # | File | Event | Delivery |
|---|---|---|---|
| R1 | `R13verGrrl_Biome_Arctic_001.wav` | `Biome Arctic` | Cold complaint, warm undertone |
| R2 | `R13verGrrl_Biome_Canyon_001.wav` | `Biome Canyon` | Alert, navigational caution |
| R3 | `R13verGrrl_Biome_Earthlike_001.wav` | `Biome Earthlike` | Nostalgic, warm |
| R4 | `R13verGrrl_Biome_Forest_001.wav` | `Biome Forest` | Wistful, quiet |
| R5 | `R13verGrrl_Biome_Hostile_001.wav` | `Biome Hostile` | Grim humor, alien-planet dread |

**Suggested lines** (Nil is free to riff — these are seeds, not scripts):

- **R1 Arctic:** "Cold up here. Cockpit heater's not what it used to be. [cat] you still with me back there?"
- **R2 Canyon:** "Watch the elevation on radar — canyons play tricks."
- **R3 Earthlike:** "Trees, real gravity, breathable air. Almost feels like home."
- **R4 Forest:** "Beautiful out here. Shame we're not sightseeing."
- **R5 Hostile:** "Mama did not raise me to breathe canned air. Let's finish this and go home."

**Notes:** Each biome line is a "cockpit thought" moment — she's talking half to herself, half to the cat, half to whoever's on the radio. Warm delivery. Cat meow background welcome on any of them.

---

### R6. Kill Blow — Mech Critical Cheer (Finishing a Hero Mech)
**File:** `R13verGrrl_KillBlowMechCritical_001.wav`  
**Event:** `Kill Blow Mech Critical Cheer`  
**Trigger:** She lands the killing blow on a hero/boss mech  
**Delivery:** Full triumph — earned it  

**English:** "Yes! Got the big one!"  
**Turkish (optional):** "İşte bu!" (That's it!)

**Notes:** Cheer, not just satisfaction. Boss kills are rare — go big.

---

### R7. Take Damage — Friendly Fire from Commander
**File:** `R13verGrrl_TakeDamage_FriendlyFire_001.wav`  
**Event:** `Take Damage Unit Friendly Fire Commander`  
**Trigger:** Player shoots her by mistake  
**Delivery:** Annoyed but restrained — she still likes the boss  

**English:** "Hey! Watch it, boss — that's me!"  
**Turkish (optional):** "Dikkat et!" (Watch out!)

**Notes:** Not angry. Slight exasperation. She'll forgive you. Half-laugh at the end works.

---

### R8–R13. Take Damage per Component (6 lines — one per body part)

Fires when a specific mech part is destroyed. All follow the same shape — short, sharp callout naming the part.

| # | File | Event | Suggested line |
|---|---|---|---|
| R8 | `R13verGrrl_TakeDamage_LArm_001.wav` | `Take Damage Destroy Component LArm` | "Left arm's gone!" |
| R9 | `R13verGrrl_TakeDamage_RArm_001.wav` | `Take Damage Destroy Component RArm` | "Right arm's off!" |
| R10 | `R13verGrrl_TakeDamage_LLeg_001.wav` | `Take Damage Destroy Component LLeg` | "Left leg's out — I'm hobbling!" |
| R11 | `R13verGrrl_TakeDamage_RLeg_001.wav` | `Take Damage Destroy Component RLeg` | "Right leg's blown!" |
| R12 | `R13verGrrl_TakeDamage_LTorso_001.wav` | `Take Damage Destroy Component LTorso` | "Left side's shredded!" |
| R13 | `R13verGrrl_TakeDamage_RTorso_001.wav` | `Take Damage Destroy Component RTorso` | "Right side's gone!" |

**Delivery notes:** Real vocal strain. Short (~1.5 sec each). Slight variation per line so they don't sound copy-pasted. Add a grunt or hiss where natural.

---

### R14. Spot Enemy Vehicle
**File:** `R13verGrrl_SpotEnemyVehicle_001.wav`  
**Event:** `Spot Enemy Vehicle`  
**Trigger:** First enemy vehicle spotted (tanks, hovercraft — not mechs)  
**Delivery:** Slight relief — vehicles are easier  

**English:** "Vehicles inbound. Should be quick work."  
**Turkish (optional):** "Araç." (Vehicle.)

**Notes:** Confident. She's not intimidated by tanks.

---

### R15. Command Affirmative — Weapons Free
**File:** `R13verGrrl_CmdAffirmativeWeaponsFree_001.wav`  
**Event:** `Command Affirmative Weapons Free`  
**Trigger:** Player gives weapons-free order (engage anything hostile)  
**Delivery:** Eager, hungry  

**English:** "Weapons free — finally!"  
**Turkish (optional):** "Ateş serbest!" (Fire at will!)

**Notes:** Combat itch scratched. Slight predator energy.

---

## Tier 3 — Optional (situational depth, ~15+ lines)

Fires only in specific scenarios. Skip cleanly if energy fades. Grouped for scanning.

### Lance-wide command variants
When the player orders the whole lance, the game may prefer the Lance-variant slot over the single-unit variant. Recording these gives Nil a distinct voice for group orders.

- **O1** `R13verGrrl_CmdAffirmativeAttackLance_001.wav` — `Command Affirmative Attack Lance` — "Lance engaging!"
- **O2** `R13verGrrl_CmdAffirmativeFollowLance_001.wav` — `Command Affirmative Follow Lance` — "Forming up, all pilots on you."
- **O3** `R13verGrrl_CmdAffirmativeHoldFireLance_001.wav` — `Command Affirmative Hold Fire Lance` — "Lance holding fire."
- **O4** `R13verGrrl_CmdAffirmativeMoveLance_001.wav` — `Command Affirmative Move Lance` — "Lance moving."

### Solo command variants
- **O5** `R13verGrrl_CmdAffirmativeHoldFire_001.wav` — `Command Affirmative Hold Fire` — "Holding fire."
- **O6** `R13verGrrl_CmdSuccessMove_001.wav` — `Command Success Move` — "In position." (fires on waypoint arrival)
- **O7** `R13verGrrl_CmdNegativeAttack_001.wav` — `Command Negative Attack` — "Can't take that shot."
- **O8** `R13verGrrl_CmdNegativeMove_001.wav` — `Command Negative Move` — "Can't get there — path's blocked."

### Ejection variants
Three flavors of the same moment. `Ejected Critical` (C14) covers the standard case; these two add nuance.

- **O9** `R13verGrrl_EjectedHelpless_001.wav` — `Ejected Helpless` — "Punching out — cockpit's dead!" *(defeated tone)*
- **O10** `R13verGrrl_EjectedScared_001.wav` — `Ejected Scared` — "Getting out! Getting out!" *(rapid, adrenal)*

### Lance-death events
- **O11** `R13verGrrl_DiedUnitLance_001.wav` — `Died Unit Lance` — "We lost one. Damn." *(grief for a fallen lancemate)*
- **O12** `R13verGrrl_DiedUnitLanceLast_001.wav` — `Died Unit Lance Last Lancemate Standing` — "It's just us. Let's finish this." *(steel-eyed, alone)*

### Spotting subvariants
- **O13** `R13verGrrl_SpotEnemyVTOL_001.wav` — `Spot Enemy VTOL` — "VTOL inbound — heads up!"

### Marking & tag-targeting
Fires when the player uses tag/narc weapons. Rare — most players don't use these.

- **O14** `R13verGrrl_MarkedTargetTag_001.wav` — `Marked Target With Tag` — "Target tagged."
- **O15** `R13verGrrl_MarkedTargetNarc_001.wav` — `Marked Target With Narc` — "Narc's on 'em."
- **O16** `R13verGrrl_FiringAtTaggedTarget_001.wav` — `Firing At Target Marked With Tag` — "Firing on the tagged one."
- **O17** `R13verGrrl_FiringAtNarcTarget_001.wav` — `Firing At Target Marked With Narc` — "Firing on the narc."

### Kill Blow richer variants
- **O18** `R13verGrrl_KillBlowMechHeadShot_001.wav` — `Kill Blow Mech Head Congrats` — "Headshot! Cored the cockpit!" *(fires on cockpit-kill of an enemy mech)*
- **O19** `R13verGrrl_KillBlowMechCriticalCongratsCmdr_001.wav` — `Kill Blow Mech Critical Congrats Commander` — "Nice one, boss!" *(fires when the PLAYER kills a critical mech — she's praising you)*
- **O20** `R13verGrrl_KillBlowMechCriticalCongrats_001.wav` — `Kill Blow Mech Critical Congrats` — "Great shot!" *(fires when a lancemate kills a critical mech)*

### Biome subvariants
If the actor is feeling generous, sub-biomes add texture. Same shape as R1–R5, more specific delivery:

- `R13verGrrl_Biome_ArcticGlacial_001.wav` — `Biome Arctic Glacial` — grimmer than R1
- `R13verGrrl_Biome_CanyonLush_001.wav` — `Biome Canyon Lush` — surprised — colour in a canyon
- `R13verGrrl_Biome_EarthlikeDesert_001.wav` — `Biome Earthlike Desert` — tired, hot
- `R13verGrrl_Biome_ForestAutumn_001.wav` — `Biome Forest Autumn` — reflective
- `R13verGrrl_Biome_ForestSummer_001.wav` — `Biome Forest Summer` — light, warm
- `R13verGrrl_Biome_ForestWinter_001.wav` — `Biome Forest Winter` — cold, quiet
- `R13verGrrl_Biome_HostileMoon_001.wav` — `Biome Hostile Moon` — lunar strangeness
- `R13verGrrl_Biome_HostileSulfurous_001.wav` — `Biome Hostile Sulfurous` — disgusted
- `R13verGrrl_Biome_HostileVolcanic_001.wav` — `Biome Hostile Volcanic` — awed / careful

### Miscellaneous
- **O30** `R13verGrrl_PilotAnnouncement_001.wav` — `Pilot Announcement` — a "general talk-over-comms" moment. Exact trigger unclear; likely fires during major mission beats. Suggested: "Everyone stay tight — this one's for the story books."
- **O31** `R13verGrrl_DiedUnitCritical_001.wav` — `Died Unit Critical` — "Boss, I'm hit hard — can't hold much longer!"

---

## Mapping — what's already recorded

**Recording progress as of the 2026-07-19 rewrite** (from Chris's checkoff on the previous script version — commit `b4521f1`):

- ✅ Recorded: `Hire_001`, `TakingDamage_001`, `MechShutdown_001`, `KillConfirmed_001`, `MissionVictory_001`, `MissionFailed_001`
- ⏳ Not yet recorded (per the checkoff): everything else in the old MVP set

Here's what each recorded file maps to under the new event system:

| Old filename | Maps to (new event) | Keep as-is? |
|---|---|---|
| `R13verGrrl_Hire_001.wav` | **C1** `Pilot Hired` | ✅ Yes |
| `R13verGrrl_MissionStart_001.wav` | **C3** `Mission Intro` | ✅ Yes — rename to `R13verGrrl_MissionIntro_001.wav` or keep, T4 wiring handles it |
| `R13verGrrl_EnemySighted_001.wav` | **C4** `Spot Enemy` | ✅ Yes — rename to `R13verGrrl_SpotEnemy_001.wav` |
| `R13verGrrl_TakingDamage_001.wav` | **C6** `Take Damage Destroy Component` (generic) | ✅ Yes — rename to `R13verGrrl_TakeDamage_001.wav` |
| `R13verGrrl_KillConfirmed_001.wav` | **C7** `Kill Blow Cheer` | ✅ Yes — rename to `R13verGrrl_KillBlow_001.wav` |
| `R13verGrrl_MissionVictory_001.wav` | **R6** `Kill Blow Mech Critical Cheer` (finishing a hero) | 🔄 Repurpose. The "we won" vibe works well for a triumphant boss-mech kill. Rename to `R13verGrrl_KillBlowMechCritical_001.wav`. |
| `R13verGrrl_MissionFailed_001.wav` | No matching event | ⚠️ Dead line. Hold for now — may find a use in a future patch. |
| `R13verGrrl_MechShutdown_001.wav` | No matching event | ⚠️ Dead line. Hold. |
| `R13verGrrl_Order_Copy_001.wav` | **C9** `Command Affirmative` | ✅ Yes — rename to `R13verGrrl_CmdAffirmative_001.wav` |
| `R13verGrrl_Order_Moving_001.wav` | **C10** `Command Affirmative Move` | ✅ Yes — rename to `R13verGrrl_CmdAffirmativeMove_001.wav` |
| `R13verGrrl_Order_FallBack_001.wav` | **C13** `Command Negative` (approximate) | 🔄 Repurpose. Delivery reads more as "I'm pulling back" than a refusal, but the tone works. Rename to `R13verGrrl_CmdNegative_001.wav`. |
| `R13verGrrl_Idle_Cat_001.wav` | No matching event | ⚠️ Dead line under Idle. **Reuse the content on R1 (Biome Arctic) or another biome line** — the "cat on the throttle" energy plays great as biome cockpit-banter. |
| `R13verGrrl_Idle_Car_001.wav` | No matching event | ⚠️ Dead line. Hold. |
| `R13verGrrl_Idle_Home_001.wav` | No matching event | ⚠️ Dead line — but the "mom's kitchen" line plays beautifully as R3 (`Biome Earthlike`). Consider redirecting the take. |
| `R13verGrrl_Idle_MercLife_001.wav` | No matching event | ⚠️ Dead line. Hold. |
| `R13verGrrl_Idle_Humor_001.wav` | No matching event | ⚠️ Dead line. Hold. |
| `R13verGrrl_Ejection_001.wav` | **C14** `Ejected Critical` | ✅ Yes — rename to `R13verGrrl_Ejected_001.wav` |
| `R13verGrrl_Landing_001.wav` | No matching event | ⚠️ Dead line. Hold. |

**Bottom line:** ~8 already-recorded lines map cleanly. ~2 can be repurposed. ~7 are dead-line candidates that either wait for future MW5 event surface expansion or can be redirected into biome banter.

---

## Recording Notes for the Actor

### Tone & personality (unchanged)
- **Strength:** competent, never sounds lost even when things go wrong
- **Warmth:** cares about the team; not cold or detached
- **Humor:** dry, slightly sarcastic, never mean-spirited
- **Accent:** natural Turkish rhythm is welcome; pure English is fine too

### Recording setup
- **Mic:** USB condenser or better
- **Environment:** quiet room, soft furnishings
- **Monitoring:** headphones (catch clicks, pops, sibilance)
- **Levels:** peaks −3 to −6 dBFS
- **Takes per event:** 2–3 (MW5 randomizes across all files present)

### Post-processing
- Normalize to −3 dBFS peak
- Trim leading/trailing silence
- Export WAV, 44.1 kHz, 16-bit, mono
- Name per the tables above

### Language mix
- **Primary:** English
- **Turkish flavor phrases:** 1–2 per line where natural (optional but recommended)
- **Cat meows:** background on Biome + Kill Blow + relaxed idle-adjacent moments

### Radio filter
Chris is applying a radio-comm filter chain in Audacity (see conversation notes for the recipe). Deliver dry — the filter goes on afterwards.

---

## Total line count & time estimate

| Tier | Lines | Approx Time (1 take each) | With 2–3 takes each |
|---|---|---|---|
| **Core (must)** | 15 | ~25 min | ~40 min |
| **Recommended** | 15 | ~25 min | ~40 min |
| **Optional (full)** | ~30 | ~40 min | ~60 min |
| **Total (all tiers)** | ~60 | ~90 min | **~2h 20m** |

**Recommendation:** Core in this session. Recommended if the actor is fresh. Optional over one more session on another day — recording fatigue kills quality after ~90 min.

**Randomization tip:** even for Core lines, doing 2–3 takes with slightly different intonation (angry / calm / dry) gives MW5 enough variety that R13verGrrl won't feel repetitive on 20-mission playthroughs. Better to have 3 usable takes of Kill Blow than 1 perfect one.

---

## Change log

**2026-07-19** — Full rewrite (this file).

<<<<<<< HEAD
- [x] `R13verGrrl_Hire_001.wav`
- [ ] `R13verGrrl_Hire_short_001.wav` *(alt short take of line 1)*
- [x] `R13verGrrl_MissionStart_001.wav`
- [ ] `R13verGrrl_EnemySighted_001.wav`
- [x] `R13verGrrl_TakingDamage_001.wav`
- [x] `R13verGrrl_MechShutdown_001.wav`
- [x] `R13verGrrl_KillConfirmed_001.wav`
- [x] `R13verGrrl_MissionVictory_001.wav`
- [x] `R13verGrrl_MissionFailed_001.wav`
- [ ] `R13verGrrl_Order_Copy_001.wav`
- [ ] `R13verGrrl_Order_Moving_001.wav`
- [ ] `R13verGrrl_Order_FallBack_001.wav`
- [ ] `R13verGrrl_Idle_Cat_001.wav`
- [ ] `R13verGrrl_Idle_Car_001.wav`
- [ ] `R13verGrrl_Idle_Home_001.wav`
- [ ] `R13verGrrl_Idle_MercLife_001.wav`
- [ ] `R13verGrrl_Idle_Humor_001.wav`
=======
Reason: empirical inspection of PilotOverhaul-Eternal's shipping audio bank (`PO_Adder_DB.book` — the same repo Chainsaw ships in, alongside 66 other pilots) plus a deep-research pass revealed the real MW5 event surface. Findings that drove the rewrite:
>>>>>>> 8a3d7df (Rewrite script against empirical MW5 event surface (PilotOverhaul-Eternal audio bank))

- ~60 events exist per pilot, structured in categories (Biome / Command / Died / Ejected / Firing / Kill Blow / Marked / Mission / Pilot / Spot / Take Damage).
- MW5 supports randomization: multiple `.wav` files per event, cycled at random.
- Category "Idle" **does not exist** — the 5 idle lines in the previous script are dead-line risks.
- Biome banter is the closest analogue to idle chatter and is missing entirely from the old script.
- Damage-per-component (6 body-part slots) and Spot-Enemy-per-unit-type are high-frequency events missing from the old script.
- Command acks are much richer than we scoped — 8+ variants (Attack/Follow/Hold Fire/Weapons Free × single/Lance).

**Previous version** — 2026-07-19 (earlier that day). Had 16 MVP + 12 Optional = 28 lines organized around a category system that predated inspection of a real audio bank. Superseded.

**Historical versions** — 2026-07-14 initial research, 2026-07-19 morning expansion. See git history for the earlier drafts.
