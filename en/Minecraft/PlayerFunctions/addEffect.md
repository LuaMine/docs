# player:addEffect(name, duration, amplifier)
Applies a potion effect to the player.

| Param       | Type   | Description                                                    |
|-------------|--------|------------------------------------------------------------------|
| `name`      | string | Effect name (Bukkit `PotionEffectType`, e.g. `"SPEED"`, `"REGENERATION"`) |
| `duration`  | number | Duration in server ticks (20 ticks = 1 second)                    |
| `amplifier` | number | *(optional)* Effect level, 0 = level I. Defaults to `0`.           |

Unknown effect names are silently ignored.

```lua
player:addEffect("SPEED", 200, 1) -- Speed II for 10 seconds
```
