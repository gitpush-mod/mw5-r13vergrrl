<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&height=180&color=0:1F2937,45:78716C,100:F97316&text=R13verGrrl&fontColor=ffffff&fontAlignY=35&fontSize=42&desc=A%20hero%20pilot%20mod%20for%20MechWarrior%205%20%E2%80%94%20scaffold%20ready&descAlignY=57&descSize=15" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/MechWarrior%205-Mercenaries-F97316?style=for-the-badge" alt="MW5" />
  <img src="https://img.shields.io/badge/Status-scaffold-yellow?style=for-the-badge" alt="Scaffold" />
  <a href="https://github.com/gitpush-mod/mw5-r13vergrrl/issues/new?template=feature_request.md&labels=enhancement"><img src="https://img.shields.io/badge/Ideas%20welcome-green?style=for-the-badge&logo=github&logoColor=white" alt="Ideas welcome" /></a>
</p>

> **"A love letter, but in the form of a hireable pilot."**

Personal MechWarrior 5 mod that adds Chris's girlfriend as a hero pilot. Character-addition mod — will include a custom portrait, voice lines, personality traits, and a simple unlock quest.

## 🛠️ Status

**Scaffold ready — editor work not started.** The plugin skeleton is in place; `RESEARCH/` has the full implementation guide, voice script, references, and open questions. Next step is opening the Mod Editor and following [`RESEARCH/01-implementation-guide.md`](./RESEARCH/01-implementation-guide.md) to build the Persona and DataTable assets.

### What's in the repo

| Path | What's in it |
|------|--------------|
| `R13verGrrl.uplugin` | UE4 plugin descriptor (data-only mod, IsMod=true) |
| `mod.json` | Steam Workshop metadata (v0.1.0, private, `steamPublishedFileId: 0`) |
| `Config/` | `DefaultGame.ini` + `DefaultEngine.ini` stubs |
| `Content/Characters/R13verGrrl_Portrait.png` | 256×256 mod-ready portrait |
| `Content/Characters/R13verGrrl_Portrait_source.png` | 900×900 original from ticket [T1](https://github.com/gitpush-mod/mw5-r13vergrrl/issues/1) — kept for future re-processing |
| `Content/` (Personas, Data, Quests, Audio) | Empty scaffolds — populated by the Mod Editor per [T3](https://github.com/orgs/gitpush-mod/projects/12), [T4](https://github.com/orgs/gitpush-mod/projects/12), [T5](https://github.com/orgs/gitpush-mod/projects/12) |
| `Resources/` | Placeholder for `Icon128.png` |
| [`RESEARCH/`](./RESEARCH/) | Full implementation guide, voice script, references, open questions |

## 🎯 Design targets

- ☑ **Custom pilot portrait** — 256×256 ready in `Content/Characters/` ✅
- ☐ Voice lines (Turkish + English, some with real cat meows in the background — a running joke)
- ☐ Personality traits reflecting the person (strong-willed, kind, funny, a little clumsy)
- ☐ Origin planet with a canonical BattleTech connection to Türkiye
- ☐ Simple unlock quest — complete a random mission to make her hireable
- ☐ Steam Workshop release

## 🚀 Install *(once released)*

Publish target: **Steam Workshop**. Manual install path will match the standard MW5 mod pattern:

```
%LOCALAPPDATA%\MW5Mercs\Saved\Mods\R13verGrrl\
```

## 🎯 Compatibility

- 🚧 **Target:** MechWarrior 5: Mercenaries (current version, post-DLC 7)
- Not yet playable — see status above.

## 📚 Reference material

- **Knowledgebase:** [`gitpush-mod/mw5-knowledgebase`](https://github.com/gitpush-mod/mw5-knowledgebase) (private) — includes `reference/ZuluBetterHeroes/` for how a working hero-pilot mod is structured.
- **Sibling mod:** [`gitpush-mod/mw5-zulibetterheroes-reforged`](https://github.com/gitpush-mod/mw5-zulibetterheroes-reforged) — trait-tree fork of Kurst's original.

## 🙌 Credits

- **Author:** [Chris Carpenter (Godimas101)](https://github.com/Godimas101)
- **Muse:** the person the mod is about — for putting up with the whole "let me put you in a mech game" thing
- **Voice work:** *TBD* — with cameo meows from resident cats

## 🧡 Support

**Patreon** is where the running project log lives.

[![Support on Patreon](https://raw.githubusercontent.com/Godimas101/personal-projects/main/patreon/images/buttons/patreon-medium.png)](https://patreon.com/Godimas101)

---

*Part of the [`gitpush-mod`](https://github.com/gitpush-mod) mod collection. Made with ♥ (and a lot of coffee) by Godimas + Claude.*
