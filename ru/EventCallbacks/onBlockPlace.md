# onBlockPlace(player, block)
Вызывается, когда игрок ставит блок.

| Параметр | Тип      | Описание           |
|----------|----------|-----------------------|
| `player` | userdata | Игрок                  |
| `block`  | userdata | Поставленный блок       |

```lua
function onBlockPlace(player, block)
    mc.log(mc.getName(player) .. " поставил блок")
end
```
