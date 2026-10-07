# Workout app (repo: ppl-log)

Personal workout tracker PWA for my home gym: Push/Pull/Legs twice a week (6 days) + 2–3 easy runs, on GitHub Pages
(quidding1.github.io/ppl-log/), wrapped as an APK (package io.github.quidding1.twa).

- index.html is the whole app (HTML, CSS, JS, plan data). No build step.
- sw.js: bump CACHE ("ppl-log-v11" → "ppl-log-v12"…) on every change.
- Data in localStorage key "ppl-log-v2". Never lose logged history: use migrations.
- Equipment: threaded barbell, plates (15/10/5 kg pairs + 1 kg plates), 2 dumbbell
  handles, doorway pull-up bar, dip bar, stairs, foldable bench (no leg extension
  or leg curl attachment), exercise bike.
- UI in English, black minimal style, Barlow fonts.

## Plan
- PLAN_VER 4: Push / Pull / Legs, rotated twice a week, weekly goal 6 sessions.
  About 12 sets per muscle per week. Runs go in the Cardio tab (default activity: run),
  e.g. Monday and Thursday after push, not the day before legs.

## Features worth knowing
- Muscles: MUSCLE_MAP (by exercise id) and GUESS (by name) give main + helper muscles;
  an exercise's own `m` field overrides them (set in the plan editor). Body tab shows a
  front/back muscle map coloured by sets in the last 7 days or in the plan.
- Two-sided exercises: `side:true` on a plan exercise. First tick = left side done
  (set gets `l:true`, switch timer `settings.switchRest`), second tick = set done.
- Skip for today: ids in the day's draft `skip` array. Remove from plan keeps history
  through `retire()`.
