# player:hasItem(item, amount)
Checks whether the player has at least the given amount of an item in their inventory.

| Param    | Type   | Description                                   |
|----------|--------|--------------------------------------------------|
| `item`   | string | Item material name (e.g. `"DIAMOND"`)             |
| `amount` | number | *(optional)* Minimum quantity required. Defaults to `1`. |

**Returns:** boolean.

Throws an error if `item` isn't a recognized material.

```lua
if player:hasItem("DIAMOND", 10) then
    mc.sendMessage(player, "&aYou have 10+ diamonds!")
end
```
