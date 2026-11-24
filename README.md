# Ctracker

A personal calorie tracker. Plain HTML, CSS and JavaScript in a single `index.html`, no build step, no dependencies.

## Features

- **Today**: animated calorie ring (goal, eaten, burned, remaining), protein / carbs / fat bars, meals split into Breakfast, Lunch, Dinner and Snacks, exercise, water glasses and a daily weigh-in. Swipe left/right (or use the arrows) to move between days; tap the date to jump back to today.
- **Quick logging**: suggestions from your saved foods and recent entries, servings multiplier, optional macros, "Save to My foods", edit or delete any entry with undo.
- **Progress**: Week, Month, 3 Months and Year views with averages, days within goal, total deficit/surplus (and the weight it roughly equals), logging consistency, streak, a calories chart with goal line, a month calendar you can tap into, and a weight trend chart with your goal weight.
- **My foods**: a library of saved items for one-tap logging.
- **Goals**: calorie, macro and water targets, goal weight, a Mifflin-St Jeor goal calculator, kg/lb, light/dark/auto theme, export/import backup, demo data, erase.

## Data

Everything lives in the browser's `localStorage` under the key `ctracker.v1`, on the device you use. Use **Goals > Export backup** to save a JSON file, and **Import backup** to restore it on another device or browser.

## Run it

Open `index.html` in a browser. That's it.

### Use it on your phone (installable)

1. In the GitHub repo: **Settings > Pages > Source: Deploy from a branch**, pick `main` and `/ (root)`, save.
2. Open the Pages URL on your phone.
3. iPhone: Share > **Add to Home Screen**. Android: menu > **Install app**.

It then opens full screen like an app and works offline (`sw.js` caches it). When you change the code, bump `VERSION` in `sw.js` so installed copies refresh.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The whole app (markup, styles, logic) |
| `manifest.webmanifest` | App name, icon and colours for "install" |
| `sw.js` | Service worker for offline use |
| `icon.svg` | App icon |
