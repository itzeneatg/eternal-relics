# EternalRelics

A production-ready Minecraft Paper 1.21.11 plugin featuring legendary items, faction events, and cinematic PvP systems.

## Features

### Core Systems
- **Legendary Armor System** - Unique pieces with special abilities and statistics
- **Legendary Weapon System** - 15+ legendary weapons with active and passive abilities
- **Event & Faction System** - Humans, Cult, and Void factions with dynamic gameplay
- **Altar System** - Craft legendary items on interactive altars with holographic displays
- **Fragment Event System** - Timed events with fragment collection and player tracking
- **GUI Recipe System** - Interactive recipe viewer with item information
- **Cooldown Management** - BossBar-based cooldown UI for all abilities
- **Persistence Layer** - SQLite database with JSON fallback for item tracking
- **Resource Pack Integration** - Custom models, textures, and particle effects

### Legendary Armor
- **Sun Crown** - Helmet with solar-themed abilities
- **Heart of Avaritia** - Chestplate with greed-based mechanics
- **Golden Time Steppers** - Leggings with temporal abilities
- **Footsteps of Midas** - Boots with wealth-based effects

### Legendary Weapons (15 total)
Frostwind Bow, Voidguard Shield, Ironhowl, Bonecracker, Abyssal Sword, Phantom Edge, Crystal Edge, Mooncleaver, Nightfang, Ghostthorn, Titan's Axe, Oblivion Cleaver, Thundermaul, Sunreaver, Void Harvest

## Installation

1. Build the project:
   ```bash
   mvn clean package
   ```

2. Place the generated JAR in your Paper server's `plugins/` directory

3. Restart the server to generate configuration files

4. Configure `config.yml` as needed

5. Install the resource pack from `resourcepack/` directory

## Configuration

All systems are configurable via `config.yml`:
- Cooldown timings
- Damage values
- Drop chances
- Crafting windows (default: 16:00-19:00 CET)
- Particle effects
- Custom messages
- Event spawn caps

## Commands

### Admin Commands
- `/altar <helmet|chestplate|leggings|boots|weapon>` - Craft legendary items
- `/event <armor_type>` - Start fragment collection events
- `/king <player>` - Assign human faction king
- `/void awaken` - Start void faction event

### Player Commands
- `/recipes` - View legendary item recipes
- `/relicinfo` - Get information about legendary items

## Project Structure

```
eeternal-relics/
├── src/main/java/com/itzeneatg/eternalrelics/
│   ├── EternalRelics.java                 (Main plugin class)
│   ├── managers/                          (Core system managers)
│   ├── items/                             (Legendary item definitions)
│   ├── abilities/                         (Ability implementations)
│   ├── events/                            (Event listeners)
│   ├── commands/                          (Command handlers)
│   ├── guis/                              (GUI systems)
│   ├── persistence/                       (Data storage)
│   ├── utils/                             (Utility classes)
│   └── config/                            (Configuration handling)
├── src/main/resources/
│   ├── plugin.yml                         (Plugin manifest)
│   ├── config.yml                         (Default configuration)
│   └── messages.yml                       (Localization)
├── resourcepack/                          (Resource pack files)
└── pom.xml                                (Maven build configuration)
```

## Requirements

- **Java 21** or higher
- **Paper 1.21.11** or compatible
- **SQLite** (bundled via JDBC)

## Performance

- Optimized for 100+ concurrent players
- Efficient particle systems with configurable limits
- Async-safe persistence layer
- Cooldown tracking without entity scans
- Optimized ability detection using metadata

## Development

The codebase follows clean architecture principles:
- Manager/Service pattern for core systems
- Separation of concerns with dedicated modules
- Comprehensive configuration system
- Full JavaDoc comments
- Async-safe operations

## License

Closed Source - For private server use

## Support

For issues and feature requests, visit the GitHub repository.
