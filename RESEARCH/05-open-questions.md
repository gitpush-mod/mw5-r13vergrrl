# Open Questions & Research Gaps

This document lists things we couldn't verify from research and that Chris will need to determine at build time. Better to flag unknowns than pretend they're solved.

---

## Q1: HireableCharacter DataTable Availability Flag Structure

**Question:** What is the exact field name and type for configuring when a pilot becomes hireable?

**What we know:**
- Career progression is reputation-based (confirmed)
- Mission completion triggers unlock (implied but not documented)
- Multiple pilot mods (PilotOverhaul, Advanced Career Starts) modify hiring, but their source code isn't publicly visible enough to reverse-engineer the exact DataTable schema

**What we don't know:**
- Is there a single `UnlockType` field, or is it `AvailabilityRule`, `HireCondition`, or something else?
- What values are valid? (`MissionCount`, `Reputation`, `Faction`, `Always`, etc.)
- If using mission count, is there a `MissionThreshold` field?
- Does the unlock trigger automatically or need a Blueprint listener?

**To resolve:**
1. Download PilotOverhaul-Eternal from Nexus, extract the .pak with `repak.exe`
2. Open `HireableCharacter` DataTable in the Mod Editor (copy from game or mod)
3. Inspect all columns and their data types
4. Cross-reference with vanilla examples
5. Test by creating a test row with `MissionCount >= 1` and see if it works

**Impact:** Medium. If no direct API exists, fallback is to make R13verGrrl always-available and mention unlock in description. Less elegant but works.

---

## Q2: Persona Dialogue Event Trigger Names ✅ RESOLVED (2026-07-19)

**Question (original):** What are the exact event names / field names in the Persona asset for binding voice lines?

**Resolution:** Empirically discovered by inspecting PilotOverhaul-Eternal's shipping audio bank at [`github.com/blastjack85/PilotOverhaul-Eternal`](https://github.com/blastjack85/PilotOverhaul-Eternal), specifically `MW5Mercs/Plugins/PilotQuirks/ModOverride/WwiseAudio/Windows/English(US)/PO_<Pilot>_DB.book/pilot/<Pilot>/*.wem`. That mod ships 67 fully-voiced pilots using the same event structure, giving us the canonical convention:

- **Event names are title-case-with-spaces** (e.g., `Pilot Hired`, `Command Affirmative Attack`, `Take Damage Destroy Component LArm`, `Biome Arctic`).
- **~60 events per pilot** organized into 11 categories: Pilot / Mission / Spot / Take Damage / Kill Blow / Command Affirmative / Command Negative / Command Success / Biome / Marked / Firing / Died / Ejected.
- **Randomization IS supported** — files ship as `<Event> 1.wem`, `<Event> 2.wem`, `<Event> 3.wem`, `<Event> 4.wem`; MW5 randomly picks one variant per fire.
- **"Idle" is NOT a category** — the old script's Idle_Cat/Car/Home/etc. lines have no matching event. Biome banter is the closest analogue for "cockpit chatter" — it's ambient-fired based on the current map.
- **Simultaneous events:** unclear from static analysis; likely queued, but real behaviour needs in-editor observation.

**Complete event list → see [`02-voice-lines-script.md`](02-voice-lines-script.md) and [`01-implementation-guide.md` §5](01-implementation-guide.md).**

---

## Q3: Voice Line Duration Limits

**Question:** Is there a maximum duration for voice lines, and what happens if exceeded?

**What we know:**
- Typical pilot voice lines are 2–5 seconds
- WAV import is supported (not just Wwise)
- Audio specs: 44.1 kHz, 16-bit, mono (assumed from general UE4 + community notes)

**What we don't know:**
- Hard limit on line duration? (e.g., max 10 seconds? 30 seconds?)
- Does MW5 gracefully cut off long audio or throw an error?
- If voice line plays during gameplay event, does it interrupt or queue?
- Can multiple voice lines play simultaneously (e.g., damage + cockpit idle)?

**To resolve:**
1. Test with 1-second, 3-second, 5-second, and 10-second voice lines
2. Check game logs for warnings or errors
3. Observe in-game: does audio cut off, or play fully?
4. If unclear, keep lines under 5 seconds (safe bet)

**Impact:** Low. As long as voice lines stay in the 2–5 second range (which is typical), this shouldn't be an issue.

---

## Q4: Portrait Transparency & Backgrounds

**Question:** Does MW5's portrait UI support transparent backgrounds (alpha channel), or require solid color?

**What we know:**
- Portraits are 256×256 PNG
- Community mods mention transparent backgrounds as compatible
- Most MW5 portraits appear to have a backdrop (solid color or gradient)

