# onPlayerJoin(player)
Вызывается, когда игрок присоединяется к серверу.

| Параметр  | Тип      | Описание              |
|-----------|----------|------------------------|
| `player`  | userdata | Игрок, присоединяющийся|

```lua
function onPlayerJoin(player)
    mc.broadcast("&aДобро пожаловать, " .. mc.getName(player) .. "!")
end
```
