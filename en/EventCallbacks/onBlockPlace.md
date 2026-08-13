# onBlockPlace(player, block)
Called when a player places a block.

| Param    | Type     | Description         |
|----------|----------|-----------------------|
| `player` | userdata | The player            |
| `block`  | userdata | The placed block       |

```lua
function onBlockPlace(player, block)
    mc.log(mc.getName(player) .. " placed a block")
end
```