**What we don't know:**
- Does transparent alpha render correctly in the hire UI?
- If transparent, what color is the background layer (game UI color)?
- Should portrait include a colored backdrop, or let UI handle it?
- Does transparency affect rendering performance?

**To resolve:**
1. Create two portrait versions: one with transparent background, one with solid white or faction color
2. Test both in-game in hire screen
3. Screenshot to verify appearance
4. Use version that looks better

**Impact:** Low-medium. Mainly aesthetic. Both approaches should work; this is a polish question.

---

## Q5: Wwise vs. Direct WAV Import ✅ PARTIALLY RESOLVED (2026-07-19)

**Question (original):** Should we use Wwise 2019.1.4.7065 for audio, or can we ship raw SoundWave assets?

**Correction on version:** The correct Wwise version for current MW5 is **2021.1.2.7629** (per official Mod Editor Guide v2.3 — the earlier v2.2 spec of 2019.1.4.7065 is outdated). Version match is mandatory: the guide explicitly says "You must use the same version!"

**Partial resolution:** Empirical inspection of PilotOverhaul-Eternal confirms **Wwise IS used in shipping pilot voice mods** — files are `.wem` (Wwise Encoded Media) inside `.book` (Wwise SoundBank) containers under `ModOverride/WwiseAudio/Windows/English(US)/PO_<Pilot>_DB.book/`. This is the proven path.

**Still unclear:**
- Whether a bare-bones direct-WAV-import approach would ALSO work (some experimental modders may have gone this route).
- Whether the Persona asset in UE4 references `SoundWave` or `AkEvent` (Wwise event) — the shipping bank uses Wwise events.

**Recommendation:** For R13verGrrl v1.0, **plan on the Wwise path**. Nil records dry WAVs → we process them (trim, radio filter, cat mixdown) → then Wwise conversion + integration at T4. This matches what actual shipping pilot mods do.

If time-boxed, the fallback for early prototypes is to try direct SoundWave import against a test Persona and see if any lines fire — but ship-ready requires Wwise.

---

## Q6: Pilot Salary Balance

**Question:** What hire cost and daily salary would make R13verGrrl competitive but not overpowered?

**What we know:**
- Typical pilots cost 100k–500k C-Bills to hire
- Daily salary ranges 5k–15k C-Bills (depending on rank and skills)
- Hero pilots cost more but are stronger

**What we don't know:**
- Exact balancing formula (e.g., cost = base + (rank × skill_average) × factor)
- How much players earn per mission (varies by mission type and difficulty)
- Is R13verGrrl intended as affordable or expensive hero?
- Do players typically hire based on cost, skills, or appearance?

**To resolve:**
1. Pick a comparable vanilla hero pilot
2. Note their hire cost, salary, rank, and skills
3. Use same values for R13verGrrl (clone approach)
4. Test in-game: does player feel motivated to hire her?
5. Adjust based on feedback (higher cost = more "rare," lower = more accessible)

**Impact:** Low-medium. Balance is forgiving; players accept wide range of prices. Start with "Captain rank, 100k hire, 5k salary" and adjust post-release if feedback suggests change.

---

## Q7: Mission Count vs. Reputation Unlock

**Question:** Should R13verGrrl unlock after 1 mission (simple), or require a specific reputation level?

**What we know:**
- Mission count is simpler (just a counter)
- Reputation is game-canonical (career progression system)
- PilotOverhaul and other mods use reputation thresholds

**What we don't know:**
- Does the game expose a "mission count" variable, or only reputation?
- If using reputation, what's the minimum threshold for "after 1 mission"?
- First mission reward reputation: how much? (enough to trigger unlock?)

**To resolve:**
1. Research MW5 career system (Sarna.net or code)
2. Check if first mission gives enough reputation to trigger a threshold
3. If yes, use reputation (more elegant)
4. If no, use mission count (simpler workaround)
5. Worst case: make R13verGrrl always-available from game start (least elegant, but works)

**Impact:** Low. Unlock after 1 mission is the goal; exact mechanism is flexible.

---

## Q8: Origin Planet Canon

**Question:** Should R13verGrrl hail from a real BattleTech planet, or can we invent a custom headcanon planet?

**What we know:**
- Islamabad (Federated Suns, industrial) — real, lore-appropriate
- Karachi (Free Worlds League, frontier) — real, lore-appropriate
- Galatia (Anatolian heritage) — real, but Greek not Turkish
- Custom "R13ver Colony" in Outback — invented, works for mod flavor

**What we don't know:**
- Do players care if origin planet is canon or headcanon?
- Would custom planet feel out-of-place, or add charm?
- Does it matter for mod reception on Steam Workshop?

