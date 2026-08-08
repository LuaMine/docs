# OnPlayerHit(player, target)
Вызывается, когда игрок бьёт другого игрока.

| Параметр  | Тип      | Описание         |
|-----------|----------|------------------|
| `player`  | userdata | Нападающий       |
| `target`  | userdata | Жертва           |

```lua
function onPlayerHit(player, target)
    mc.log(mc.getName(player) .. " ударил " .. mc.getName(target))
end
```
