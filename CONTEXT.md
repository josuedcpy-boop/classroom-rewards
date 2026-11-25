# Project Context

History and technical reference for the Classroom Rewards project, so a new session (e.g. Claude Code) can pick up where the last one stopped.

## Overview

A standalone single-file HTML app (vanilla JS/CSS, no build, no dependencies) for a teacher's classroom reward system: `point_store.html` (localStorage key `pointStoreData_v2`, Export/Import JSON).

A separate Gradebook app (`classwork_evaluations.html`, per-grade evaluations with click-to-reveal scores) was built earlier but was dropped from this repo; development is focused on the Store.

## Timeline of what was built

### 1. Store basics
- Shop of rewards editable by the teacher (initial data from `Point_Store.xlsx`), saved locally.
- Students with individual point balances; select a student to buy items; purchases go to a per-student inventory with counts.
- Give Points: to one student or all, with a grade selector (5th/6th/7th, new grades can be added).
- Students can go negative (debt for bad behavior); Buy is disabled unless balance >= price. Earning points while in debt keeps them negative until paid off. Risk losses never wipe existing debt.
- Points Taken log, with a per-day total.
- Students can be filtered by grade, including on the wheel tab.

### 2. Prize wheel
- Editable prizes and % chance; wheel shows colors only (no text); segment colors editable.
- **Risk It:** 50% fail loses the prize; success spins again and the pot accumulates (win 10, risk, win 10 = 30). Risking never deducts below the pot.
- **Lucky Wheel:** a teacher-set % chance that a spin becomes a Lucky spin with better prizes.
- Prizes can be real shop items that go into the winner's inventory; a **Random Item** prize picks a shop item weighted by price (cheap items likelier).
- Win-modal bug fixed: the spin button used to pass the click event as the multiplier (NaN, "no points").

### 3. Halloween mode
- Candy item (base cost 50 pts); extra point prizes (10 and a 200 jackpot).
- **Trick or Treat doors** with editable odds: treat (candy or random 1-100 bonus), trick (hand your streak to a random classmate of the same grade), rare door (candy to you and 4 classmates), lose everything, back to spin, lose random 1-100, nothing.
- **Web** slice (lose everything won so far) and **Web Stash** (accumulating pot, 10 pts seeded if empty, collectable via a wheel slice or door).

### 4. Christmas mode
- **Trees:** one per grade, shown only for the class spinning; ornaments added by wins.
- **Snowmen:** per student; collect pieces, finish for an editable reward plus the **Christmas Miracle** roll (25% none, 25% open a present, 40% Hot Cocoa, 10% Elf Helper).
- **Presents:** pick one of three; a separate editable prize list with no store-point prizes by default, except the later jackpot. Defaults (sum 100%): Ornament 20.55, Snowman 20.55, Elf Helper 10.72, Hot Cocoa 10.72, Candy 7.15, 1 Bonus Point 6.25, Mystery Gift (random item) 7.96, Store Points Jackpot 10 (random 100-1000), Surprise Gift 1 (random item up to 10,000), Christmas Spirit 5 (ornament + snowman piece), Ultimate Christmas Present 0.1.
- **Ultimate Christmas Present:** hidden unique "Skip the Final Test" item, only won this way.
- **Buffs:** Hot Cocoa (+10 points on the next 3 winning spins, automatic). **Elf Helper** (x2) is saved until used: after a Christmas prize is decided, the student is asked whether to spend one to double it.
- Rare slices (Spirit, Ultimate, Surprise Gift, Jackpot) keep their exact % when the other odds are edited (`fitRarePrizes`).

### 5. Naughty wheel (punishment)
- All slices equally likely: 1 "Saved" (nothing happens), flat losses -10/-25/-50/-75/-100 (editor max 100), % losses -10/-20/-30/-50 (max 50%).
- No cap on actual loss; unlimited debt; a % slice does nothing if the balance is 0 or less. Confirm before spinning, with Undo.
- Special modes (Halloween/Christmas/Naughty) are mutually exclusive.

