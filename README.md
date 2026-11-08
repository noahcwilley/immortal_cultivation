# Immortal Cultivation

A work-in-progress Crusader Kings III mod about finding a cultivation master, developing your cultivation, and extending your character's lifespan.

The current focus is a complete Qi Condensation progression loop. This is also a learning project, with mechanics being built and tested incrementally.

## Current features

- **Search for a Master.** Characters without a cultivation trait can seek a master and choose whether to begin cultivating.
- **Two progression tracks.** Subrealm represents progress within a cultivation realm, while Quality represents the quality of that cultivation.
- **Qi Condensation.** Ten Subrealm stages and five Quality stages grant increasing lifespan and prowess bonuses.
- **Home seclusion.** Enter or leave seclusion through decisions. An active story in the Situations interface displays your Subrealm and Quality.
- **Qi mote encounters.** Outside seclusion, Qi Condensation cultivators can encounter a mote of Qi and choose whether to absorb it. Success improves cultivation, while failure causes death. Subrealm and Quality can improve the success odds.
- **Custom artwork.** Cultivation trait icons, a seclusion illustration and icon, and a custom event theme with a cultivation header badge.

## Playing the current version

1. Take **Search for a Master** and accept the master's gift to gain Qi Condensation. The trait is also available in Ruler Designer.
2. Take **Enter Seclusion** to begin monthly practice.
3. Open **Situations** to inspect your seclusion story and its progress counters.
4. Take **Exit Seclusion** to end the session and resume receiving eligible Qi mote encounters.

### Current balance

These values are provisional and may change during development.

| Mechanic | Current behavior |
|---|---|
| Seclusion practice | +1 Subrealm XP per month |
| Seclusion cost | −10 General Opinion and −15% monthly lifestyle XP gain modifier |
| Quality during seclusion | No automatic monthly gain |
| Qi mote availability | 20% chance per quarterly check for an eligible player character |
| Absorption success | Base success weight 70 against failure weight 30 |
| Success bonuses | Success weight is multiplied by 1.5 at 10 Subrealm XP and again at 50 Quality XP |
| Successful absorption | Adds 100 Subrealm XP and raises Quality to 50 XP if it is below 50 |
| Failed absorption | Character dies |

Both trait tracks use a 0–100 XP scale. The Qi Condensation story converts those values into stage numbers. Subrealm 9 covers 80–99 XP, and Subrealm 10 is reached at 100 XP.

## Development status

The mod descriptor targets **CK3 1.20.1.2**, with mod version **0.1**. English localization is included.

Qi Condensation is the primary development and testing focus. Foundation Establishment has a trait definition, icon, and XP support, but its progression and story display are still being developed. Realm breakthroughs are a future design area.

The current decisions and encounter pulse target player-controlled characters. Wider AI participation and compatibility with other mods require further development and testing. The mod is being developed on Linux; Windows and macOS testing is still needed.

## Local installation

1. Download or clone this repository.
2. Use the CK3 launcher's mod tools to create a local mod named **Immortal Cultivation**.
3. Copy this repository's contents into that mod's folder, with `descriptor.mod`, `common/`, `events/`, `gfx/`, and `localization/` directly inside it.
4. Add the local mod to a playset, enable it, and launch CK3.

For a standard native Linux installation, the user mod directory is usually:

```text
~/.local/share/Paradox Interactive/Crusader Kings III/mod/
```

## Repository layout

```text
common/
  decisions/             Player decisions
  event_backgrounds/     Event illustration definitions
  event_themes/          Event presentation, icons, and sounds
  modifiers/             Seclusion effects
  on_action/             Recurring encounter checks
  scripted_effects/      Reusable XP and progress-display effects
  story_cycles/          Monthly seclusion logic and counters
  traits/                Cultivation realms and XP tracks
events/                  Master and Qi mote encounters
gfx/                     Icons and illustrations
localization/english/    English interface text
descriptor.mod           Mod metadata
```

## Reporting problems

Include your CK3 version, enabled mods, the action that caused the problem, and the relevant portion of `logs/error.log`. For crashes, include the corresponding crash report if available. Screenshots of trait tracks and story counters help diagnose progression issues.

## Artwork

Custom cultivation illustrations and icons were generated with AI assistance and converted to DDS for use in CK3. Event themes also reference existing CK3 interface and audio assets.
