# R13verGrrl Voice Line Transcripts — Source of Truth

**Purpose.** Every recorded WAV needs a text caption. MW5's `MWDialogueBookAsset` displays these in-game when captions are on, and the editor's per-line `Caption` field is populated from this file at T4 wiring time.

**Two states per line:** the checkbox reflects "recorded"; the quoted text is the caption that will land in the editor. Both start pre-populated from [`02-voice-lines-script.md`](02-voice-lines-script.md) v5.

## Workflow during recording

1. **Take is as-scripted?** → tick the checkbox. Move on.
2. **Take diverged from the script?** → tick the checkbox AND edit the quoted caption to reflect what Nil actually said. (Natural delivery beats rigid script-reading — expect divergence to be the norm, not the exception.)
3. **Multiple usable takes of the same slot?** → keep the best; add extras as `_002`, `_003` variants beneath. MW5 randomises across variants.
4. **Line skipped entirely?** → leave the checkbox unticked. If deliberate (Nil ran out of time / didn't feel it), add a `SKIPPED` note; the editor will fall back to a neighbouring variant.

## Workflow after recording

The final state of this file feeds the editor: one row = one `Caption` field in the corresponding line entry inside `PO_R13verGrrl_DB.uasset` (or whatever we name our Dialogue Book).

**Legend:**
- `(TR)` — Turkish flavour take. Full line in TR or English with a Turkish phrase mixed in.
- `(dry)` / `(louder)` / `(strained)` / `(playful)` — delivery notes copied from the script. Don't need to preserve in the caption itself.
- `[cat's name]` — placeholder where Nil substitutes her cat's actual name at record time.

---

## Tier 1 — Core mission arc (18 slots, ~35 lines)

### C1. Pilot Hired
- [ ] `PilotHired_001.wav` — "Hey, thanks for the offer. Ready when you are, Commander."
- [ ] `PilotHired_002.wav` — "Merhaba, Commander. Ready to work." *(TR)*
- [ ] `PilotHired_short_001.wav` — *(short alt take, 2–3 sec target)* "Hey, thanks. Ready when you are."

### C2. Pilot Intro
- [ ] `PilotIntro_001.wav` — "Systems green. Let's earn some C-Bills."
- [ ] `PilotIntro_002.wav` — "Marauder's warm. Ready to move, Commander."

### C3–C5. Pilot Announcement
- [ ] `PilotAnnouncement_001.wav` — "R13ver here."
- [ ] `PilotAnnouncement_002.wav` — "This is R13ver."
- [ ] `PilotAnnouncement_003.wav` — "R13ver reporting in."

### C6–C8. Mission Intro
- [ ] `MissionIntro_001.wav` — "Alright, let's move out."
- [ ] `MissionIntro_002.wav` — "Grid looks clear. Stay sharp."
- [ ] `MissionIntro_003.wav` — "Simple op, huh? Yeah, we'll see." *(dry)*

### C9. Spot Enemy (generic)
- [ ] `SpotEnemy_001.wav` — "Contacts on radar."
- [ ] `SpotEnemy_002.wav` — "Tangos incoming."
- [ ] `SpotEnemy_003.wav` — "Düşman!" *(TR — "Enemy!")*

### C10. Spot Enemy Mech
- [ ] `SpotEnemyMech_001.wav` — "Enemy mech ahead."
- [ ] `SpotEnemyMech_002.wav` — "Heavy metal! Big one, too."
- [ ] `SpotEnemyMech_003.wav` — "Mech contact — now it's a real fight."

### C11. Command Affirmative (generic)
- [ ] `CmdAffirm_001.wav` — "Copy that."
- [ ] `CmdAffirm_002.wav` — "Acknowledged."
- [ ] `CmdAffirm_003.wav` — "Roger."
- [ ] `CmdAffirm_004.wav` — "Anladım." *(TR — "Understood.")*

### C12. Command Affirmative — Move
- [ ] `CmdAffirmMove_001.wav` — "On my way."
- [ ] `CmdAffirmMove_002.wav` — "Moving now."
- [ ] `CmdAffirmMove_003.wav` — "Yoldayım." *(TR — "On my way.")*

### C13. Command Affirmative — Attack
- [ ] `CmdAffirmAttack_001.wav` — "Engaging."
- [ ] `CmdAffirmAttack_002.wav` — "On your target."
- [ ] `CmdAffirmAttack_003.wav` — "Saldırıyorum." *(TR — "Attacking.")*

### C14. Command Success Move (arrived at waypoint)
- [ ] `CmdSuccessMove_001.wav` — "In position."
- [ ] `CmdSuccessMove_002.wav` — "At the waypoint, holding."

### C15. Take Damage — generic
- [ ] `TakeDamage_001.wav` — "Taking heavy hits!"
- [ ] `TakeDamage_002.wav` — "Argh! Lost a component!" *(louder)*
- [ ] `TakeDamage_003.wav` — "I can't sustain this — need support!" *(strained)*

### C16. Kill Blow — generic Cheer
- [ ] `KillBlow_001.wav` — "Target down."
- [ ] `KillBlow_002.wav` — "Got them."
- [ ] `KillBlow_003.wav` — "Bitti." *(TR — "Done.")*

### C17. Kill Blow — Mech Cheer
- [ ] `KillBlowMech_001.wav` — "Enemy mech down!"
- [ ] `KillBlowMech_002.wav` — "Scratch one mech."
- [ ] `KillBlowMech_003.wav` — "That's another one on the pile."

### C18. Ejected Critical
- [ ] `EjectedCritical_001.wav` — "Punching out! That was close."

---

## Tier 2 — Full command range (~28 lines)

### R1. Command Affirmative Attack Lance
- [ ] `CmdAffirmAttackLance_001.wav` — "Lance target confirmed."
- [ ] `CmdAffirmAttackLance_002.wav` — "Coordinating fire."

### R2. Command Affirmative Follow
- [ ] `CmdAffirmFollow_001.wav` — "Right behind you."
- [ ] `CmdAffirmFollow_002.wav` — "On your six."
- [ ] `CmdAffirmFollow_003.wav` — "Lead the way."

### R3. Command Affirmative Follow Lance
- [ ] `CmdAffirmFollowLance_001.wav` — "Lance on you, Commander."
- [ ] `CmdAffirmFollowLance_002.wav` — "With you, boss."

### R4. Command Affirmative Move Lance
- [ ] `CmdAffirmMoveLance_001.wav` — "Lance moving."
- [ ] `CmdAffirmMoveLance_002.wav` — "On the move as a group."

### R5. Command Affirmative Hold Fire
- [ ] `CmdAffirmHoldFire_001.wav` — "Holding fire."
- [ ] `CmdAffirmHoldFire_002.wav` — "Weapons hold."

### R6. Command Affirmative Hold Fire Lance
- [ ] `CmdAffirmHoldFireLance_001.wav` — "Lance, all weapons hold!"

### R7. Command Affirmative Weapons Free
- [ ] `CmdAffirmWeaponsFree_001.wav` — "Weapons hot!"
- [ ] `CmdAffirmWeaponsFree_002.wav` — "Finally — safeties off." *(playful)*

### R8. Command Negative (generic)
- [ ] `CmdNegative_001.wav` — "Negative — can't do that, Commander."
- [ ] `CmdNegative_002.wav` — "Unable to comply."

### R9. Command Negative Attack
- [ ] `CmdNegativeAttack_001.wav` — "Can't take that shot."
- [ ] `CmdNegativeAttack_002.wav` — "Sensors won't lock."

### R10. Command Negative Move
- [ ] `CmdNegativeMove_001.wav` — "Can't get there — path's blocked."
- [ ] `CmdNegativeMove_002.wav` — "Negative, route's out."

### R11. Spot Enemy Vehicle
- [ ] `SpotEnemyVehicle_001.wav` — "Vehicles inbound. Should be quick."
- [ ] `SpotEnemyVehicle_002.wav` — "Enemy armor on radar."

### R12. Spot Enemy VTOL
- [ ] `SpotEnemyVTOL_001.wav` — "Airborne hostiles — eyes up!"
- [ ] `SpotEnemyVTOL_002.wav` — "Bogey overhead."

### R13. Take Damage — Friendly Fire from Commander
- [ ] `TakeDamageFriendlyFire_001.wav` — "Hey! Watch your fire, boss!"
- [ ] `TakeDamageFriendlyFire_002.wav` — "Blue on blue! Check your target!"
- [ ] `TakeDamageFriendlyFire_003.wav` — "You know I'm on your side, right?" *(dry)*

### R14. Kill Blow Mech Critical Cheer
- [ ] `KillBlowMechCritical_001.wav` — "That one's going critical — reactor's cooking!"
- [ ] `KillBlowMechCritical_002.wav` — "Clear back — that mech's about to blow!"

---

## Tier 3 — Per-component damage (6 lines, single variant each)

- [ ] `TakeDamageLArm_001.wav` — "Left arm — gone!"
- [ ] `TakeDamageRArm_001.wav` — "Right arm's off!"
- [ ] `TakeDamageLLeg_001.wav` — "Left leg's out — I'm hobbling!"
- [ ] `TakeDamageRLeg_001.wav` — "Right leg's blown — moving slow!"
- [ ] `TakeDamageLTorso_001.wav` — "Argh! Left side's gone!"
- [ ] `TakeDamageRTorso_001.wav` — "Right torso — shredded!"

---

## Tier 4 — Death and ejection (~10 lines)

### D1. Died Pilot
- [ ] `DiedPilot_001.wav` — "No — cover me, I'm—" *(cut short by static in post)*
- [ ] `DiedPilot_002.wav` — "Hayır, hayır—!" *(TR — "No, no—!" — cut short)*

### D2. Died Unit Critical (mech critical, about to eject)
- [ ] `DiedUnitCritical_001.wav` — "Mech's gone critical — I'm ejecting!"

### D3. Died Unit Lance (lancemate KIA)
- [ ] `DiedUnitLance_001.wav` — "Lancemate down!"
- [ ] `DiedUnitLance_002.wav` — "We lost one. Damn."

### D4. Died Unit Lance — Last Lancemate Standing
- [ ] `DiedLastLancemate_001.wav` — "It's just us, Commander. Let's finish this."
- [ ] `DiedLastLancemate_002.wav` — "You and me. Take point, I'll cover."

### D5. Ejected Helpless (defeated tone)
- [ ] `EjectedHelpless_001.wav` — "Weapons wiped — punching out."
- [ ] `EjectedHelpless_002.wav` — "Mech's dead. Ejecting."

### D6. Ejected Scared (adrenal, panic edge)
- [ ] `EjectedScared_001.wav` — "Reactor's going! Getting out! Getting out!"
- [ ] `EjectedScared_002.wav` — "All critical! Punching out — now!"

---

## Tier 5 — Biome banter (~26 lines)

### B1. Biome Arctic
- [ ] `BiomeArctic_001.wav` — "Cold up here. Cockpit heater's not what it used to be."
- [ ] `BiomeArctic_002.wav` — "[cat's name], you still warm back there?" *(cat meow post-splice)*

### B2. Biome Arctic Glacial
- [ ] `BiomeArcticGlacial_001.wav` — "Even for me, this is cold."
- [ ] `BiomeArcticGlacial_002.wav` — "Buz gibi." *(TR — "Ice-cold.")*

### B3. Biome Canyon
- [ ] `BiomeCanyon_001.wav` — "Watch the elevation on radar — canyons play tricks."
- [ ] `BiomeCanyon_002.wav` — "Dust. So much dust." *(dry)*

### B4. Biome Canyon Lush
- [ ] `BiomeCanyonLush_001.wav` — "How does anything grow down here?"
- [ ] `BiomeCanyonLush_002.wav` — "Watch your bearings — easy to get turned around."

### B5. Biome Earthlike
- [ ] `BiomeEarthlike_001.wav` — "Feels like a place I could actually live in."

### B6. Biome Earthlike Desert
- [ ] `BiomeEarthlikeDesert_001.wav` — "I forgot how much I don't miss the sun back home."

### B7. Biome Forest
- [ ] `BiomeForest_001.wav` — "Beautiful out here. Shame we're not sightseeing."
- [ ] `BiomeForest_002.wav` — "Trees. Real cover. That's a nice change."

### B8. Biome Forest Autumn
- [ ] `BiomeForestAutumn_001.wav` — "Fall colors. My grandmother would have loved this."
- [ ] `BiomeForestAutumn_002.wav` — "Nice cover in the leaves — use it."

### B9. Biome Forest Summer
- [ ] `BiomeForestSummer_001.wav` — "Heat's coming up. Watch your cooling."
- [ ] `BiomeForestSummer_002.wav` — "Reminds me of summers back home."

### B10. Biome Forest Winter
- [ ] `BiomeForestWinter_001.wav` — "Fresh snow. Tracks will show."
- [ ] `BiomeForestWinter_002.wav` — "Targets will stand out against the white."

### B11. Biome Hostile
- [ ] `BiomeHostile_001.wav` — "Mama did not raise me to breathe canned air."
- [ ] `BiomeHostile_002.wav` — "Let's finish this and get back to a real planet."

### B12. Biome Hostile Moon
- [ ] `BiomeHostileMoon_001.wav` — "Low gravity — watch your recoil."
- [ ] `BiomeHostileMoon_002.wav` — "Too quiet up here."

### B13. Biome Hostile Sulfurous
- [ ] `BiomeHostileSulfurous_001.wav` — "This air is going to eat the seals off my cockpit."

### B14. Biome Hostile Volcanic
- [ ] `BiomeHostileVolcanic_001.wav` — "Really? Volcanoes? Who picks these contracts?"

---

## Tier 6 — Kill Blow richer variants (3 lines)

- [ ] `KillBlowMechCriticalCongrats_001.wav` — "Nice one — though you left me no salvage." *(lancemate killed a critical mech)*
- [ ] `KillBlowMechCriticalCongratsCmdr_001.wav` — "Boss, save some parts for us next time!" *(commander killed a critical mech)*
- [ ] `KillBlowMechHeadCongrats_001.wav` — "Headshot — clean kill, cleaner salvage." *(cockpit-kill on a mech)*

---

## Tier 7 — Tactical marking (~8 lines)

### T1. Marked Target With Narc
- [ ] `MarkedTargetNarc_001.wav` — "Narc's on 'em."

### T2. Marked Target With Tag
- [ ] `MarkedTargetTag_001.wav` — "Target tagged."

### T3. Firing At Target Marked With Narc
- [ ] `FiringAtNarcTarget_001.wav` — "Firing on the Narc'd one."

### T4. Firing At Target Marked With Tag
- [ ] `FiringAtTaggedTarget_001.wav` — "Firing on the tagged target."

---

## Running tally

| Tier | Files planned | Files recorded |
|---|---|---|
| 1 — Core mission arc | 37 | *(update as you go)* |
| 2 — Full command range | 28 | *(update as you go)* |
| 3 — Per-component damage | 6 | *(update as you go)* |
| 4 — Death and ejection | 11 | *(update as you go)* |
| 5 — Biome banter | 24 | *(update as you go)* |
| 6 — Kill Blow variants | 3 | *(update as you go)* |
| 7 — Tactical marking | 4 | *(update as you go)* |
| **Total** | **113** | |

---

**Ticket:** [R13v-T2 on the R13verGrrl project board](https://github.com/orgs/gitpush-mod/projects/12?pane=issue&itemId=213292520).
**Script v5:** [`02-voice-lines-script.md`](02-voice-lines-script.md).
**Reference audio:** `~/OneDrive/Desktop/R13vergrrl Lines/reference-pilot-samples/`.
