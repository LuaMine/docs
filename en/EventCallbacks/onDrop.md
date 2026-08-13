# onDrop(player, itemType, amount)
Called when a player drops an item on the ground.

| Param      | Type     | Description                  |
|------------|----------|----------------------------------|
| `player`   | userdata | The player dropping the item        |
| `itemType` | string   | Material name of the dropped item   |
| `amount`   | number   | How many were dropped                |

```lua
function onDrop(player, itemType, amount)
    mc.log(mc.getName(player) .. " dropped " .. amount .. "x " .. itemType)
end
```
