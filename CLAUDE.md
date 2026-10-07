# Workout app (repo: ppl-log)

Personal workout tracker PWA for my home gym (3 full-body days A/B/C + running), on GitHub Pages
(quidding1.github.io/ppl-log/), wrapped as an APK (package io.github.quidding1.twa).

- index.html is the whole app (HTML, CSS, JS, plan data). No build step.
- sw.js: bump CACHE ("ppl-log-v10" → "ppl-log-v11"…) on every change.
- Data in localStorage key "ppl-log-v2". Never lose logged history: use migrations.
- Equipment: threaded barbell, plates (15/10/5 kg pairs + 1 kg plates), 2 dumbbell
  handles, doorway pull-up bar, dip bar, stairs, foldable bench (no leg extension
  or leg curl attachment), exercise bike.
- UI in English, black minimal style, Barlow fonts.

## Plan
- Day keys stay push/pull/legs internally (colours, history) but are named Day A, B, C.
- PLAN_VER 3 = full-body plan; each muscle is trained about every 2 days. Runs go in the
  Cardio tab (default activity: run) on the days between lifting.

## Features worth knowing
- Muscles: MUSCLE_MAP (by exercise id) and GUESS (by name) give main + helper muscles;
  an exercise's own `m` field overrides them (set in the plan editor). Body tab shows a
  front/back muscle map coloured by sets in the last 7 days or in the plan.
- Two-sided exercises: `side:true` on a plan exercise. First tick = left side done
  (set gets `l:true`, switch timer `settings.switchRest`), second tick = set done.
- Skip for today: ids in the day's draft `skip` array. Remove from plan keeps history
  through `retire()`.
