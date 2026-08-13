# onWeatherChange(world, isRaining)
Вызывается при изменении погоды в мире.

| Параметр    | Тип     | Описание                              |
|-------------|---------|------------------------------------------|
| `world`     | string  | Имя мира, где изменилась погода           |
| `isRaining` | boolean | `true`, если начинается дождь, `false` — если проясняется |

```lua
function onWeatherChange(world, isRaining)
    if isRaining then
        mc.broadcast("&9В мире " .. world .. " начался дождь")
    end
end
```
