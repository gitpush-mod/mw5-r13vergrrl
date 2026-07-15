# R13verGrrl Mod: Step-by-Step Implementation Guide

A complete walkthrough for adding a custom hero pilot to MechWarrior 5: Mercenaries. Written for someone with no prior MW5 modding experience.

## 1. Prerequisites

### Tools Needed

1. **MechWarrior 5 Mod Editor** (free via Epic Games Store)
   - Download from Epic Games Launcher
   - ~60 GB installed
   - Install path: `D:/Epic/Games/MechWarrior5Editor/` (adjust to your system)
   - Contains UE4 4.26 editor + MW5 project

2. **MechWarrior 5: Mercenaries (game)**
   - Buy on Steam / Epic / MS Store
   - Required for testing mods
   - Install path: `D:/SteamLibrary/steamapps/common/MechWarrior 5 Mercenaries/` (your path)

3. **Audio editing (for voice lines)**
   - Audacity (free) or similar WAV editor
   - Needed to normalize, trim, export voice recordings
   - **Do NOT use before recording** — the voice actor will handle raw recordings

4. **Image editor (for portrait)**
   - Photoshop, GIMP, or similar
   - Needed to create/edit 256×256 PNG portrait

5. **Text editor**
   - VS Code, Notepad++, or built-in editor
   - For editing `.json` and `.ini` files

6. **Optional: Wwise Audiokinetic** (for custom audio integration)
   - Free non-commercial license from audiokinetic.com
   - Version 2019.1.4.7065 (matches MW5)
   - Only needed if you're wiring voice lines into Wwise; many mods skip this and ship raw audio

### Knowledge Base

Before starting, **read these**:

1. **Chris's MW5 knowledge base** (local)
   - Path: `C:/Users/Chris Carpenter/VS Code Projects/mods/mw5-knowledgebase/MW5_MODDING_KNOWLEDGE.md`
   - Sections 1–5: essential (environment, packaging, plugin structure)
   - Section 13: the checklist

2. **Official MW5 Mod Editor Guide** (v2.3)
   - URL: `https://static.mw5mercs.com/docs/MW5Mercs_Mod_Editor_Guide_(v2.3).pdf`
   - Sections on DataTables, asset copying, and mod packaging

3. **GitHub PilotOverhaul-Eternal example**
   - URL: `https://github.com/blastjack85/PilotOverhaul-Eternal`
   - See how a real pilot mod is structured

### Install Order

