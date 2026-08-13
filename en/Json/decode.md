# json.decode(text)
Parses a JSON string into a Lua table.

| Param  | Type   | Description       |
|--------|--------|----------------------|
| `text` | string | The JSON text to parse |

**Returns:** a Lua table, or `nil` if `text` isn't valid JSON.

```lua
local json = require("json")

local data = json.decode('{"name":"Steve","level":5}')
if data then
    mc.log(data.name .. " is level " .. data.level)
end
```
