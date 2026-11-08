# Heroic (Fabric, Minecraft 1.21.1)

All-in-one, data-driven superhero suits and powers. Characters, gems and tech are original designs
(rename freely in the lang files).

## Build
1. Check versions in `gradle.properties` against https://fabricmc.net/develop/
2. Add a Gradle wrapper (`gradle wrapper`) or copy `src/` + build files into a fresh Fabric template.
3. `./gradlew runClient`  /  `./gradlew build` -> `build/libs/heroic-*.jar`

## Keys (all rebindable)
| Key | Action |
|---|---|
| Z / X / C | hero powers 1 / 2 / 3 |
| G / H | cycle / use the selected Core Gem |
| J | The Snap (all six gems socketed) |
| K | Nano suit deploy / retract |
| V / B / N | AEGIS visor on-off / deploy drones / recall drones |

## Suits
- Suit Fabricator (right-click) or `/heroic suit <hero>`. Heroes: Stormwing, Crimson Comet, Shadowveil,
  Ironclad, Emberheart, **Arcwright** (built-in AEGIS AI, drones, repulsor).
- Armor has a dyeable plated base + permanent glowing overlay (arc core, cyan eyes, trim).
- Suits self-repair slowly using energy.

## Core Gems (six, original names)
Vigor (beam), Rift (long blink), Mirage (turns hostile mobs into sheep), Chrono (slows mobs, speeds you),
Psyche (mobs fight each other), Spirit (heal/cleanse allies). Right-click a gem while wearing a hero
chestplate to socket it. Each gem: +30 max energy and faster regen. Craft: nether star + 4 diamonds + dye.
With all six: press J for the Snap — half of all nearby hostile mobs turn to ash (never players),
then you are drained and weakened, 5-minute cooldown.

## Nano system
Craft a **Nano Core** (nether star ring). Wear a full suit and right-click the core (or press K): the suit
folds into the core piece by piece, keeping gems. Press K again to deploy it, boots to helmet.
Ironclad also has the **Nano Shield** power (resistance + regenerating absorption).

## AEGIS (AI) and drones
Wear **AEGIS Glasses** (helmet slot) or the Arcwright suit: threat scanner HUD, spoken-style warnings,
fall assist and emergency shields (suit), plus up to 4 Sentinel Drones that orbit you, shoot hostile
mobs, swat incoming projectiles and give you Resistance.

## City
`/heroic city [3-7]` (OP) builds a Manhattan-style city around you: roads, glass towers, apartments,
parks, plazas and the central Arc Tower with glowing rings and a landing pad. Use a flat area.
`/heroic drones` spawns test drones.

## Extending
Hero JSON (`data/<ns>/heroes/<name>.json`): `color`, `powers` (max 3), `max_energy`, optional `ai: true`.
Addon powers: extend `com.heroic.power.Power` and call `PowerRegistry.register(id, power)`.
