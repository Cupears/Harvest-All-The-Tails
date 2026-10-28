# Harvest All The Tails â€” 1.7 Race Support

![RimWorld](https://img.shields.io/badge/RimWorld-1.7-orange) ![Stage](https://img.shields.io/badge/stage-beta.1-purple) ![License](https://img.shields.io/badge/license-MIT-green)

Natural tail harvesting and transplantation for supported humanoid anatomy.

## Changes â€” 1.7.0-beta.1

- Rebuilt runtime assembly for RimWorld 1.7 / .NET 10.
- Added generic tail, Tozol tail and Yanzihko tail harvesting and installation.
- Reused native Dogbold, Foxbold and Orassan tail items.
- Added anatomy-based surgery availability across installed humanoid races.
- Retained upstream conditional race modules.
- Added separate package identity and incompatibility with the original.

## Race coverage

The current mod list contains 46 humanoid race definitions. 19 have actual tail parts.

Added coverage includes Vulpoids, Lombax, Kisalfar, FressÃ¤lfar, Yanzihko felines, Tozol, Frosty Dragon, Dogbolds, Foxbolds, Orassans and the tailed Big and Small bodies. Matching tail types share an item; different anatomical tail types do not.

**Visual-only tails are not anatomical parts.** Anthro Race variants and xenotype/gene-only appearances with no tail BodyPartRecord have no tail to amputate or transplant. No body structure or gene is invented or changed. See [race coverage](RACE-COVERAGE.md).

## Load order

Harmony â†’ race mods â†’ this fork â†’ Harvest Everything (original or fork) â†’ Harvest Organs Post Mortem â†’ compatibility patches.

The new recipes require the matching tail part. Post Mortem retains its own corpse condition and success rules. Ordinary animal transplantation is outside this humanoid-race extension.

## Credits and distribution

Original project: [EspioIdsavant/Harvest-All-The-Tails](https://github.com/EspioIdsavant/Harvest-All-The-Tails). Original credits and MIT license retained. 1.7 maintenance: Cupears.

A new Workshop item is required; the original PublishedFileId is not included as publishing metadata.

## Build

Requires the .NET 10 SDK, RimWorld 1.7 and Harmony.

```powershell
dotnet build Source17/Mod.csproj -c Release -p:RimWorldDir="M:/Steam/steamapps/common/RimWorld" -p:HarmonyPath="M:/Steam/steamapps/workshop/content/294100/2009463077/1.7/Assemblies/0Harmony.dll"
```

Game and Harmony assemblies are referenced locally and are not included in the 1.7 package.

## Installation

Enable the fork instead of the original. Both versions are declared incompatible to prevent duplicate content. Keep Harmony enabled. Existing upstream item names are retained.

## Testing

493 automated checks passed against the current 1.7 game assemblies and 46 humanoid race definitions: XML patch application, repeat application without duplicates, existing tail items, exact anatomical matching and surgery hook binding. Live startup validation passed across 768 living humanoid definitions, including runtime-generated races: 18 tail surgery definitions, no missing tail mappings and no mod startup errors. Full surgery outcomes and visual tail disappearance still need colony testing.
