# Ctracker

A personal calorie tracker. Plain HTML, CSS and JavaScript in a single `index.html`, no build step, no dependencies.

## Features

- **Diary**: animated calorie ring (eaten, burned, remaining; ring style set in Settings: Grow adds your exercise burn to the ring as earned room, or Net / Start / End), protein / carbs / fat bars, meals split into Breakfast, Lunch, Dinner and Snacks, exercise, water (by container: glass, bottle, Stanley 20/30/40 oz or custom size, set in Settings) and a daily weigh-in. Swipe left/right (or use the arrows) to move between days; tap the date to jump back to today.
- **Quick logging**: suggestions from your saved foods and recent entries as you type, plus My foods / Recipes / Recent tabs in the Add food dialog to browse and pick, servings multiplier, optional macros, "Save to My foods", edit or delete any entry with undo.
- **Progress**: Week, Month, 3 Months and Year views with averages, days within goal, total deficit/surplus (and the weight it roughly equals), logging consistency, streak, a calories chart with goal line, a month calendar you can tap into, and a weight trend chart with your goal weight.
- **Calendar**: a month view where each logged day is coloured by how it went against your goal: green (on target, up to +100 kcal), yellow (+101 to +600), orange (+601 to +1,000), red (more than +1,000). The cut-offs are adjustable in Settings. Hover a day for a checklist (calories, protein, water, exercise, meals, weigh-in); click to open it.
- **My stats**: day count since your start date, progress bar toward your goal weight, weight change, days logged, on-target days, averages, total deficit, exercise, streaks, body stats (BMI, resting burn) and a weight chart since you started.
- **My foods**: a library of saved items for one-tap logging. Editing a saved food (or a recipe) can also update every past entry of it.
- **Exercise calculator**: pick walking, running, cycling, weights, HIIT, swimming, hiking or yoga. Walking and running use speed, incline and time (ACSM equations, good for a walking pad or treadmill); the rest use intensity and time (MET values). Both use your latest logged weight and count only net calories (the extra on top of resting burn), since your maintenance/goal already includes resting burn. You can still type calories directly.
- **Recipes**: save dishes you make with their ingredients (amount, calories, macros), servings and notes. Calories per serving are worked out for you, and you can log a serving (or 1.5, etc.) in one tap. Recipes also show up as suggestions when adding food.
- **Goals**: calorie, macro and water targets, goal weight, and a Mifflin-St Jeor goal calculator.
- **Settings**: your profile (start date, starting weight, sex, birthday, height; days before the start date are not counted anywhere), Metric or Imperial units, light/dark/auto theme, backup export (download or copy), import (file or paste, merge or replace), CSV export of the whole log, demo data, erase.
- **Desktop layout** (1000px and wider): sidebar, multi-column pages, centered dialogs and keyboard shortcuts (A add food, E add exercise, arrows change day, T today, 1-8 switch page).

## Data

Everything lives in the browser's `localStorage` under the key `ctracker.v1`, on the device you use. To move it to another device: **Settings > Download backup** (or **Copy backup**), then on the other device **Settings > Import file** (or **Paste backup**) and choose Merge or Replace.

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
