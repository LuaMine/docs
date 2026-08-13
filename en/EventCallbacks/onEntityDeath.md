# onEntityDeath(entity)
Called when any entity dies (mobs, animals, players, etc).

| Param    | Type     | Description       |
|----------|----------|---------------------|
| `entity` | userdata | The entity that died  |

> **Note:** in Bukkit's own event hierarchy, a player's death is also an entity death,
> so `onEntityDeath` fires alongside [`onPlayerDeath`](onPlayerDeath.md) whenever a player dies -
> that's expected, not a bug. If you only care about non-player deaths, check the
> entity's type yourself.

```lua
function onEntityDeath(entity)
    mc.log("An entity died")
end
```
