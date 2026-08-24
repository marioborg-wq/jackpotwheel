# Jackpot Wheel — Skin Guide

Graphics are split into two folders:

- **`skin/`** — everything you replace to give the wheel a new visual identity. Keep filenames identical when swapping.
- **`assets/`** — coin-rain sprites, shared across skins (rarely need to change).
- **`audio/`** — all sound clips (music, SFX, voice).

## `skin/` — reskin these

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
| `image-88.png` | "KTO Jackpot de Fogo" logo/banner art | 574×256 (transparent) | Used above wheel and on win screen |

## `assets/` — usually untouched

| File | Role |
|---|---|
| `coin0.png`–`coin10.png` | Coin-rain sprites (10 variants) |

## `audio/` — all sound

| File | Role |
|---|---|
| `short_dramatic.mp3` | Background loop |
| `countdown-sine-wave-beeps.mp3` | Countdown beeps |
| `win-loop.mp3` | Win ambience loop |
| `coins-drop.wav` | Coin-drop SFX |
| `reel-spin.wav` | Wheel ratchet SFX while spinning |

## Rules for a clean re-skin
- Keep transparent PNGs transparent (chest icons, wheel ring, pointer, logo) — they sit over the background and glow effects.
- Keep `wheel-labels.png` square and centered; the 4 sector labels must stay in the same rotational order (Fogo top, then clockwise Major/Minor/Mini) since the code targets sectors by angle, not by reading the art.
- Chest icons should share the same canvas size/anchor point across all 5 (`icon_default` + 4 tiers) so they don't jump when swapped mid-animation.
- Tier colors (title, halo, fire tint) are set in code (`TIERS` array in `index.html`), not baked into the art — update them there if the new skin needs different accent colors.
