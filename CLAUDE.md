# Workout app (repo: ppl-log)

Personal Push/Pull/Legs tracker PWA for my home gym, on GitHub Pages
(quidding1.github.io/ppl-log/), wrapped as an APK (package io.github.quidding1.twa).

- index.html is the whole app (HTML, CSS, JS, plan data). No build step.
- sw.js: bump CACHE ("ppl-log-v8" → "ppl-log-v9"…) on every change.
- Data in localStorage key "ppl-log-v2". Never lose logged history: use migrations.
- Equipment: threaded barbell, plates (15/10/5 kg pairs + 1 kg plates), 2 dumbbell
  handles, doorway pull-up bar, dip bar, stairs, foldable bench (no leg extension
  or leg curl attachment), exercise bike.
- UI in English, black minimal style, Barlow fonts.