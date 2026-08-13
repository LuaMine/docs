# onSneakToggle(player, isSneaking)
Вызывается, когда игрок начинает или прекращает красться.

| Параметр     | Тип      | Описание                                    |
|--------------|----------|--------------------------------------------------|
| `player`     | userdata | Игрок                                              |
| `isSneaking` | boolean  | `true`, если только начал красться, `false` — если перестал |

```lua
function onSneakToggle(player, isSneaking)
    if isSneaking then
        mc.sendMessage(player, "&7*крадётся*")
    end
end
```
