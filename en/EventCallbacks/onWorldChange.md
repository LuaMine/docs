# onWorldChange(player, fromWorld)
Called when a player moves from one world to another (e.g. through a portal).

| Param       | Type     | Description                    |
|-------------|----------|-----------------------------------|
| `player`    | userdata | The player who changed worlds        |
| `fromWorld` | string   | Name of the world they came from     |

Use `player:getPosition()` together with [Player Functions](../Minecraft/PlayerFunctions/index.yaml)
to check which world they're in *now*, if needed.

```lua
function onWorldChange(player, fromWorld)
    mc.sendMessage(player, "&eYou left " .. fromWorld)
end
```
