# GitHub Tickets to Create

Chris should file these 7 issues on the [R13verGrrl project board](https://github.com/orgs/gitpush-mod/projects/12) as he progresses. They represent the major workstreams. Each includes title, description, and acceptance criteria.

---

## Ticket 1: Art Asset — Create R13verGrrl Portrait

**Title:** Create 256×256 portrait asset for R13verGrrl  
**Labels:** `art`, `pilot`, `MVP`  
**Assignee:** Chris (or artist volunteer)  
**Milestone:** Pre-implementation  
**Size:** Small (1-2 hours)

### Description

Create a 256×256 PNG portrait image representing R13verGrrl. Character traits: strong-willed, kind, caring, great sense of humor, a bit clumsy. Turkish/Anatolian heritage. Should reflect personality in art style.

### Acceptance Criteria

- [ ] Portrait image is 256×256 pixels
- [ ] PNG format (24-bit RGB or 32-bit RGBA)
- [ ] File size < 500 KB
- [ ] Shows character personality (confident, approachable, potentially humor)
- [ ] Saved as `R13verGrrl_Portrait.png` in project repo
- [ ] Art is original or properly credited/licensed (no copyright issues)

### Notes

Consider art style options: anime, photorealistic, stylized digital art, watercolor. Match MW5's existing portrait aesthetic (see reference portraits in Nexus mods).

---

## Ticket 2: Voice Recording — Record & Process Voice Lines (MVP Set)

**Title:** Record 13 core voice lines for R13verGrrl (MVP set)  
**Labels:** `audio`, `voice`, `pilot`, `MVP`, `recording`  
**Assignee:** Chris's girlfriend (voice actor)  
**Milestone:** Voice production  
**Size:** Medium (2-3 hours recording + post-processing)

### Description

Record 13 essential voice lines using the script in `02-voice-lines-script.md`. Lines include hire greeting, mission start, damage callout, victory/defeat, idle lines with cat/car themes, and misc flavor.

Delivery should reflect personality: confident, warm, slightly sarcastic humor. Turkish + English mix OK (1-2 Turkish words/phrases per line optional).

### Acceptance Criteria

- [ ] All 13 MVP voice lines recorded in quality (USB condenser mic or better)
- [ ] 2–3 takes per line; best take selected
- [ ] Each line trimmed to remove excess silence
- [ ] Normalized to -3 dB peak level
- [ ] Exported as WAV: 44.1 kHz, 16-bit, Mono
- [ ] Files named per script (e.g., `R13verGrrl_Hire_001.wav`)
- [ ] Total audio duration ~30–45 seconds
- [ ] Cat meow backgrounds on cat-related line (real meow or royalty-free sample, credited)
- [ ] Files staged in project `/audio/voice_lines/` folder
- [ ] No technical issues: no clipping, no hum, no excessive background noise

### Notes

See `02-voice-lines-script.md` for detailed delivery notes per line. Record in one session if possible for vocal consistency.

---

## Ticket 3: Modding — Implement Pilot in MW5 Editor

**Title:** Build R13verGrrl pilot DataTable and Persona assets in Mod Editor  
**Labels:** `modding`, `UE4`, `DataTable`, `MVP`  
**Assignee:** Chris  
**Milestone:** Implementation  
**Size:** Medium (3-4 hours)

### Description

Following `01-implementation-guide.md` Sections 3–5:

1. Copy a base Persona asset from `/Game/Characters/Personas/`
2. Rename and edit to `R13verGrrl_Persona` (name, callsign, rank, personality bio)
3. Copy HireableCharacter DataTable, add row for R13verGrrl (hire cost, salary, skills, traits)
4. Import portrait PNG and wire to Persona
5. All assets saved to R13verGrrl plugin (not base game)

### Acceptance Criteria

- [ ] Persona asset created: `R13verGrrl_Persona.uasset`
- [ ] Persona has name, callsign, rank (Captain or higher), personality description
- [ ] Persona portrait points to imported `R13verGrrl_Portrait` texture
- [ ] HireableCharacter DataTable row created with complete hire stats
- [ ] Hire cost: 100k–500k C-Bills (typical hero range)
- [ ] Daily salary: 5k–10k C-Bills
- [ ] Skills set to Veteran or Elite (60+ base gunnery/piloting)
- [ ] IsHero flag = True
- [ ] Traits assigned (1-3 from base game, e.g. Steady Hand, Sharp Shot)
- [ ] All assets saved to R13verGrrl plugin folder
- [ ] No errors in Editor logs on asset open
- [ ] Can compile/cook without errors

### Notes

Refer to vanilla Persona examples (`Persona_Female_Merc_*`) for field reference.

---

## Ticket 4: Voice Integration — Wire Voice Lines to Pilot

**Title:** Import voice WAVs and wire to R13verGrrl Persona in Editor  
**Labels:** `audio`, `voice`, `modding`, `MVP`  
**Assignee:** Chris  
**Milestone:** Implementation  
**Size:** Small (1-2 hours)

### Description

Import recorded voice WAV files into UE4 as SoundWave assets, then link each to the appropriate Persona dialogue trigger (hire greeting, mission start, damage callout, etc.).

### Acceptance Criteria

- [ ] All 13 voice WAV files imported into `/R13verGrrl/Content/Audio/` folder
- [ ] UE4 auto-converts to SoundWave assets (no manual reimport needed after first import)
- [ ] Each SoundWave asset loads without errors
- [ ] Persona asset populated with dialogue mappings:
  - [ ] OnHire → R13verGrrl_Hire_001
  - [ ] MissionStart → R13verGrrl_MissionStart_001
  - [ ] EnemySighted → R13verGrrl_EnemySighted_001
  - [ ] TakingDamage → R13verGrrl_TakingDamage_001
  - [ ] MechShutdown → R13verGrrl_MechShutdown_001
  - [ ] KillConfirmed → R13verGrrl_KillConfirmed_001
  - [ ] MissionVictory → R13verGrrl_MissionVictory_001
  - [ ] MissionFailed → R13verGrrl_MissionFailed_001
  - [ ] IdleCockpit (1–3 variants) → Idle_Cat, Idle_Car, Idle_Humor SoundWaves
- [ ] All dialogue links verified (no "None" or broken references)
- [ ] Editor plays voice when clicking preview button on SoundWave
- [ ] No audio clipping or distortion on preview

### Notes

If Wwise integration needed (advanced), see `01-implementation-guide.md` Section 5 and official Mod Editor guide Wwise section.

---

## Ticket 5: Unlock Mechanism — Implement Mission-1 Unlock Trigger

**Title:** Implement "hire after 1 mission" unlock trigger for R13verGrrl  
**Labels:** `modding`, `quest`, `UE4`, `MVP`  
**Assignee:** Chris  
**Milestone:** Implementation  
**Size:** Medium (2-3 hours, depends on MW5 API clarity)

### Description

Configure R13verGrrl to become hireable after the player completes any single mission. This may be a simple DataTable flag (MissionCount >= 1) or require a custom Blueprint/Career Arc.

Research from `05-open-questions.md` should clarify the cleanest approach.

### Acceptance Criteria

- [ ] R13verGrrl does NOT appear in hire list before any mission completion
- [ ] After completing first mission (any difficulty/type), R13verGrrl appears in hire list
- [ ] Hire cost, description, portrait all display correctly in hire UI
- [ ] Can successfully hire her and add to pilot roster
- [ ] Testing confirmed on clean career save (fresh game)

### Notes

If HireAvailability API unclear, check PilotOverhaul-Eternal source or create simpler: always-available with cosmetic "unlock" flag shown in description. Worst case: she's available from mission 1 (simple, but not "unlocked").

---

## Ticket 6: Testing & Iteration — Play-test and Balance

**Title:** Play-test mod, verify all features, gather balance feedback  
**Labels:** `testing`, `QA`, `balance`, `MVP`  
**Assignee:** Chris (+ volunteers)  
**Milestone:** QA / Pre-release  
**Size:** Large (2-3 play-through sessions, ~6-8 hours)

### Description

Launch MW5 with R13verGrrl mod enabled. Test:

1. Pilot appears in hire pool after first mission
2. Portrait displays correctly
3. All voice lines trigger at appropriate moments
4. Hire cost and salary feel balanced
5. Skills and traits match intended experience level
6. No crashes or audio glitches
7. No clipping/overlapping with other mods

### Acceptance Criteria

- [ ] Fresh career save: complete 1 mission, verify unlock trigger fires
- [ ] Enter market, hire R13verGrrl (verify portrait, name, description display)
- [ ] Fly 1-2 missions as R13verGrrl, listen for hire greeting + mission start voice lines
- [ ] Verify damage callout, kill confirmation, and victory lines play on appropriate events
- [ ] Verify idle cockpit lines play during mission downtime
- [ ] Salary and hire cost feel reasonable (not overpowered, not useless)
- [ ] No error messages in game log
- [ ] No audio distortion, clipping, or sync issues
- [ ] Comparison to vanilla pilots: R13verGrrl feels like a peer hero (not underpowered)
- [ ] Optional: test with other popular mods (PilotOverhaul, Portrait packs, etc.) to verify no conflicts

### Notes

Document any balance issues (e.g., "hire cost too high," "voice line doesn't trigger," "portrait texture distorted") as sub-comments or new issues.

---

## Ticket 7: Release — Package Mod and Publish to Steam Workshop

**Title:** Package R13verGrrl mod and publish to Steam Workshop  
**Labels:** `release`, `steam-workshop`, `modding`  
**Assignee:** Chris  
**Milestone:** Release  
**Size:** Small (1-2 hours)

### Description

Use "Manage Mod → Package Mod" in the Editor to cook and stage the mod, then publish to Steam Workshop for public availability.

### Acceptance Criteria

- [ ] Package Mod completed without errors
- [ ] Mod appears at `[ModEditor]/MW5Mercs/Mods/R13verGrrl/`
- [ ] Folder contains: Paks/, Resources/, mod.json
- [ ] mod.json has correct metadata (displayName, description, author, version)
- [ ] `steamPublishedFileId: 0` (fresh upload) before first publish
- [ ] Publish to Steam clicked, Workshop ID assigned
- [ ] Workshop page created and visible on Steam (may require 24-48 hours for indexing)
- [ ] Mod appears in Steam Workshop search for "R13verGrrl"
- [ ] Subscribers can download and enable mod via Steam client
- [ ] Gameplay verification: re-test with Workshop-installed version (not local copy)

### Notes

After first publish, Steam overwrites `steamPublishedFileId` with assigned numeric ID. Save that for future updates.

---

## Optional: Ticket 8 (Expansion)

**Title:** Record expansion voice lines (8 additional lines)  
**Labels:** `audio`, `voice`, `nice-to-have`, `expansion`  
**Assignee:** Chris's girlfriend (voice actor)  
**Milestone:** Post-1.0  
**Size:** Small (20-30 min recording)

### Description

If time/energy allows, record 8 expansion lines (overheating, low ammo, teammate praise, etc.) to add richness and variety to R13verGrrl's dialogue.

See `02-voice-lines-script.md` expansion section.

### Acceptance Criteria

- [ ] All 8 expansion voice lines recorded (same quality as MVP set)
- [ ] Exported as WAV, normalized, processed
- [ ] Files staged in project `/audio/voice_lines_expansion/`
- [ ] Integrated into Persona (if pursuing this ticket post-1.0 release)

---

## Tracking Template

Copy-paste into each GitHub issue body:

```markdown
## Checklist

- [ ] Item 1
- [ ] Item 2
- [ ] ...

## Notes

[Any additional context]

## Related Issues

[Link to related tickets]

## Resources

[Link to relevant research doc sections]
```

---

**Filing Order Recommendation**

1. Create all 7 tickets in quick succession (do not wait for prior ticket completion)
2. Assign Ticket 2 (Voice Recording) immediately — it's on the critical path and takes longest
3. Proceed with Tickets 1 & 3 in parallel (portrait art + modding)
4. Tickets 4 & 5 can start once 2 is underway
5. Ticket 6 (testing) starts after Tickets 3–5 complete
6. Ticket 7 (release) final step

All tickets can have dependencies noted to help with project timeline visualization.

---

**Board Setup**

If using GitHub Projects (classic or beta):

1. Create columns: `TODO`, `In Progress`, `Done`
2. Add all 7 tickets to `TODO`
3. Move to `In Progress` as work starts
4. Move to `Done` when acceptance criteria met

---

End of tickets. Chris can file these tomorrow and start work.
