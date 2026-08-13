# json.save(name, value)
Saves a Lua table (or value) as JSON to a file under `plugins/LuaMine/config/`.

| Param   | Type   | Description                                        |
|---------|--------|------------------------------------------------------|
| `name`  | string | File name (without extension) - see restriction below |
| `value` | any    | The table/value to save                              |

**Returns:** `true` on success, `false` if the write failed.

The file is written to `plugins/LuaMine/config/<name>.json`. `name` may only contain
letters, digits, `_` and `-` - no path separators or `..` are allowed, and using them
throws an error rather than being silently stripped. This is a safety restriction: it
prevents a script from writing files outside the `config/` folder.

```lua
local json = require("json")

json.save("player_stats", {kills = 10, deaths = 2})
```
