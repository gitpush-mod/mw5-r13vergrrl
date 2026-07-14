# AGENTS.md — R13verGrrl

MechWarrior 5: Mercenaries mod. Part of Chris's mod collection under
[`gitpush-mod`](https://github.com/gitpush-mod).

## What this is

Adds Chris's girlfriend as a character in MW5. Scaffold repo — project has
not started yet.

## For agents

- **Game:** MechWarrior 5: Mercenaries (Unreal Engine 4)
- **Knowledgebase (READ FIRST):** [`gitpush-mod/mw5-knowledgebase`](https://github.com/gitpush-mod/mw5-knowledgebase)
  — everything Chris knows about MW5 modding. `reference/ZuluBetterHeroes/`
  shows what a real MW5 UE4 plugin looks like end-to-end.
- **MW5 skill:** planned, not built yet.

## Getting started (once work begins)

Follow the standard MW5 mod plugin layout:

- `Config/`, `Content/`, `Resources/`, `ModOverride/`
- `R13verGrrl.uplugin` — UE4 plugin metadata
- `mod.json` — MW5 mod manifest

Build output (`Saved/`, `Intermediate/`, `Build/`) is regenerable and
gitignored — GitHub's 100 MB file cap blocks the cook-time
`Metadata/DevelopmentAssetRegistry.bin` file that UE4 produces.

Start by reading the knowledgebase, then look at
`mw5-knowledgebase/reference/ZuluBetterHeroes/` for how another character-
addition mod was structured. `PORT_PLAN.md` in the knowledgebase covers
the general porting approach.

## MUST NOT

- Modify vanilla MW5 game files
- Commit `Saved/`, `Intermediate/`, or `Build/` folders

## Related

- Knowledgebase: [`gitpush-mod/mw5-knowledgebase`](https://github.com/gitpush-mod/mw5-knowledgebase)
- Parent when checked out under Chris's tree: `mods/mw5-mods/` / `mods/AGENTS.md`
