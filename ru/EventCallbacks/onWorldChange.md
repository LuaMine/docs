# onWorldChange(player, fromWorld)
Вызывается, когда игрок переходит из одного мира в другой (например, через портал).

| Параметр    | Тип      | Описание                       |
|-------------|----------|------------------------------------|
| `player`    | userdata | Игрок, сменивший мир                 |
| `fromWorld` | string   | Имя мира, из которого он пришёл       |

Используйте `player:getPosition()` вместе с [Функциями игрока](../Minecraft/PlayerFunctions/index.yaml),
чтобы узнать, в каком мире игрок находится *сейчас*, если это нужно.

```lua
function onWorldChange(player, fromWorld)
    mc.sendMessage(player, "&eВы покинули мир " .. fromWorld)
end
```
