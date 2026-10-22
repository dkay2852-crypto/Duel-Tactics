# Duel Tactics

A single-file mobile-friendly auto-battler that mixes shop/bench/field synergy with classic Life Point combat.

Open `index.html` in a browser (or serve the folder locally). No build step or frameworks required.

## Card modes

- **Classic cards** (default): loads monster data at runtime from the public [YGOPRODeck API](https://db.ygoprodeck.com/api-guide/) for *Legend of Blue Eyes White Dragon* and *Metal Raiders*. Results are cached in `localStorage` for 7 days. No card images are loaded.
- **Original**: built-in fantasy roster (also used if the Classic fetch fails).

## Play

- Start with **8000 LP** and **10 gold**
- Shop cost by Level: 1–2 → 1🪙, 3–4 → 2🪙, 5–6 → 3🪙, 7 → 4🪙, 8+ → 5🪙
- Bench holds 5; field has 5 monster zones
- **3 copies** of the same monster fuse into a stronger ★★ card
- **2+ of the same Type** grant an ATK type bonus
- Cards are colored by Attribute (emoji/CSS art only)
- Battle auto-resolves left to right; leftover ATK hits Life Points
- Earn gold after each round — **0 LP** ends the duel 
