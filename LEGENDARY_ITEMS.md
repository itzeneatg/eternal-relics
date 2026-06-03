# Legendary Items Implementation Guide

## Armor System

### Sun Crown (Helmet)
**Stats**: Netherite armor level with gold appearance

**Passives**:
- Solar flare: Jump with sun fragment
- Heat immunity: Reduced fire damage
- Day powered: Extra effects during daytime

**Visuals**:
- Golden white textures
- Solar particle effects
- Animated glow

### Heart of Avaritia (Chestplate)
**Stats**: Netherite armor level

**Passives**:
- Greed sense: Shows nearby valuable items
- Wealth shield: More protection when holding gold
- Explosion aura: Triggered on taking damage

### Golden Time Steppers (Leggings)
**Stats**: Netherite armor level

**Passives**:
- Speed boost: Enhanced movement
- Double jump: Temporal jump mechanic
- Time slow: Brief slowdown effect

### Footsteps of Midas (Boots)
**Stats**: Netherite armor level

**Passives**:
- Gold trails: Particles on movement
- Wealth walk: Extra speed when wealthy
- Vault access: Special abilities

## Weapon System

### Bow: Frostwind Bow
**Mechanics**:
- Frost arrows on hit
- Slow effect to enemies
- Chain freeze ability
- Cooldown: 15s between charges

**Visuals**:
- Ice blue coloring
- Frost particle trails
- Snowy projectiles

### Shield: Voidguard Shield
**Mechanics**:
- Void absorption
- Reflects damage
- Teleport away on block

### Swords (Multiple)

**Ironhowl**
- Knockback ability
- Howling effect
- AoE damage

**Abyssal Sword**
- True damage on hit
- Void corruption effect
- Teleport slash

**Phantom Edge**
- Ghost abilities
- Phase through blocks
- Invisibility effects

**Crystal Edge**
- Shatter mechanic
- Reflect damage
- Crystallize enemies

**Mooncleaver**
- Moon phase dependent
- Extra damage at night
- Lunar abilities

**Sunreaver**
- Solar damage
- Daylight powered
- Burning effects

### Axes

**Bonecracker**
- Bone effects
- Wither application
- Skeletal summons

**Titan's Axe**
- Massive AoE
- Earthquake effects
- True damage

**Oblivion Cleaver**
- Void-themed
- Black hole summoning
- Instant kill potential

### Specialty

**Ghostthorn (Dagger)**
- Quick strikes
- Poison damage
- Shadow teleport

**Thundermaul**
- Lightning strikes
- Chain damage
- Stun mechanic

**Void Harvest (Scythe)**
- Life steal
- Death reaper theme
- Soul harvesting

## Fragment System

**Fragment of the Sun**
- Drops from Withers
- Event spawning
- Solar crafting ingredient

**Fragment of the Heart**
- Drops from Wardens
- Heart passive requirement
- Blood ritual ingredient

**Fragment of Time**
- Drops from Ominous Vaults
- Temporal crafting
- Rare drops

**Fragment of Gold**
- Drops from Vaults
- Wealth-based crafting
- Common drops

## Relic of Convergence

**Only one exists server-wide**

**Mechanics**:
- 30-minute defense timer
- 200 HP boss object
- Team capture mechanics
- Win condition for factions
- Pickup/drop persistence

**Victory Broadcasts**:
- Humans capture
- Cult captures
- Void captures

## CustomModelData Mapping

```
Helmet variants: 1-10
Chestplate variants: 11-20
Leggings variants: 21-30
Boots variants: 31-40
Sword variants: 41-70
Axe variants: 71-85
Bow variants: 86-95
Shield variants: 96-100
Dagger variants: 101-110
Scythe variants: 111-120
Special: 121+
```

## Crafting Requirements

### Legendary Armor
Each piece requires:
- Specific fragments (varies by piece)
- Rare crafting materials
- Gold blocks
- Enchanted items

### Legendary Weapons
Each weapon requires:
- 2-4 fragments
- Rare materials
- Enchanted books
- Special components

## Item Properties

**All Legendary Items**:
- Indestructible (not damageable)
- Cannot burn in lava
- Cannot receive Curse of Vanishing
- Cannot receive Curse of Binding
- Tradable (not soulbound)
- Global unique tracking

**Persistence**:
- Survives restarts
- Survives crashes
- Survives reloads
- Owner tracked in database
