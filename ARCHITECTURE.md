# Architecture Overview

## Package Structure

```
com.itzeneatg.eternalrelics/
├── EternalRelics.java                 (Main plugin class)
├── managers/
│   ├── CooldownManager.java
│   ├── LegendaryItemManager.java
│   ├── AltarManager.java
│   ├── EventManager.java
│   ├── FactionManager.java
│   ├── EffectManager.java
│   └── GuiManager.java
├── items/
│   ├── LegendaryArmor.java
│   ├── LegendaryWeapon.java
│   ├── Fragment.java
│   └── Relic.java
├── abilities/
│   ├── ArmorAbility.java
│   ├── WeaponAbility.java
│   └── implementations/
├── events/
│   ├── PlayerInteractListener.java
│   ├── DamageListener.java
│   ├── InventoryListener.java
│   ├── BlockListener.java
│   └── EntityListener.java
├── commands/
│   ├── AltarCommand.java
│   └── (5 more command classes)
├── guis/
│   ├── RecipesGui.java
│   └── (GUI implementations)
├── persistence/
│   ├── PersistenceManager.java
│   ├── SqliteDatabase.java
│   └── DataCache.java
├── config/
│   └── ConfigManager.java
└── utils/
    ├── MessageUtils.java
    └── ParticleUtils.java
```

## Core Managers

**CooldownManager**
- Tracks ability cooldowns without entity scans
- Provides BossBar-based UI
- Async-safe cooldown cleanup

**LegendaryItemManager**
- Global item tracking (one per server)
- CustomModelData registration
- Indestructible item properties

**AltarManager**
- Altar placement and holographic displays
- Recipe validation
- Crafting logic coordination

**EventManager**
- Fragment event timing
- Crafting window management
- Broadcast coordination

**FactionManager**
- Faction membership tracking
- Role assignment
- King/Leader management

**EffectManager**
- Centralized VFX/SFX
- Particle density control
- Sound effect playback

**GuiManager**
- Recipe viewer GUI
- Item display systems
- Interactive menu handling

## Configuration System

All settings in `config.yml`:
```yaml
crafting-window:
  enabled: true
  start-hour: 16
  end-hour: 19
  timezone: CET

fragments:
  spawn-cap: 5
  drop-chance: 0.15

particles:
  enabled: true
  item-held-density: 10

persistence:
  type: sqlite
  auto-save-interval: 600
```

## Persistence Layer

**SQLite Primary**
- `legendary_items` table
- `player_data` table
- `fragments` table

**Features**
- Auto-save intervals
- Crash-safe design
- JSON fallback support

## Performance Targets

- Support 100+ concurrent players
- Efficient cooldown cleanup (30s intervals)
- Configurable particle density
- Optimized entity scanning
- Async-safe operations
