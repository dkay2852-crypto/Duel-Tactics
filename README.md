# Duel Tactics

A single-file mobile auto-battler themed as the Season 1 **Duelist Kingdom** tournament — Star Chips, an island map, and area type bonuses — with a one-screen iPhone portrait layout (`100dvh`, safe-area insets, no page scrolling). Classic mode uses locally cached card art under `images/` (YGOPRODeck; emoji fallback). The hex field is a CSS 3D hologram tabletop.

Open `index.html` in a browser (or serve the folder locally). No build step or frameworks required.

## Card modes

- **Classic cards** (default): loads monster data at runtime from the public [YGOPRODeck API](https://db.ygoprodeck.com/api-guide/) for *Legend of Blue Eyes White Dragon* and *Metal Raiders*. Results are cached in `localStorage` for 7 days. Card art is stored locally under `images/small/` and `images/cropped/` (YGOPRODeck asks not to hotlink); emoji art is the fallback if a file is missing.
- **Original**: built-in fantasy roster (also used if the Classic fetch fails).

## Board & art

- Shop and bench show card art with name and ATK/DEF; tap a card for a full-size view.
- The hex field uses CSS `perspective` / `rotateX(~50deg)` as a tabletop. Monsters are upright hologram billboards (cropped art, soft shadow, faint blue glow) with HP/mana bars above.
- Place / attack / hit / death use CSS 3D transforms only (no 3D library) so it stays smooth on iPhone.

## Play

- Start with **8000 LP** and **10 gold** at **Level 1** (board slots = level, up to 9)
- **Buy XP** (4🪙 → 4 XP) or earn **+2 XP** after each round; tap level for shop odds
- Shop weights stronger monsters as you level; card cost still follows monster Level
- Bench holds 9; place on a unified **4×7 hex board** per side (enemy + you)
- Tap a token for full stats; drag tokens to place (scroll is only blocked on token drags)
- **☰ menu**: How to Play, Classic/Original, speed, duel log
- **3 copies** fuse into ★★; trait bar counts **unique** Types (2/4/6 → bronze/silver/gold)
- **FIGHT** with board count (e.g. `3/5`); 1x/2x speed; results banner
- Lock the shop between rounds; income = base + interest (≤5) + streak — **0 LP** ends the duel
- **Items** after rounds 2 / 5 / 9 / 13 (pick 1 of 3 Equip Spells; max 3 per monster)
- **Duelist ladder** from Weevil to Yami Yugi — beat Yugi to win; end screen shows a run summary