### 6. Gradebook (dropped from the repo)
- Was a separate file with per-grade evaluations and hidden scores; no longer maintained here.

### 7. Random student picker
- Picks a random student from a chosen grade; no repeats in a session, with a reset-session option.
- Opened from both the Store toolbar (`randomStudentBtn`) and the Prize Wheel toolbar (`wheelRandomStudentBtn`); both call `openRandomModal()`.

### 8. Default example data (Nov 2026)
- Fresh installs (no `pointStoreData_v2` in localStorage) start with one grade `Test` (shown as "Test Grade") and one student `Test Student` (100 points, selected), so a new teacher can try everything immediately. Defined by `DEFAULT_GRADES` and `DEFAULT_STUDENTS`. Saved or imported data is never touched; the old v1 migration still uses `DEFAULT_GRADES`.
- Previously the defaults were grades 5th/6th/7th with no students.
- Removed class-specific default shop items ("Change a normal day class to Modern History / Little Alchemy 2 tournament", "Double points card", "Triple points card") so the defaults make sense to any teacher. Existing saved stores keep whatever items they have.

### 9. Verification and tuning
- Pick rates for all wheels were checked against their stated %; the wheel's landing matches the awarded prize; Risk is 50/50.
- Students winning big on the Normal wheel: ~15% of Normal spins hit 50/100 prizes, the Lucky Wheel supplies much of the points (avg ~23 pts/spin). Possible levers were suggested (lower Lucky chance, smaller 50/100 slices, bigger Nothing slice) but none were applied.
- Random Item weights floor at 1, so very expensive items are as likely as ~1000 pts ones; offered to change, not requested.

## Technical notes

- State in `localStorage`; functions `currentState()`, `persist()`, `loadState()`. One-time migrations use boolean flags in the saved state (e.g. `halloweenExtrasAdded`, `presentsNoPointsMigrated`, `presentsRareMigrated`, `presentsCappedMigrated`, `presentsPointsMigrated`) and set `halloweenExtrasJustAdded = true` to force a save.
- Prize object: `{id, label, points, percent, itemId, color}`. Special `itemId` values: `CANDY`, `RANDOM`, `RANDOM_CAPPED`, `RANDOM_POINTS`, `WEB`, `STASH`, `ORNAMENT`, `SNOWMAN`, `SPIRIT`, `PRESENT`, `BUFF_DOUBLE`, `BUFF_COCOA`, `ULTIMATE`, `NAUGHTY_SAVED/FLAT/PCT`, `@BONUS_POINT` (placeholder resolved by item name).
- Item: `{id, name, price, note, weight, special, hidden}`. Key functions: `pickPrize(pool)`, `pickRandomShopItem(maxPrice)`, `resolvePrizeItem`, `applyChristmasPrize(s, prize, opts)`, `elfCanBoost`, `askElfHelper`, `resolvePresent`, `applyNaughtyPrize`, `fitRarePrizes`.
- Grade names are stored bare (`5th`); the UI appends " Grade". A grade can be deleted only when empty and not the last one.
- `localStorage` does not work from `data:` previews; to test in a browser, serve the folder (e.g. `python -m http.server`) and open `http://localhost:<port>/point_store.html`.
- Testing used jsdom simulations (`npm install jsdom`); DOM spins are slow, so use small samples. Those test scripts are not included in this folder.

## Repo files

- `point_store.html` — the app.
- `README.md` — detailed, non-technical teacher guide (keep it in sync when UI changes).
- `CONTEXT.md` — this file.
- `.gitignore` — blocks `*.json` so exported backups with real student names are never committed.

## Open ideas / not done

- **Nice Meter:** only brainstormed, never specified or built.
- Normal-wheel generosity tuning (see section 9).
- Price-based weighting for Random Item.
