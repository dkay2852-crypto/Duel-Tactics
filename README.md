# Duel Tactics

A single-file mobile auto-battler themed as the Season 1 **Duelist Kingdom** tournament — Star Chips, an island map, and area type bonuses — with a one-screen iPhone portrait layout (`100dvh`, safe-area insets, no page scrolling). Card art is cached locally under `images/` (YGOPRODeck; emoji fallback). The hex field is a CSS 3D hologram tabletop.

Open `index.html` in a browser (or serve the folder locally). No build step or frameworks required.

## Home

- Mobile-game home menu: glowing **DUEL TACTICS** logo, VS hero card, mode select, huge **▶ Duel!** button, and a bottom nav (Records / Duel / Card Binder).
- **Duelist Kingdom** is the main tournament run. **Pegasus's Castle** unlocks after beating Pegasus once.
- Best Star Chip count, wins, and favorite monster are saved in `localStorage`.
- Settings (gear): sound, fight speed, reset progress. How to Play uses the book icon.

## Cards & combat

- Always uses Classic monsters from the public [YGOPRODeck API](https://db.ygoprodeck.com/api-guide/) (*Legend of Blue Eyes White Dragon* + *Metal Raiders*), cached in `localStorage` for 7 days.
- Art lives under `images/small/` and `images/cropped/` (YGOPRODeck asks not to hotlink); emoji art is the fallback if a file is missing.
- If the API/cache load fails, the home screen shows **Couldn't load cards, tap to retry** (no fantasy roster fallback).
- **Cost** from ATK+DEF: under 2000→1, 2000s→2, 3000s→3, 4000s→4, 5000+→5 (Level ignored). Borders: gray / green / blue / purple / gold.
- **Battle:** HP = DEF×1.5 (min 600), damage = ATK÷4. ★★ ×1.8, ★★★ ×3.2.
- **Roles:** Tank / Attacker / Fighter from ATK vs DEF; Attackers that are Spellcaster, Thunder, or Machine have range 2.
- Tap a monster (binder, shop, or board) for the full-screen **Guide** (fusion chain, ability, Types / Items / Basics / Duelists tabs).

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
- **☰ menu**: How to Play, speed, duel log
- **3 copies** fuse into ★★; trait bar counts **unique** Types (2/4/6 → bronze/silver/gold)
- **FIGHT** with board count (e.g. `3/5`); 1x/2x/3x speed; results banner
- Lock the shop between rounds; income = base + interest (≤5) + streak — **0 LP** or **0 Star Chips** ends the run
- **Items** after rounds 2 / 5 / 9 / 13 (pick 1 of 3 Equip Spells; max 3 per monster)
- **Duelist ladder** from Weevil through Pegasus — beat Pegasus to win
