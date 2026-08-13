# player:giveItem(item, amount)
Gives the player an item.

| Param    | Type   | Description                                   |
|----------|--------|--------------------------------------------------|
| `item`   | string | Item material name (e.g. `"DIAMOND"`)             |
| `amount` | number | *(optional)* Quantity to give. Defaults to `1`.    |

Throws an error if `item` isn't a recognized material.

```lua
player:giveItem("DIAMOND", 5)
```
