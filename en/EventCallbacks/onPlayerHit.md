# OnPlayerHit(player, target)
Called when a player hits another player.

| Param    | Type     | Description       |
|----------|----------|-------------------|
| `player` | userdata | The attacker      |
| `target` | userdata | The victim        |

```lua
function onPlayerHit(player, target)
    mc.log(mc.getName(player) .. " hit " .. mc.getName(target))
end
```
