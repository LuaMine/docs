# json.load(name)
Loads a Lua table previously saved with [`json.save`](save.md).

| Param  | Type   | Description                    |
|--------|--------|-----------------------------------|
| `name` | string | File name (without extension), same restriction as `json.save` |

**Returns:** a Lua table, or `nil` if the file doesn't exist or isn't valid JSON.

```lua
local json = require("json")

local stats = json.load("player_stats") or {kills = 0, deaths = 0}
stats.kills = stats.kills + 1
json.save("player_stats", stats)
```
