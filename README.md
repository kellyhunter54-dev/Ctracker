# Ctracker

A personal calorie tracker. Plain HTML, CSS and JavaScript in a single `index.html`, no build step, no dependencies.

## Features

- **Diary**: animated calorie ring (eaten, burned, remaining; ring style set in Settings: Grow adds your exercise burn to the ring as earned room, or Net / Start / End), protein / carbs / fat bars, meals split into Breakfast, Lunch, Dinner and Snacks, exercise, water (by container: glass, bottle, Stanley 20/30/40 oz or custom size, set in Settings) and a daily weigh-in. Swipe left/right (or use the arrows) to move between days; tap the date to jump back to today.
- **Log by servings or grams**: switch to Grams to enter calories per 100 g and the amount you ate (it remembers your last amount). Saved foods can be per serving or per 100 g, and recipes can store their cooked weight so a dish like pasta can be logged by the gram.
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

### Install it on your phone (or computer)

Ctracker is an installable web app (PWA), hosted free on GitHub Pages.

1. One-time setup: in this repo go to **Settings > Pages**, set **Source: Deploy from a branch**, branch **main**, folder **/ (root)**, and save. After a minute it is live at **https://kellyhunter54-dev.github.io/Ctracker/**
2. Open that link on your phone:
   - **iPhone (Safari):** Share button > **Add to Home Screen** > Add
   - **Android (Chrome):** Ctracker **Settings > Install the app** > Install (or the browser menu > Install app)
   - **Computer (Chrome/Edge):** the install icon in the address bar, or Settings > Install the app
3. It opens full screen with its own icon, works offline, and shows "A new version of Ctracker is ready" when an update has been pushed.

Your data stays on each device. On iPhone the installed app has its own storage, separate from Safari, so if you logged anything in Safari first, move it with **Settings > Copy backup** in Safari and **Paste backup** in the app.

When you change the code, bump `VERSION` in `sw.js` so installed copies get the update notice.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The whole app (markup, styles, logic) |
| `manifest.webmanifest` | App name, icons, colours and home-screen shortcuts for "install" |
| `sw.js` | Service worker: offline use and update notices |
| `icon.svg`, `icons/` | App icons (PNG sizes for Android/iPhone, maskable icon) |
