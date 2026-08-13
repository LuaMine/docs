# onPickup(player, itemType, amount)
Called when a player picks up an item from the ground.

| Param      | Type     | Description                    |
|------------|----------|------------------------------------|
| `player`   | userdata | The player picking up the item        |
| `itemType` | string   | Material name of the picked-up item   |
| `amount`   | number   | How many were picked up                |

```lua
function onPickup(player, itemType, amount)
    mc.log(mc.getName(player) .. " picked up " .. amount .. "x " .. itemType)
end
```
