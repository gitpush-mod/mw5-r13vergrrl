# AGENTS.md — R13verGrrl

MechWarrior 5: Mercenaries mod. Part of Chris's mod collection under
[`gitpush-mod`](https://github.com/gitpush-mod).

## What this is

Adds Chris's girlfriend as a character in MW5. Scaffold repo — project has
not started yet.

## Where work lives (RULE — non-negotiable)

**Every task on this mod is a ticket on its project board.** YOU (the agent) create the ticket BEFORE touching anything. No exceptions for "small" work.

**Board:** [R13verGrrl board](https://github.com/orgs/gitpush-mod/projects/12)

Concrete rules — same as TCS ticket-first:

- **Starting work?** Open a ticket in this repo, add to the board, set Status = **In Progress**, then start.
- **Have an idea for later?** Ticket in **Backlog**. Not in memory, not in a README, not in NOTES.md.
- **Finished?** Close the ticket with a closing summary comment (what you did / problems + solutions / anything NOT done).
- **Same-session micro-work?** Open + close in the same session — but the ticket exists.
- **Older than 30 days in Done?** The weekly cron in this repo moves it to Archived. The closed ticket + CHANGELOG entry persist.

Automation: closing a Done ticket auto-appends an entry to this repo's `CHANGELOG.md` (via the workflow in `gitpush-mod/.github`). Requires `MOD_PROJECT_TOKEN` org secret — already installed.

**Do NOT** work on this mod without a ticket. If Chris asks for something small, create + immediately-close the ticket. It's still faster than the paper-trail debt of un-ticketed work.

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
