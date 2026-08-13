# onPlayerDeath(player)
Вызывается, когда игрок умирает.

| Параметр | Тип      | Описание           |
|----------|----------|----------------------|
| `player` | userdata | Умерший игрок          |

```lua
function onPlayerDeath(player)
    mc.broadcast("&c" .. mc.getName(player) .. " погиб!")
end
```
