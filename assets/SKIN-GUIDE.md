# Jackpot Wheel — Skin Guide

Every graphic the wheel uses lives in this `assets/` folder and is referenced by
filename only. To fully re-skin the wheel (new art style/brand), replace these
files **keeping the exact same filenames** — no code changes needed.

| File | Role | Source resolution | Notes |
|---|---|---|---|
| `game-bg-keyvisual.jpg` | Full-screen background scene | any (cover-fit to 393×861) | Dark, moody; text/UI sits on top |
| `wheel-labels.png` | The wheel ring art (4 sector labels + rim) | 720×720 (square, transparent) | Rendered at 360×360; sector order fixed at 0°/90°/180°/270° = Fogo/Major/Minor/Mini |
| `pointer.png` | Pointer/indicator at bottom of wheel | 728×127 (transparent) | Positioned independently of wheel scaling |
| `icon_default.png` | Closed chest (shown while spinning) | 275×275 (square, transparent) | |
| `icon_mini.png` | Open chest — Mini tier | same aspect as `icon_default` | No flames |
| `icon_minor.png` | Open chest — Minor tier | same aspect | Light glow |
| `icon_major.png` | Open chest — Major tier | same aspect | Stronger fire |
| `icon_super.png` | Open chest — Jackpot do Fogo (top tier) | same aspect | Largest flames/gold |
| `image-88.png` | "KTO Jackpot de Fogo" banner/logo art | 574×256 (transparent) | Used above wheel and on win screen |
| `coin0.png`–`coin10.png` | Coin-rain sprites (10 variants) | ~200×190 each (transparent) | Any subset of distinct coin faces works |
| `win-loop.mp3` | Win ambience loop | — | Audio, not graphics |
| `coins-drop.wav` | Coin-drop SFX | — | Audio |
| `reel-spin.wav` | Wheel ratchet SFX while spinning | — | Audio |

## Rules for a clean re-skin
- Keep transparent PNGs transparent (chest icons, wheel ring, pointer, banner) — they sit over the background and glow effects.
- Keep `wheel-labels.png` square and centered; the 4 sector labels must stay in the same rotational order (Fogo top, then clockwise Major/Minor/Mini) since the code targets sectors by angle, not by reading the art.
- Chest icons should share the same canvas size/anchor point across all 5 (`icon_default` + 4 tiers) so they don't jump when swapped mid-animation.
- Tier colors (title, halo, fire tint) are set in code (`TIERS` array in the component), not baked into the art — update them there if the new skin needs different accent colors.
