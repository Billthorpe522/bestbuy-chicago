# Best Buy Chicago — HVAC Repipe Tracker

Multi-unit job tracker for Job # 262302 — 10 condensing/AHU pairs.

## Live URLs (once pushed)

| View | URL |
|------|-----|
| **Mobile** | https://billthorpe522.github.io/bestbuy-chicago/dashboard-mobile.html |
| **Desktop** | https://billthorpe522.github.io/bestbuy-chicago/dashboard-desktop.html |
| **Daily Log** | https://billthorpe522.github.io/bestbuy-chicago/daily-log.html |
| **Master RFI** | https://billthorpe522.github.io/bestbuy-chicago/master-rfi.md |

Password (all views): `Emcor`

## Push instructions (force-push over old single-file index.html)

From your own terminal (NOT from Hermes — git push hangs in this env):

```bash
cd /f/Evil\ Droid/Evil\ Droid/workspace/bestbuy-chicago
git init -q -b main
git add dashboard-mobile.html dashboard-desktop.html daily-log.html master-rfi.md checklists/ README.md
git commit -m "Best Buy Chicago - re-skin to SPM dark theme, 6-milestone per-AHU, TWE service section, 10 checklists" -q
git remote add origin https://github.com/Billthorpe522/bestbuy-chicago.git
git branch -M main
git push -u origin main --force
```

The `--force` is needed because the existing repo has the old single-file `index.html`. We're replacing it with the multi-file structure.

Then in repo Settings → Pages → Source: `main` / root.

## What's in this folder

```
workspace/bestbuy-chicago/
├── dashboard-mobile.html        # Mobile (foreman's phone view), 10 unit cards + TWE service
├── dashboard-desktop.html       # Desktop (PM's laptop view), unit stage matrix + TWE phases
├── daily-log.html               # Add days as work happens (localStorage)
├── master-rfi.md                # 5 RFIs pre-seeded (5/16", 7/8", #7 liquid, #9/#10 plans, TWE Phase 4)
├── checklists/                  # 10 per-AHU checklists
│   ├── ahu-01.md  (20T, reuse, TWE affected)
│   ├── ahu-02.md  (20T, partial, TWE affected)
│   ├── ahu-03.md  (20T, reuse, TWE affected)
│   ├── ahu-04.md  (20T, reuse, TWE affected)
│   ├── ahu-05.md  (20T, partial, TWE affected)
│   ├── ahu-06.md  (15T, reuse)
│   ├── ahu-07.md  (2-5T, partial)
│   ├── ahu-08.md  (2-5T, partial)
│   ├── ahu-09.md  (2-5T, full-repipe)
│   └── ahu-10.md  (2-5T, partial)
├── _old-light-theme.html        # Archive of the previous teal+white site
└── README.md
```

## What changed vs the old version

- **Theme:** light (teal+white) → dark (matches Loyola / SPM aggregator)
- **Layout:** single-page → mobile + desktop variants
- **Checklist items:** 4 per unit (Installed/Piped/Wired/Started) → **6 per unit** (Demo unit, Demo piping, Install unit, Install piping, Pressure test, Charge / startup)
- **TWE Condensate Service section:** added at the bottom with 7 phases (incl. Phase 0 EMERGENCY) + per-unit sign-off for AHU-1 through AHU-5
- **Daily Log + Master RFI:** added (Loyola parity)
- **10 per-AHU checklists:** added in `checklists/`

## Companion artifacts (not in this repo)

| File | Path |
|------|------|
| Vault master note | `Day Job — Emcor/Best Buy Chicago HVAC Repipe.md` |
| TWE action plan HTML | `Day Job — Emcor/Best Buy - TWE Condensate Action Plan.html` |
| TWE action plan MD | `Day Job — Emcor/Best Buy - TWE Condensate Drainage Issue.md` |
| IOM drop folder | `Day Job — Emcor/Best Buy IOMs/` (TWE-1, TTA-1, BAYDRKT010 install guide) |