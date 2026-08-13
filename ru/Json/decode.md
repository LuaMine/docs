# json.decode(text)
Разбирает строку JSON в Lua-таблицу.

| Параметр | Тип    | Описание           |
|----------|--------|-----------------------|
| `text`   | string | JSON-текст для разбора   |

**Возвращает:** Lua-таблицу, или `nil`, если `text` не является валидным JSON.

```lua
local json = require("json")

local data = json.decode('{"name":"Steve","level":5}')
if data then
    mc.log(data.name .. " уровня " .. data.level)
end
```
