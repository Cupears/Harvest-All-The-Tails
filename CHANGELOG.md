## Changes - 1.7.0.2

- Merged into Harvest Everything + Tails; the standalone tails mod is deprecated and not needed if you use Harvest Everything.
- About metadata and README now point users at Harvest Everything + Tails.
- The merged mod and this package declare each other incompatible.
- Moved every race module under `Races/`; load gating is unchanged.
- No functional changes in this repository; development continues in [Cupears/HarvestEverything](https://github.com/Cupears/HarvestEverything).

## Changes - 1.7.0-beta.1

- Rebuilt runtime assembly for RimWorld 1.7 / .NET 10.
- Added generic tail, Tozol tail, Yanzihko tail and xenomorph tail harvesting and installation.
- Added Logann, Ferrex and Xenomorph Type coverage.
- The generic tail install recipe now also accepts race-supplied `Tail` items.
- Fixed job-string typos in the race patches.
- Reused native Dogbold, Foxbold and Orassan tail items.
- Added anatomy-based surgery availability across installed humanoid races.
- Retained upstream conditional race modules.
- Added separate package identity and incompatibility with the original.
