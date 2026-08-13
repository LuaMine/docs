# onPickup(player, itemType, amount)
Вызывается, когда игрок подбирает предмет с земли.

| Параметр   | Тип      | Описание                        |
|------------|----------|--------------------------------------|
| `player`   | userdata | Игрок, подбирающий предмет             |
| `itemType` | string   | Имя материала подобранного предмета      |
| `amount`   | number   | Сколько штук подобрано                  |

```lua
function onPickup(player, itemType, amount)
    mc.log(mc.getName(player) .. " подобрал " .. amount .. "x " .. itemType)
end
```
