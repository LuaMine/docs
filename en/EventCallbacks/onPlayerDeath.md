# onPlayerDeath(player)
Called when a player dies.

| Param    | Type     | Description        |
|----------|----------|---------------------|
| `player` | userdata | The player who died  |

```lua
function onPlayerDeath(player)
    mc.broadcast("&c" .. mc.getName(player) .. " has died!")
end
```
