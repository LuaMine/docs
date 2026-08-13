# onPlayerRespawn(player)
Вызывается, когда игрок возрождается после смерти.

| Параметр | Тип      | Описание              |
|----------|----------|--------------------------|
| `player` | userdata | Возрождающийся игрок      |

```lua
function onPlayerRespawn(player)
    mc.sendMessage(player, "&aС возвращением!")
end
```
