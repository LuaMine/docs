# json.load(name)
Загружает Lua-таблицу, ранее сохранённую через [`json.save`](save.md).

| Параметр | Тип    | Описание                                                   |
|----------|--------|-----------------------------------------------------------------|
| `name`   | string | Имя файла (без расширения), то же ограничение, что у `json.save` |

**Возвращает:** Lua-таблицу, или `nil`, если файл не существует или содержит невалидный JSON.

```lua
local json = require("json")

local stats = json.load("player_stats") or {kills = 0, deaths = 0}
stats.kills = stats.kills + 1
json.save("player_stats", stats)
```
