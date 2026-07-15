# References & Research Sources

Every URL, tutorial, and resource used to build this research. Grouped by topic.

## Official MechWarrior 5 Documentation

- **[MechWarrior 5: Mercenaries Mod Editor Guide v2.3](https://static.mw5mercs.com/docs/MW5Mercs_Mod_Editor_Guide_(v2.3).pdf)** — Official guide to modding MW5. Covers DataTables, asset copying, mod packaging, Wwise audio setup. **Critical reference.**

- **[MechWarrior 5: Mercenaries Mod Editor Guide v2.1](https://static.mw5mercs.com/docs/MW5Mercs_Mod_Editor_Guide_(v2.1).pdf)** — Older version, included for reference. Same core info as v2.3.

- **[MechWarrior 5: Mercenaries Mod Editor Guide v2.2](https://static.mw5mercs.com/docs/MW5Mercs_Mod_Editor_Guide_(v2.2).pdf)** — Intermediate version, minor differences.

- **[MW5 Mission Campaign Integration Guide](https://mw5mercs.com/static/docs/MW5%20Mission%20Campaign%20Integration%20Guide.pdf)** — How to author custom quests and campaign arcs. Used for unlock quest design.

- **[MechWarrior 5: Mercenaries - Resources](https://mw5mercs.com/resources)** — Official modding resources hub. Links to editor, documentation, community.

## Chris's Local Knowledge Base

- **[mw5-knowledgebase/MW5_MODDING_KNOWLEDGE.md](C:/Users/Chris Carpenter/VS Code Projects/mods/mw5-knowledgebase/MW5_MODDING_KNOWLEDGE.md)** — Chris's personal knowledge dump from ZuluBetterHeroes-Reforged project. **Essential.** Covers pak structure, DataAsset inheritance gotchas, plugin renaming, debugging, and mod packaging workflow. Sections 1–5 and 13 are critical.

- **[ZuluBetterHeroes source files](C:/Users/Chris Carpenter/VS Code Projects/mods/mw5-knowledgebase/reference/ZuluBetterHeroes/)** — Raw mod source (rare). Reference for folder structure, trait DataAssets, and how real MW5 mods are organized.

## Pilot Modding Examples (GitHub & Nexus)

### GitHub Repositories

- **[blastjack85/PilotOverhaul-Eternal](https://github.com/blastjack85/PilotOverhaul-Eternal)** — Modern, maintained pilot overhaul mod. Demonstrates how to add/customize pilots, voice integration, portrait system. 56+ voiced pilots added. **Good reference for structure.**

- **[Wpnx330/PilotOverhaul](https://github.com/Wpnx330/Pilot Overhaul)** — Earlier pilot overhaul version. Similar patterns to Eternal.

- **[mw5mercs-modding/](https://github.com/mw5mercs-modding)** — Community org hosting multiple MW5 mods. Browse for example projects.

- **[Snafulator/mechwarrior_5_mods](https://github.com/Snafulator/mechwarrior_5_mods)** — Another modder's collection. Mix of systems mods but good for folder structure patterns.

### Nexus Mods (Pilot-Related)

- **[330's Pilot Overhaul (Nexus #477)](https://www.nexusmods.com/mechwarrior5mercenaries/mods/477)** — Heavily modified pilot system. Good for understanding hire mechanics, pilot customization.

- **[Pilot Overhaul - Eternal (Nexus #1265)](https://www.nexusmods.com/mechwarrior5mercenaries/mods/1265)** — Latest maintained pilot mod. Download & examine folder structure.

- **[Expanded Pilots (Nexus #433)](https://www.nexusmods.com/mechwarrior5mercenaries/mods/433)** — Adds 90+ new pilots. Example of large-scale pilot addition.

- **[All Pilots Have Potential (Nexus #383)](https://www.nexusmods.com/mechwarrior5mercenaries/mods/383)** — Pilot progression system. Shows alternative approach to pilot unlock mechanics.

- **[Fake ID - Pilot Customization (Nexus #295)](https://www.nexusmods.com/mechwarrior5mercenaries/mods/295)** — Simple pilot editing. Reference for minimal pilot data model.

- **[Portrait Pools Corrected (Nexus #1470)](https://www.nexusmods.com/mechwarrior5mercenaries/mods/1470)** — Portrait system deep-dive. Separates portrait pools for hireables vs NPCs.

## Career/Unlock Systems

- **[Advanced Career Starts (Nexus #641)](https://www.nexusmods.com/mechwarrior5mercenaries/mods/641)** — Custom career paths and unlock triggers. Demonstrates career system modding.

- **[Advanced Career Starts - Continued (Nexus #1444)](https://www.nexusmods.com/mechwarrior5mercenaries/mods/1444)** — Updated version. References reputation-based unlocks.

- **[Alternate Career Reputation Progression (Nexus #1176)](https://www.nexusmods.com/mechwarrior5mercenaries/mods/1176)** — Modifies reputation thresholds. Used to understand unlock triggers.

- **[MechWarrior 5: Mercenaries/Campaign Missions (Sarna.net)](https://www.sarna.net/wiki/MechWarrior_5:_Mercenaries/Campaign_Missions)** — Official campaign structure. Background for understanding mission types and progression.

## Audio/Wwise

- **[MechWarrior 5: Mercenaries Mod Editor Guide v2.3 — Wwise Section](https://static.mw5mercs.com/docs/MW5Mercs_Mod_Editor_Guide_(v2.3).pdf)** — Step-by-step Wwise 2019.1.4.7065 setup for audio modding. **Critical for voice implementation.**

- **[Audiokinetic Wwise](https://www.audiokinetic.com/)** — Download Wwise Authoring (free non-commercial). Documentation for audio project setup.

- **[Female Protagonist with Voice-Over (Nexus #559)](https://www.nexusmods.com/mechwarrior5mercenaries/mods/559)** — Custom-voiced pilot mod. Demonstrates voice line wiring.

- **[Shout at your BattleMech (Nexus #3)](https://www.nexusmods.com/mechwarrior5mercenaries/mods/3)** — Voice command mod. Alt approach to pilot audio (VoiceAttack integration).

- **[Modding MechCommander - Voices & Sound (IndieDB)](https://www.indiedb.com/features/modding-mechcommander-voices-sound)** — Related game (MechCommander 1/2). Audio specs may differ but provides context. Specs: ~100 kb/s bitrate, 8-bit, 12 kHz, Mono PCM (MechCommander; MW5 likely higher quality).

- **[Sounds of the Succession Wars Audio Overhaul 3.0 (Nexus #756)](https://www.nexusmods.com/mechwarrior5mercenaries/mods/756)** — Full audio mod. Example of how audio mods are packaged and deployed.

## Portrait & Art

- **[MW5 Portrait Overhaul (Nexus #879)](https://www.nexusmods.com/mechwarrior5mercenaries/mods/879)** — Large portrait pack. Format examples: 256×256 PNG confirmed.

- **[Gundam Portraits V3 (Nexus #315)](https://www.nexusmods.com/mechwarrior5mercenaries/mods/315)** — Anime-styled pilot portraits. Reference for 256×256 format and visual style options.

- **[The Alternate Player Portrait Series (Nexus #378)](https://www.nexusmods.com/mechwarrior5mercenaries/mods/378)** — Diverse portrait pack. Shows portrait asset integration.

- **[Animechwarrior - Anime Portraits Replacer with AI Generated Art (Nexus #755)](https://www.nexusmods.com/mechwarrior5mercenaries/mods/755)** — Modern portrait generation approach. 256×256 PNG.

- **[Mechwarrior 5 Pilot Portraits (Notion)](https://lancer-valkyrion.notion.site/Mechwarrior-5-Pilot-Portraits-1fd00268e2244504b20984a4c9a1ce5f)** — Community portrait guide. Dimensions and format specs.

## BattleTech Lore (Inner Sphere Planets)

### Core References

- **[Sarna.net - Inner Sphere](https://www.sarna.net/wiki/Inner_Sphere)** — Definitive BattleTech wiki. Encyclopedia of all planets, factions, history.

- **[Sarna.net - Galatia](https://www.sarna.net/wiki/Galatia)** — Planet candidate. Greek/Anatolian names (ancient Galatia = region in modern Turkey).

- **[Sarna.net - Galatea](https://www.sarna.net/wiki/Galatea)** — Different planet, famous as mercenary hiring hub.

- **[Sarna.net - Karachi](https://www.sarna.net/wiki/Karachi)** — Planet candidate. Pakistani-named, industrial hub. Available in MW5 timeframe.

- **[Sarna.net - Turko](https://www.sarna.net/wiki/Turko)** — Turkish-named planet (Federated Suns). Lost in 2nd Succession War, unavailable in MW5 (3015–3049).

- **[Sarna.net - Ahlat](https://www.sarna.net/wiki/Ahlat)** — Frontier world, Taurian Concordat. Middle Eastern possibility (Ahlat = historic Anatolian city).

- **[Sarna.net - Taurian Concordat](https://www.sarna.net/wiki/Taurian_Concordat)** — Periphery faction. Frontier colonization patterns, cultural diversity.

- **[Sarna.net - Outback](https://www.sarna.net/wiki/Outback)** — Underdeveloped frontier region (Federated Suns). Lore for headcanon planet creation.

- **[BattleTechWiki - Conflict Zones](https://www.sarna.net/wiki/MechWarrior_5:_Mercenaries/Conflict_Zones)** — MW5-specific playable regions. Available planets for MW5 career mode.

### Alternate Sources

- **[Inner Sphere Atlas - Interactive Map](http://www.isatlas.teamspam.net/)** — Visual map of Inner Sphere planets.

- **[Inner Sphere 3025 (gruese.de)](https://www.gruese.de/innersphere/)** — 3025-era snapshot (MW5 is 3015–3049).

- **[Stellar Cartography: The Inner Sphere (Atlas of Ice and Fire Blog)](https://atlasoficeandfireblog.wordpress.com/2021/06/07/stellar-cartography-the-inner-sphere-of-battletech/)** — In-depth planetary geography analysis.

## Community Guides & Tutorials

- **[Steam Community: Yosharian's MW5 Modding Guide](https://steamcommunity.com/sharedfiles/filedetails/?id=3130149004)** — Community guide to mod creation. High-level overview.

- **[Steam Community: Career Mode Tips and Mechanics](https://steamcommunity.com/sharedfiles/filedetails/?id=2193968918)** — Career system deep-dive. Reputation, unlocks, progression.

- **[Steam Community: How to Get Best AI Pilots?](https://steamcommunity.com/sharedfiles/filedetails/?id=2834500688)** — Pilot ranking and hiring strategy (player perspective, but reveals pilot system mechanics).

- **[MWO Forums: Mechwarrior 5 Mercenaries Mission Creation Tutorial](https://mwomercs.com/forums/topic/278099-mechwarrior-5-mercenaries-mission-creation-tutorial/)** — Mission authoring guide. Relevant for quest design.

## General Modding / UE4

- **[Unreal Engine 4 Documentation (Epic Games)](https://docs.unrealengine.com/4.26/)** — UE4 4.26 docs (MW5 uses this). Data tables, assets, blueprints.

- **[PC Gaming Wiki: MechWarrior 5 Mercenaries](https://www.pcgamingwiki.com/wiki/MechWarrior_5:_Mercenaries)** — Technical specs, file paths, installation notes.

## Tools

- **[repak.exe v0.2.3](https://github.com/trumank/repak)** — PAK packing/unpacking tool. Used in emergency troubleshooting (though "Manage Mod → Package Mod" is preferred).

- **[Audacity (free)](https://www.audacityteam.org/)** — Audio editing. For post-processing voice lines.

- **[Notepad++ (free)](https://notepad-plus-plus.org/)** — Text editor. For editing `.json`, `.ini` files.

- **[GIMP (free)](https://www.gimp.org/)** — Image editor. For portrait creation/editing.

## Survey Papers / Deep Dives

- **["Planets named for Real Places" (BattleTech Forums)](https://battletech.com/forums/index.php?topic=45171.0)** — Forum discussion on planet naming conventions. Context for origin planet choice.

- **[An Introduction to the Taurian Concordat (Secrets of BattleTech Substack)](https://secretsofbattletech.substack.com/p/an-introduction-to-the-taurian-concordat)** — Lore background on Periphery faction. Context for frontier colonization.

---

## Key Takeaways by Research Phase

### Phase 1: Environment & Tools
- Official Mod Editor (Epic Store, v2.26 UE4)
- Game from any storefront (cross-store compatible)
- Pack via "Manage Mod → Package Mod" (not manual repak)

### Phase 2: Pilot Data Model
- Persona asset (personality, voice, visuals)
- HireableCharacter DataTable (hire cost, salary, rank, unlock conditions)
- Portrait Texture (256×256 PNG)

### Phase 3: Voice System
- Wwise 2019.1.4.7065 (free non-commercial)
- WAV files (44.1 kHz, 16-bit, mono recommended)
- SoundWave assets (UE4 import)
- Persona → Dialogue → SoundWave references

### Phase 4: Unlock Mechanics
- Reputation-based or mission-count-based triggers
- Career Arc DataAsset (quest-like, complex)
- Or simple DataTable flag (if available)

### Phase 5: Planet Lore
- Galatia (Greek/Anatolian heritage, MW5-available)
- Islamabad (industrial hub, Federated Suns)
- Karachi (frontier, Free Worlds League)
- Or custom headcanon planet

---

**How to Use This List**

1. **For immediate reference:** Start with "Chris's Local Knowledge Base" and "Official MechWarrior 5 Documentation."
2. **For examples:** Check GitHub and Nexus Mods links (PilotOverhaul-Eternal most relevant).
3. **For troubleshooting:** See Chris's knowledge base Section 7–14.
4. **For lore:** Sarna.net is authoritative; search by planet name.

All URLs verified as of July 14, 2026.
