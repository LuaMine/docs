# onPlayerQuit(player)
Вызывается, когда игрок выходит с сервера.

| Параметр | Тип      | Описание           |
|----------|----------|-----------------------|
| `player` | userdata | Вышедший игрок          |

```lua
function onPlayerQuit(player)
    mc.broadcast("&7" .. mc.getName(player) .. " покинул сервер")
end
```
