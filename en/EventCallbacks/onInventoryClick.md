# onInventoryClick(player, slot, itemType)
Called when a player clicks a slot in any open inventory.

| Param      | Type     | Description                                              |
|------------|----------|-------------------------------------------------------------|
| `player`   | userdata | The clicking player                                         |
| `slot`     | number   | The clicked slot index                                       |
| `itemType` | string   | Material name of the clicked item, or `nil` if the slot is empty |

Return the string `"cancel"` to cancel the click (e.g. to lock items in place inside a
custom GUI/shop menu).

```lua
function onInventoryClick(player, slot, itemType)
    if itemType == "BEDROCK" then
        return "cancel"
    end
end
```