1. Install MechWarrior 5 game
2. Install Mod Editor
3. Download and extract the mw5-r13vergrrl repository to `D:/SteamLibrary/steamapps/common/SpaceEngineersModSDK` (Chris's setup) or similar working directory
4. Install audio editor (optional; use later during voice recording)

---

## 2. Mod File Structure

### Directory Layout

Create the following structure inside the Mod Editor's MW5 project:

```
[ModEditor]/MW5Mercs/Plugins/R13verGrrl/
├── Binaries/                         (generated at cook time, ignore)
├── Content/
│   ├── Personas/
│   │   └── R13verGrrl_Persona.uasset     (pilot personality, voice, dialogue)
│   ├── Characters/
│   │   └── R13verGrrl_Portrait.uasset    (portrait texture asset)
│   ├── Data/
│   │   └── Pilots/
│   │       └── R13verGrrl_HireData.uasset (DataTable row or custom data)
│   └── Quests/
│       └── UnlockR13verGrrl_Quest.uasset  (quest/career arc for unlock)
├── Resources/
│   └── Icon128.png                    (mod icon, 128×128)
├── Source/                            (C++ code, if needed; skip for data-only mod)
├── Config/
│   ├── DefaultGame.ini                (template, copy from base game)
│   └── DefaultEngine.ini              (template)
├── R13verGrrl.uplugin                 (plugin descriptor)
├── mod.json                           (mod metadata)
└── Intermediate/                      (generated, ignore)
```

### Key Files Explained

#### `R13verGrrl.uplugin`

Plugin descriptor. Example:

```json
{
  "FriendlyName": "R13verGrrl Hero Pilot",
  "Version": 1,
  "VersionName": "1.0",
  "Description": "Adds R13verGrrl (Turkish frontier merc) as a hireable hero pilot. Unlock by completing any single mission.",
  "Category": "Pilots",
  "CreatedBy": "Chris Carpenter",
  "CreatedByURL": "https://github.com/gitpush-mod/mw5-r13vergrrl",
  "DocsURL": "",
  "MarketplaceURL": "",
  "SupportURL": "https://github.com/gitpush-mod/mw5-r13vergrrl/issues",
  "CanContainContent": true,
  "IsMod": true,
  "Installed": false,
  "Modules": [
    {
      "Name": "R13verGrrl",
      "Type": "Runtime",
      "LoadingPhase": "Default"
    }
  ]
}
```

#### `mod.json`

Metadata for Steam Workshop / Nexus. Example:

```json
{
  "displayName": "R13verGrrl - Hero Pilot Mod",
  "version": "1.0",
  "buildNumber": 1,
  "description": "Adds R13verGrrl (Türkiye-born frontier pilot) as a hireable hero character with full voice lines in Turkish/English, custom portrait, and an unlock quest that fires after completing any single mission.\n\nPersonality: Strong-willed, kind, caring, great humor, a bit clumsy. Loves cars and cats (real cat meows in voice lines!).\n\nAvailable for hire after first mission completion.",
  "author": "Chris Carpenter",
  "authorURL": "https://github.com/gitpush-mod/mw5-r13vergrrl",
  "defaultLoadOrder": 100,
  "gameVersion": "1.1.0",
  "manifest": [],
  "steamPublishedFileId": 0,
  "steamLastSubmittedBuildNumber": 0,
  "steamModVisibility": "Private"
}
```

**Important:** `steamPublishedFileId: 0` means "assign me a new Workshop ID on first upload." Steam will overwrite this after first publish.

---

## 3. Adding a Pilot: The DataTable Approach

### Understanding MW5 Pilot Data

MW5 stores hireable pilots in multiple DataTables:

- **Persona DataTable** — character personality, voice lines, visual appearance
- **HireableCharacter DataTable** — salary, rank, traits, availability, hire location
- **Portrait Texture** — 256×256 PNG asset reference

**Source file to copy from:**
- Vanilla game: `[ModEditor]/MW5Mercs/Content/Characters/Personas/`
- Find an existing pilot's Persona (e.g., `Persona_Female_Merc_01`) and copy to your plugin

### Step 1: Copy a Base Persona Asset

1. In the Mod Editor, open **Content Browser**
2. Navigate to `/Game/Characters/Personas/`
3. Find a female merc Persona (e.g., `Persona_Female_Merc_01`)
4. **Right-click → Create a copy** (or Duplicate)
5. Rename to `R13verGrrl_Persona`
6. **File → Save to Mod → R13verGrrl**
   - This moves the asset into your plugin folder
7. Now edit the asset (double-click to open)

### Step 2: Edit the Persona Asset

In the Persona details panel, update:

| Field | Value | Notes |
|---|---|---|
| **Character Name** | R13verGrrl | Display name in hire screen |
| **Callsign** | R13ver | Callsign shown in game UI |
| **Gender** | Female | Affects voice tone & UI |
| **Rank** | Captain or Major | Hero pilots typically rank higher |
| **Personality Description** | "Strong-willed, kind, caring. Loves cars & cats. Sharp sense of humor, bit clumsy." | Flavor text (shown on hover) |
| **Background Bio** | "Frontier pilot from the Anatolian territories. Known for unconventional tactics and loyalty." | Longer bio (optional) |
| **Portrait Texture** | (see Step 4 below) | Reference your new portrait |
| **Voice Persona** | (see Section 4 below) | Wire to voice lines |

**Save the asset.**

### Step 3: Copy a HireableCharacter DataTable Row

HireableCharacter DataTable defines hiring stats.

1. Navigate to `/Game/Characters/` in Content Browser
2. Find `HireableCharacter` DataTable (or similar, depending on game version)
3. Right-click → Create a copy
4. Rename to `R13verGrrl_HireData`
5. Save to your Mod
6. Double-click to edit

Add a new row with:

| Field | Value | Notes |
|---|---|---|
| **Name** | R13verGrrl | Must match Persona name |
| **Persona** | R13verGrrl_Persona | Point to your Persona asset |
| **HireCost** | 100000 | C-Bills to hire (500k–2M for hero) |
| **SalaryPerDay** | 5000 | Daily upkeep cost |
| **Rank** | 4 (Captain) or higher | Hero rank |
| **IsHero** | True | Marks as hero pilot (special treatment in UI) |
| **Traits** | [select 1-3 from base game] | E.g., Steady Hand, Resilient, Sharpshooter |
| **SkillRating** | 2 (Veteran) or 3 (Elite) | Hero pilots start better |
| **GunnerySkill** | 60 | 0–100 base skill |
| **PilotingSkill** | 60 | 0–100 base skill |

**Don't forget:** Save both assets to your Mod.

---

## 4. Portrait Image

### Specifications

- **Dimensions:** 256 × 256 pixels
- **Format:** PNG (24-bit RGB or 32-bit RGBA)
- **Aspect ratio:** Square (1:1)
- **Transparency:** Supported (use alpha channel for backgrounds)
- **Color space:** sRGB or standard RGB
- **File size:** Keep under 500 KB (typically 50–200 KB for portraits)

### How to Create

1. **Source image:** A headshot or character artwork (anime, photorealistic, digital art, etc.)
   - Ensure copyright is yours or CC licensed
   
2. **Resize in image editor:**
   - Open original in Photoshop/GIMP/Aseprite
   - Crop to focus on face/shoulders
   - Resize canvas to 256×256
   - Center character
   - Background: solid color or transparent (recommended: white or transparent)
   
3. **Save as PNG**
   - File → Export As → `R13verGrrl_Portrait.png`
   - Save to `[ModEditor]/MW5Mercs/Plugins/R13verGrrl/Content/Characters/`

### Import into UE4

1. In Content Browser, navigate to `/R13verGrrl/Characters/`
2. Drag the PNG file into the folder
3. UE4 imports it as a Texture2D asset
4. Double-click the imported texture to verify it looks correct
5. In Details panel, ensure:
   - **Compression Settings** = Default (LQ)
   - **MipGenSettings** = NoMipmaps (portraits are small)
   - **Sampler Type** = Default
6. Save

### Wire to Persona

In the Persona asset (Section 3, Step 2), set:
- **Portrait Texture** = R13verGrrl_Portrait

---

## 5. Voice Lines

### Audio Format & Specs

- **Codec:** WAV (uncompressed PCM)
- **Sample rate:** 44100 Hz (CD quality) or 48000 Hz (professional video standard)
- **Bit depth:** 16-bit
- **Channels:** Mono (recommended) or Stereo (use mono to save space)
- **Duration per line:** 1–5 seconds (most lines 2–3 seconds)
- **Peak levels:** Normalize to -3 dB (leave headroom for mixing)
- **Background:** Cat meows, ambient audio OK (part of character)

### Voice Line Checklist

Read **02-voice-lines-script.md** for the full script. Quick summary:

**MUST-HAVE lines (~12 lines):**
1. Hire screen greeting ("Hey, thanks for the offer.")
2. Mission start ("Let's move out.")
3. Enemy sighted ("Contacts on radar.")
4. Taking damage ("Taking fire!")
5. Mech shutdown ("Took a hit. Rebooting.")
6. Kill confirmed ("Target down.")
7. Mission victory ("We did it!")
8. Mission failure ("Damn, we lost.")
9. Idle cockpit line 1 (humor, cat-related)
10. Idle cockpit line 2 (car-related)
11. Ejection ("Punching out!")
12. Landing ("Feet on the ground.")

**NICE-TO-HAVE lines (~8 lines):**
- Overheating warning
- Low ammo callout
- Teammate praise
- Sarcastic lines
- Clumsy mishap reaction
- Alliance faction greeting
- Enemy faction callout

**Record in Turkish + English mix** (e.g., English main line + Turkish flavor phrases). See **02-voice-lines-script.md** for exact dialogue.

### Importing Voice Lines into UE4

1. Have actor record all lines → save as individual WAV files (e.g., `R13verGrrl_Hire_001.wav`)
2. In Content Browser, navigate to `/R13verGrrl/Content/Audio/`
3. Drag WAV files into folder
4. UE4 converts to SoundWave assets automatically
5. Each SoundWave becomes a referenceable audio asset

### Wiring Voice Lines to Persona

In the Persona asset, populate the **Dialogue** section:

| Event | SoundWave Asset |
|---|---|
| OnHire | R13verGrrl_Hire_001 |
| MissionStart | R13verGrrl_MissionStart_001 |
| EnemySighted | R13verGrrl_EnemySighted_001 |
| TakingDamage | R13verGrrl_TakingDamage_001 |
| MechShutdown | R13verGrrl_MechShutdown_001 |
| KillConfirmed | R13verGrrl_KillConfirmed_001 |
| MissionVictory | R13verGrrl_MissionVictory_001 |
| MissionFailed | R13verGrrl_MissionFailed_001 |
| IdleCockpit (1–3) | R13verGrrl_Idle_Car_001, Idle_Cat_001, Idle_Humor_001 |

**Note:** This is a simplified model. Real implementation may require:
- Persona → CharacterData → DialogueBank → SoundWave references
- Possible use of Wwise banks (optional, complex)

Check the reference section for exact Persona structure.

---

## 6. Unlock Quest

### Goal

After completing any single mission, R13verGrrl becomes hireable. No complex prerequisites.

### Implementation Approach

**Option A: Simple DataTable Flag (Easiest)**
- Create a HireAvailability DataTable row that triggers on mission count ≥ 1
- Reference in HireableCharacter row
- Minimal Blueprint work

**Option B: Career Arc DataAsset (Medium)**
- Create a Campaign Arc DataAsset (quest-like progression)
- Trigger on reputation threshold or mission completion
- More game-like feel, possible dialogue/notification

**Option C: Blueprint Logic (Hard)**
- Custom Blueprint that listens to mission-complete events
- Dynamically adds R13verGrrl to hire pool
- Most flexible but requires C++ knowledge

### Recommended: Option A

In your HireableCharacter DataTable row, add:

| Field | Value |
|---|---|
| **UnlockType** | MissionCount |
| **UnlockThreshold** | 1 |
| **AvailabilityLocation** | All (or specific faction) |

If the game doesn't have such fields, check **05-open-questions.md** — this may need verification.

### Origin Planet

For flavor, R13verGrrl hails from **Islamabad** (Federated Suns territory, industrial hub). Alternatively:

- **Karachi** (Free Worlds League, frontier feel)
- **Custom headcanon planet** (e.g., "R13ver Colony" in the Outback, invented for the mod)

**Chosen:** Islamabad (established lore planet, Turkish/Anatolian cultural analogue).

Set in the Persona **Background** or **Bio** field:
- *"Frontier pilot from Islamabad, Federated Suns space. Raised around engineering & off-road vehicles. Sharp tactical sense."*

---

## 7. Testing

### Workflow

1. **In the Mod Editor:**
   - Open MW5Mercs project
   - Click **Manage Mod** button
   - Select **R13verGrrl** as active mod
   - Click **Package Mod**
   - Waits for cook (5–30 min depending on cache)

2. **After cook:**
   - Mod appears at `[ModEditor]/MW5Mercs/Mods/R13verGrrl/`
   - Copy entire folder to `[SteamGame]/MW5Mercs/Mods/R13verGrrl/`

3. **Test in game:**
   - Launch MW5 game
   - Mods menu on title screen → enable R13verGrrl
   - Start career or new game
   - Complete first mission (any type)
   - Check hire screen in a market — R13verGrrl should be available

### Common Issues & Fixes

| Issue | Cause | Fix |
|---|---|---|
| Pilot appears but portrait is blank | Texture not linked in Persona | Re-check Section 4; ensure Portrait Texture field points to R13verGrrl_Portrait |
| Hire cost shows 0 | HireData DataTable row incomplete | Populate all cost/salary fields in DataTable |
| Voice line doesn't play | SoundWave asset not linked | Verify Dialogue → OnHire → points to correct SoundWave |
| Pilot doesn't unlock after mission | Availability rule not set | Check unlock trigger (Section 6); may need code |
| Game crashes on launch with R13verGrrl mod | Plugin not properly saved to mod | Verify all assets are saved to R13verGrrl plugin, not base game |

### Proof of Concept Test

1. Start career
2. Complete any mission
3. Travel to nearest Market with Hiring Hall
4. Click "Hire Pilot"
5. Scroll list — look for "R13verGrrl" or "R13ver (callsign)"
6. If visible, mod works
7. Optional: hire her, fly a mission, listen for voice lines

---

## 8. Packaging & Release

### Pre-Package Checklist

- [ ] All assets saved to R13verGrrl plugin (not base game)
- [ ] Persona asset has name, callsign, portrait, voice links
- [ ] HireableCharacter DataTable row has hire cost, salary, rank
- [ ] Portrait PNG is 256×256
- [ ] All voice WAV files imported & linked to SoundWave assets
- [ ] Unlock trigger set (mission count, reputation, etc.)
- [ ] R13verGrrl.uplugin FriendlyName set
- [ ] mod.json description clear & accurate
- [ ] No DevelopmentAssetRegistry.bin in output (too large)

### Package for Local Testing

1. **Manage Mod → Package Mod**
   - Cooks content (5–30 min)
   - Produces `[ModEditor]/MW5Mercs/Mods/R13verGrrl/`

2. **Copy to game:**
   ```
   xcopy "[ModEditor]/MW5Mercs/Mods/R13verGrrl/" "[SteamGame]/MW5Mercs/Mods/R13verGrrl/" /E /Y
   ```
   (Or manually drag folder)

3. **Edit modlist.json:**
   ```
   {
     "gameVersion": "1.x.x",
     "modStatus": {
       "R13verGrrl": { "bEnabled": true }
     }
   }
   ```

4. **Launch MW5 and test**

### Publish to Steam Workshop

1. In Mod Editor, click **Publish to Steam**
2. Fill in:
   - Title (same as mod.json `displayName`)
   - Description (same as mod.json `description`)
   - Visibility: Private (for initial testing) or Public (ready for release)
   - Tags: Pilots, Character, Hero
3. Accept Steam terms
4. Steam assigns Workshop ID, writes to mod.json `steamPublishedFileId`
5. Future updates: just re-cook + click Publish again

### Publish to Nexus Mods

(Optional, separate from Steam)

1. Create account on nexusmods.com/mechwarrior5mercenaries
2. Upload .zip of mod folder
3. Fill in Nexus form (similar to Steam)
4. Community moderators review & approve
5. Your mod appears in Nexus search

---

## 9. Post-Build: Iteration

### Common Next Steps

1. **Community feedback:** Collect feedback from testers
2. **Balance:** Adjust hire cost or skills based on user feedback
3. **More voice lines:** Record additional dialogue if actor is available
4. **Alternate portraits:** Add cosmetic portrait variants
5. **Mech customization:** Bundle a custom mech loadout with her unlock

### Version Bumping

Each update:
1. Edit mod.json: bump `version` and `buildNumber`
2. Re-cook Package Mod
3. Test locally
4. Publish to Steam/Nexus (same process)

---

## References

- **Chris's knowledge base:** `C:/Users/Chris Carpenter/VS Code Projects/mods/mw5-knowledgebase/MW5_MODDING_KNOWLEDGE.md` (sections 1–5, 13)
- **Official Mod Editor Guide:** https://static.mw5mercs.com/docs/MW5Mercs_Mod_Editor_Guide_(v2.3).pdf
- **PilotOverhaul-Eternal example:** https://github.com/blastjack85/PilotOverhaul-Eternal
- **Sarna.net (BattleTech lore):** https://www.sarna.net

---

**Next:** See **02-voice-lines-script.md** for the voice recording script.
