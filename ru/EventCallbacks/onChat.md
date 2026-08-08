# onChat(player, message)
Вызывается, когда игрок отправляет сообщение в чат.

| Параметр     | Тип      | Описание             |
|--------------|----------|----------------------|
| `player`     | userdata | Игрок в чате         |
| `message`    | string   | Сообщение в чате     |

Верните строку `"cancel"`, чтобы отменить отправку сообщения.

```lua
function onChat(player, message)
    if string.find(message, "badword") then
        return "cancel"
    end
end
```