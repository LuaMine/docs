# onItemMend(player, itemType)
Вызывается, когда зачарование "Починка" (Mending) чинит предмет игроку.

| Параметр   | Тип      | Описание                                         |
|------------|----------|-------------------------------------------------------|
| `player`   | userdata | Игрок, чей предмет был починен                         |
| `itemType` | string   | Имя материала починенного предмета, или `nil`, если недоступно |

```lua
function onItemMend(player, itemType)
    mc.sendMessage(player, "&aВаш " .. tostring(itemType) .. " немного починился!")
end
```
