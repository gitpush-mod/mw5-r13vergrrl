# Content/

Raw source assets for the R13verGrrl mod. **`.uasset` files are NOT stored here** — those live only in the Mod Editor's project directory (`[ModEditor]/MW5Mercs/Plugins/R13verGrrl/Content/…`) and are regenerated on cook.

## Layout

| Path | What lives here | Editor path after import |
|------|-----------------|---------------------------|
| `Characters/R13verGrrl_Portrait.png` | 256×256 mod-ready portrait — drag into the editor's Content Browser to import as `Texture2D` | `/R13verGrrl/Characters/R13verGrrl_Portrait.uasset` |
| `Characters/R13verGrrl_Portrait_source.png` | Original high-res source (900×900) from ticket T1. Kept for future re-processing; do **not** import directly | — |
| `Personas/` | Empty until the editor creates `R13verGrrl_Persona.uasset` (see T3). Duplicate a vanilla `Persona_Female_Merc_*` and Save-To-Mod here | `/R13verGrrl/Personas/R13verGrrl_Persona.uasset` |
| `Data/Pilots/` | Empty until the editor creates `R13verGrrl_HireData.uasset` (see T3). Copy `HireableCharacter` DataTable row here | `/R13verGrrl/Data/Pilots/R13verGrrl_HireData.uasset` |
| `Quests/` | Empty until the editor creates `UnlockR13verGrrl_Quest.uasset` (see T5), if the unlock is Blueprint/CareerArc-driven rather than a DataTable flag | `/R13verGrrl/Quests/UnlockR13verGrrl_Quest.uasset` |
| `Audio/` | Voice WAVs (44.1 kHz, 16-bit mono per T2's acceptance criteria) drop in here once recorded. Editor auto-converts each to `SoundWave.uasset` on import | `/R13verGrrl/Audio/R13verGrrl_*_001.uasset` |

## Why raw sources and not .uasset

- `.uasset` binary files are Mod-Editor output and can drift between editor versions
- Source PNGs / WAVs are the canonical form — recoverable across editor rebuilds
- GitHub 100 MB per-file cap and the cooked pak size make `.uasset` a poor VCS fit anyway

See [`../RESEARCH/01-implementation-guide.md`](../RESEARCH/01-implementation-guide.md) for the full import + wiring workflow.
