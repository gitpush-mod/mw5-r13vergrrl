# Resources/

Mod-manager icon, Steam Workshop tile, and other non-Content assets.

| File | Purpose | Dimensions | Source |
|------|---------|-----------:|--------|
| `Icon128.png` | In-game mod-manager icon | 128×128 PNG | Derived from `../Content/Characters/R13verGrrl_Portrait.png` (LANCZOS downscale) — the pilot portrait renders more cleanly at small size than a cropped ID card |
| `WorkshopTile.png` | Steam Workshop tile — fed into the editor's *Publish to Steam* dialog at release time | 912×1136 PNG | Nil's Mercenary Command ID card promo (see [T0b](https://github.com/gitpush-mod/mw5-r13vergrrl/issues/2)) |
| `WorkshopTile_source.jpg` | Original JPG source for the Workshop tile — kept unmodified for re-processing | 912×1136 JPG | Original from Chris |

## When Steam picks these up

- **`Icon128.png`** is picked up automatically by MW5's mod-manager UI once the mod is enabled in-game.
- **`WorkshopTile.png`** is uploaded through the *Publish to Steam* dialog inside the Mod Editor (see [`RESEARCH/01-implementation-guide.md`](../RESEARCH/01-implementation-guide.md) §8, and [T7](https://github.com/orgs/gitpush-mod/projects/12)). Steam stores its own copy on the Workshop CDN — the file here is the source-of-truth for re-uploads.
