# onPlayerRespawn(player)
Called when a player respawns after death.

| Param    | Type     | Description            |
|----------|----------|--------------------------|
| `player` | userdata | The respawning player     |

```lua
function onPlayerRespawn(player)
    mc.sendMessage(player, "&aWelcome back!")
end
```
