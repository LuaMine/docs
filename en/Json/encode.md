# json.encode(value)
Converts a Lua table (or value) to a JSON string.

| Param   | Type  | Description               |
|---------|-------|-----------------------------|
| `value` | any   | The table/value to encode    |

Lua tables with sequential integer keys starting at 1 are encoded as JSON arrays;
everything else is encoded as a JSON object. Functions and other non-serializable
values are encoded as `null`.

```lua
local json = require("json")

local text = json.encode({name = "Steve", items = {"sword", "shield"}})
mc.log(text) -- {"name":"Steve","items":["sword","shield"]}
```
