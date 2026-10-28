# Harvest All The Tails - 1.7 Race Support

![RimWorld](https://img.shields.io/badge/RimWorld-1.7-orange) ![Stage](https://img.shields.io/badge/stage-beta.1-purple) ![License](https://img.shields.io/badge/license-MIT-green)

Natural tail harvesting and transplantation for supported humanoid anatomy.

## Changes - 1.7.0-beta.1

- Rebuilt runtime assembly for RimWorld 1.7 / .NET 10.
- Added generic tail, Tozol tail, Yanzihko tail and xenomorph tail harvesting and installation.
- Added Logann, Ferrex and Xenomorph Type coverage.
- The generic tail install recipe also accepts race-supplied `Tail` items.
- Reused native Dogbold, Foxbold and Orassan tail items.
- Added anatomy-based surgery availability across installed humanoid races.
- Retained upstream conditional race modules.
- Added separate package identity and incompatibility with the original.

## Race coverage

The current mod list contains 51 humanoid race definitions. 23 have actual tail parts.

Added coverage includes Vulpoids, Lombax, Kisalfar, Fressalfar, Yanzihko felines, Tozol, Frosty Dragon, Dogbolds, Foxbolds, Orassans, Logann, Ferrex, Xenomorph Type and the tailed Big and Small bodies. Matching tail types share an item; different anatomical tail types do not.

**Visual-only tails are not anatomical parts.** Anthro Race variants and xenotype/gene-only appearances with no tail BodyPartRecord have no tail to amputate or transplant. No body structure or gene is invented or changed. See [race coverage](RACE-COVERAGE.md).

## Load order

Harmony -> race mods -> this fork -> Harvest Everything (original or fork) -> Harvest Organs Post Mortem -> compatibility patches.

The new recipes require the matching tail part. Post Mortem retains its own corpse condition and success rules. Ordinary animal transplantation is outside this humanoid-race extension; the Harvest Everything fork handles butchering animal corpses for organs.

## Credits and distribution

Original project: [EspioIdsavant/Harvest-All-The-Tails](https://github.com/EspioIdsavant/Harvest-All-The-Tails). Original credits and MIT license retained. 1.7 maintenance: Cupears.

A new Workshop item is required; the original PublishedFileId is not included as publishing metadata.

## Repository layout

| Path | Purpose |
|---|---|
| `1.7/` | RimWorld 1.7 content (Assemblies) |
| `About/` | Mod metadata and preview image |
| `Races17/` | Insect tail patches (def-driven fallback) |
| `Source17/` | C# source for the 1.7 build |
| `tools/` | Packaging script |
| `Kurin/`, `Revia/`, `Moyo/`, `Dragonian/`, `DragonianUnofficial/`, `Silkiera/`, `Ratkin/`, `Kiiro/`, `Rabbie/`, `Glassy/`, `Mofy/`, `Heruan/`, `Nyaron/` | Race modules for HAR and anthro races |
| `BigSmall/`, `Dogbold/`, `Foxbold/`, `Orassan/`, `Tozol/`, `Yanzihko/`, `Xenomorph/` | Race modules for tailed non-HAR races |

## Build

Requires the .NET 10 SDK, RimWorld 1.7 and Harmony.

```powershell
dotnet build Source17/Mod.csproj -c Release -p:RimWorldDir="M:/Steam/steamapps/common/RimWorld" -p:HarmonyPath="M:/Steam/steamapps/workshop/content/294100/2009463077/1.7/Assemblies/0Harmony.dll"
```

Game and Harmony assemblies are referenced locally and are not included in the 1.7 package.

## Installation

Enable the fork instead of the original. Both versions are declared incompatible to prevent duplicate content. Keep Harmony enabled. Existing upstream item names are retained.
