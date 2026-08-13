# mc.getBlock(x, y, z, world)
Gets the block type at the given coordinates.

| Param   | Type   | Description                                                    |
|---------|--------|--------------------------------------------------------------------|
| `x`     | number | X coordinate                                                        |
| `y`     | number | Y coordinate                                                        |
| `z`     | number | Z coordinate                                                        |
| `world` | string | *(optional)* World name. Defaults to the server's first/primary world |

**Returns:** string material name, or `nil` if the given world doesn't exist.

```lua
local block = mc.getBlock(0, 100, 0)
mc.log("Block: " .. block)
```
