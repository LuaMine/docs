# onPlayerInteract(player)
Called when a player right-clicks in the air (main hand only).

| Param    | Type     | Description       |
|----------|----------|-------------------|
| `player` | userdata | The interacting player|

```lua
function onPlayerInteract(player)
    mc.sendMessage(player, "&aInteract detected!")
end
```
