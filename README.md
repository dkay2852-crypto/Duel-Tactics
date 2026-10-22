# Duel Tactics

A single-file mobile-friendly auto-battler that mixes shop/bench/field synergy with classic Life Point combat.

Open `index.html` in a browser (or serve the folder locally). No build step or frameworks required.

## Card modes

- **Classic cards** (default): loads monster data at runtime from the public [YGOPRODeck API](https://db.ygoprodeck.com/api-guide/) for *Legend of Blue Eyes White Dragon* and *Metal Raiders*. Results are cached in `localStorage` for 7 days. No card images are loaded.
- **Original**: built-in fantasy roster (also used if the Classic fetch fails).

## Play

- Start with **8000 LP** and **10 gold** at **Level 1** (board slots = level, up to 9)
- **Buy XP** (4🪙 → 4 XP) or earn **+2 XP** after each round; tap level for shop odds
- Shop weights stronger monsters as you level; card cost still follows monster Level
- Bench holds 5; place on a **4×7 hex board** (your half)
- **3 copies** fuse into ★★; trait bar counts **unique** Types (2/4/6 → bronze/silver/gold)
- **FIGHT**: slide, lunge, mana ultimates; 1x/2x speed; results banner
- Income: base gold + interest (≤5) + win/loss streak bonus — **0 LP** ends the duel
- **Items** after rounds 2 / 5 / 9 / 13 (pick 1 of 3 Equip Spells; max 3 per monster)
- **Duelist ladder** from Weevil to Yami Yugi — beat Yugi to win; end screen shows a run summary 
