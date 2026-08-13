# mc.hasPermission(sender, node)
Проверяет, есть ли у игрока или отправителя команды указанная право-нода (permission).

| Параметр | Тип      | Описание                                                            |
|----------|----------|--------------------------------------------------------------------------|
| `sender` | userdata | Игрок (обёрнутый, из колбэка события, или объект `player:xxx()`) или "сырой" `sender`, переданный в колбэк команды |
| `node`   | string   | Право-нода для проверки (например `"myplugin.admin"`)                     |

**Возвращает:** булево значение. Возвращает `false` (а не выбрасывает ошибку), если
`sender` не удалось привести к чему-то, у чего можно проверить права.

```lua
function onPlayerJoin(player)
    if mc.hasPermission(player, "myplugin.vip") then
        mc.sendMessage(player, "&6С возвращением, VIP!")
    end
end

mc.registerCommand("admin", function(sender, args)
    if not mc.hasPermission(sender, "myplugin.admin") then
        mc.sendMessage(sender, "&cУ вас нет прав.")
        return
    end
    -- ...
end)
```
