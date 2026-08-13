# onDrop(player, itemType, amount)
Вызывается, когда игрок выбрасывает предмет на землю.

| Параметр   | Тип      | Описание                      |
|------------|----------|------------------------------------|
| `player`   | userdata | Игрок, выбрасывающий предмет           |
| `itemType` | string   | Имя материала выброшенного предмета      |
| `amount`   | number   | Сколько штук выброшено                  |

```lua
function onDrop(player, itemType, amount)
    mc.log(mc.getName(player) .. " выбросил " .. amount .. "x " .. itemType)
end
```