**To resolve:**
1. Pick Islamabad (safest: established industrial hub, Federated Suns, no need for headcanon)
2. Add to Persona bio: "Frontier pilot from Islamabad, Federated Suns space."
3. If desired, add lore snippet: "Raised around engineering and off-road vehicles on the Anatolian frontier."
4. If creating headcanon: write 2-3 sentences of flavor text to justify the planet's existence

**Impact:** Very low. Flavor text only. Won't affect gameplay. Choose Islamabad for simplicity.

**Recommendation:** Use Islamabad. If you want Anatolian flavor, that's just flavoring in the description.

---

## Q9: Expansion Voice Lines Recording

**Question:** Should we record the 8 expansion voice lines (E1–E8) now, or defer to post-1.0?

**What we know:**
- MVP set (13 lines) takes ~30–45 min to record
- Expansion set (8 lines) takes ~20–30 min additional
- Total time: ~60–90 min for full set
- Voice actor availability / time constraints unknown

**What we don't know:**
- Is the actor available for a 90-minute session, or only 45 minutes?
- Would it be more efficient to record all 21 lines in one session, or split?
- How much does voice fatigue affect later takes (quality degradation)?
- Is it possible to re-record expansion lines later at same audio quality?

**To resolve:**
1. Ask the voice actor: "Can you do 45 min (MVP) or 90 min (full set) in one session?"
2. If 90 min possible, go for full set (cleaner workflow, consistent audio)
3. If only 45 min, record MVP now, schedule expansion for v1.1
4. If re-recording later, expect to spend extra time matching audio quality

**Impact:** Medium. Affects scope and timeline. MVP + expansion is better for v1.0 launch, but MVP alone is sufficient for "feature complete."

**Recommendation:** Aim for full 21-line recording in one session (90 min). If actor is tired after 50 min, stop and defer expansion to v1.1.

---

## Q10: Mod Load Order / Compatibility

**Question:** Should the mod declare a specific load order, and will it conflict with other popular mods?

**What we know:**
- mod.json supports `defaultLoadOrder` field (integer)
- Some mods depend on others (e.g., PilotOverhaul requires MW5 Compat Pak)
- Portrait mods, audio mods, and pilot mods can conflict if both override the same Persona

**What we don't know:**
- What load order should R13verGrrl declare? (100 is default, higher = load later)
- Does R13verGrrl conflict with PilotOverhaul or other pilot-heavy mods?
- If user has multiple pilot mods, do all pilots appear in hire list, or does one override?

**To resolve:**
1. Set `defaultLoadOrder: 100` (neutral) in mod.json
2. Test with 0–2 other popular mods simultaneously (e.g., PilotOverhaul, Portrait packs)
3. Check if R13verGrrl appears in hire list and functions correctly
4. If conflicts detected, document in README and bump load order if needed
5. Communicate load order requirements in Steam Workshop description

**Impact:** Low-medium. Most mods don't conflict, but documenting it prevents user confusion.

---

## Summary: What Needs Verification at Build Time

| Question | Risk | Workaround |
|---|---|---|
| HireableCharacter schema (Q1) | Medium | Inspect existing DataTable + test |
| Persona event names (Q2) | High | Open vanilla Persona and inspect |
| Voice line duration (Q3) | Low | Keep lines under 5 sec (safe) |
| Portrait transparency (Q4) | Low | Test both options, pick visually better |
| Wwise vs. direct WAV (Q5) | High | Try direct WAV first, fallback to Wwise if needed |
| Pilot salary balance (Q6) | Low | Copy vanilla hero, adjust post-release if feedback |
| Mission count vs. reputation (Q7) | Low | Try mission count, fallback to always-available |
| Origin planet canon (Q8) | Very Low | Use Islamabad (established lore) |
| Expansion voice lines (Q9) | Medium | Record MVP now, defer expansion if time constrained |
| Mod load order / compatibility (Q10) | Low | Set default, test with other mods, document |

---

## Action Items for Chris

1. **Before modding starts:** Open Mod Editor, inspect one vanilla Persona + HireableCharacter DataTable to answer Q2, Q6
2. **During voice recording:** Plan for 45–90 min session depending on actor availability (Q9)
3. **During implementation:** Test direct WAV import → Persona binding; if no voice lines play, explore Wwise (Q5)
4. **During testing:** Try portrait with/without transparency, pick visually better version (Q4)
5. **During testing:** Test with 2–3 other popular mods installed to check compatibility (Q10)
6. **Post-release:** Gather community feedback on balance (salary, hire cost), adjust in v1.1 if needed (Q6)

---

**Note:** This is not a blocker list—these are questions to resolve as you build. Most have reasonable fallbacks or "safe defaults."

Good luck! The research phase is done; now it's execution.
