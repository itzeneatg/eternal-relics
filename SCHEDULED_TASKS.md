# Scheduled Tasks Overview

## CraftingWindowTask
**Purpose**: Manages crafting window broadcasts and timing

**Broadcasts**:
- 15:50 CET: "Crafting window opens in 10 minutes"
- 15:55 CET: "Crafting window opens in 5 minutes"
- 16:00 CET: "Crafting window is now OPEN" (Beacon activate + Pling sound)
- 18:50 CET: "Crafting window closes in 10 minutes"
- 18:55 CET: "Crafting window closes in 5 minutes"
- 19:00 CET: "Crafting window is now CLOSED" (Wither spawn sound)

**Configuration**:
- Timezone: CET (configurable)
- Window duration: 3 hours (16:00-19:00)
- Sound effects enabled/disabled

## FragmentTrackerTask
**Purpose**: Tracks fragment holder locations

**Interval**: Every 50 seconds

**Broadcast Format**:
```
[Fragment Holder] PlayerName is at X: 1234 Y: 64 Z: 5678
```

**Requirements**:
- Fragment event must be active
- Player must be online
- Fragment must be in inventory

## CooldownCleanupTask
**Purpose**: Periodic cleanup of expired cooldowns

**Interval**: Every 30 seconds (600 ticks)

**Operations**:
- Remove expired cooldowns
- Clean empty player maps
- Async execution to prevent lag

## AltarParticleTask
**Purpose**: Display rotating item and particles above altars

**Interval**: Every tick (20 times per second)

**Effects**:
- Rotate item display
- Spawn altar particles
- Update hologram text
- Play ambient sounds

## Configuration

```yaml
scheduled-tasks:
  crafting-window-check: 100  # ticks between checks
  fragment-tracking: 1000     # 50 seconds
  cooldown-cleanup: 600       # 30 seconds
  altar-particles: 1          # every tick
```

## Performance Considerations

- All tasks are configurable
- Async execution where safe
- No blocking operations
- Efficient data structures
- Early exit conditions

## Example Task Implementation

```java
public class CustomTask implements Runnable {
    private final EternalRelics plugin;
    private int taskId;
    
    public void start() {
        taskId = plugin.getServer().getScheduler()
            .scheduleSyncRepeatingTask(
                plugin,
                this,
                0L,      // delay
                20L      // period (1 second)
            );
    }
    
    @Override
    public void run() {
        // Task logic here
    }
}
```
