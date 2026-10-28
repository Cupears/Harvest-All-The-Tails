# Harvest All The Tails - 1.7 Race Support

> **Merged into Harvest Everything + Tails.**
>
> **You do not need this mod if you use [Harvest Everything + Tails](https://github.com/Cupears/HarvestEverything).**
> That mod already contains every tail, race module and recipe from this one, plus
> body-part harvesting and animal butchering. Install that instead of this.
>
> This mod is no longer needed as a standalone package and is no longer maintained here.
> Do not enable both together; they are declared incompatible. This repository remains
> available for the original source history and MIT-licensed content.

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

If you are using Harvest Everything + Tails, this mod is not part of the load order at all.
That mod only needs:

Harmony -> race mods -> Harvest Everything + Tails -> Harvest Organs Post Mortem -> compatibility patches.

The rest of this section applies only to the deprecated standalone build:

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
| `Races/` | Per-race modules; each one is only loaded when its race mod is active |
| `Source17/` | C# source for the 1.7 build |
| `tools/` | Packaging script |
| `Races/Kurin/`, `Races/Revia/`, `Races/Moyo/`, `Races/Dragonian/`, `Races/DragonianUnofficial/`, `Races/Silkiera/`, `Races/Ratkin/`, `Races/Kiiro/`, `Races/Rabbie/`, `Races/Glassy/`, `Races/Mofy/`, `Races/Heruan/`, `Races/Nyaron/` | Race modules for HAR and anthro races |
| `Races/BigSmall/`, `Races/Dogbold/`, `Races/Foxbold/`, `Races/Orassan/`, `Races/Tozol/`, `Races/Yanzihko/`, `Races/Xenomorph/` | Race modules for tailed non-HAR races |
| `Races/InsectTails/` | Insect tail patches (def-driven fallback) |

## Build

Requires the .NET 10 SDK, RimWorld 1.7 and Harmony.

```powershell
dotnet build Source17/Mod.csproj -c Release -p:RimWorldDir="M:/Steam/steamapps/common/RimWorld" -p:HarmonyPath="M:/Steam/steamapps/workshop/content/294100/2009463077/1.7/Assemblies/0Harmony.dll"
```

Game and Harmony assemblies are referenced locally and are not included in the 1.7 package.

## Installation

**Use [Harvest Everything + Tails](https://github.com/Cupears/HarvestEverything) instead.**
It includes this entire mod, so a separate tails mod is not needed.

If you are still on the standalone build, enable this fork instead of the original. The
original, this fork and Harvest Everything + Tails are declared incompatible to prevent
duplicate content. Keep Harmony enabled. Existing upstream item names are retained.
