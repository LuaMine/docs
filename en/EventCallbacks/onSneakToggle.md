# onSneakToggle(player, isSneaking)
Called when a player starts or stops sneaking.

| Param        | Type     | Description                              |
|--------------|----------|---------------------------------------------|
| `player`     | userdata | The player                                    |
| `isSneaking` | boolean  | `true` if they just started sneaking, `false` if they stopped |

```lua
function onSneakToggle(player, isSneaking)
    if isSneaking then
        mc.sendMessage(player, "&7*sneaking*")
    end
end
```
