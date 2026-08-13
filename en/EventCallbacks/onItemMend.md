# onItemMend(player, itemType)
Called when the Mending enchantment repairs an item for a player.

| Param      | Type     | Description                                    |
|------------|----------|----------------------------------------------------|
| `player`   | userdata | The player whose item was repaired                    |
| `itemType` | string   | Material name of the repaired item, or `nil` if unavailable |

```lua
function onItemMend(player, itemType)
    mc.sendMessage(player, "&aYour " .. tostring(itemType) .. " was repaired a bit!")
end
```
