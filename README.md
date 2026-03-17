# ⚡ Stormcaller

A Phaser 3 browser game inspired by World of Warcraft TBC Classic.
Play as a Tauren Shaman - summon totems, cast lightning, and take down raid bosses alongside your tank and healer.
Built for 1080×2400 (FHD+ Android portrait), playable in any desktop browser.

---

## 🚀 Running the Game

```bash
# 1. Install dependencies (first time only)
npm install

# 2. Start the dev server — browser opens automatically
npm run dev

# 3. Build for production / Android packaging
npm run build
```

---

> **Why `public/`?** Vite bundles everything in `src/` but serves `public/` as-is.
> Game data and sprites live in `public/` so Phaser's runtime loader can fetch them by URL.

---

## 🗺️ Screen Zones

All zones are defined in `src/main.js` under `window.GAME_CONFIG.ZONES`.
Set `DEBUG_ZONES: true` to see colored outlines (default on).

| Zone        | Description                          |
|-------------|--------------------------------------|
| BACKGROUND  | Full screen — level art              |
| BOSS        | Top center — raid boss sprite + HP   |
| TANK        | Center left — tank character         |
| HEALER      | Center right — healer character      |
| PLAYER      | Bottom left — Tauren Shaman (you)    |
| TOTEMS      | Bottom right — 4 totem slots         |
| POPUP       | Dead center — event messages         |
| ACTION_BAR  | Bottom strip — player ability buttons|

---

## 🎮 Adding Sprite Sheets

1. Drop your `.png` sprite sheet into `assets/sprites/`
2. Uncomment the matching `this.load.spritesheet(...)` line in `PreloadScene.js`
3. Adjust `frameWidth` / `frameHeight` to match your sheet

---

## 📋 Adding Game Data

Edit `data/level01.json`:
- **New ability**: add an entry under `"abilities"` and add its `id` to the character's `"abilityIds"` array
- **New phase**: add an entry to `"boss.phases"` with a `trigger` and `abilityIds`
- **Stat changes**: edit values directly under `"stats"` for any character or boss

---

## 🔜 Next Steps

1. Combat systems in `src/systems/` (threat, damage calc, AI)  
2. Real sprite sheet integration  
3. Totem placement logic  
4. Phase transition effects  
5. Win/lose conditions  
6. Capacitor packaging for Android  

---

## 🔧 Tech Stack

- [Phaser 3](https://phaser.io/) — game engine (loaded via CDN)
- Vanilla JS — no build step required for development
- [Capacitor](https://capacitorjs.com/) — Android packaging (later)
