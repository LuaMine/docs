# mc.setBlock(x, y, z, type, world)
Sets the block type at the given coordinates.

| Param   | Type   | Description                                                    |
|---------|--------|--------------------------------------------------------------------|
| `x`     | number | X coordinate                                                        |
| `y`     | number | Y coordinate                                                        |
| `z`     | number | Z coordinate                                                        |
| `type`  | string | Block material name (e.g. `"STONE"`, `"DIAMOND_BLOCK"`)             |
| `world` | string | *(optional)* World name. Defaults to the server's first/primary world |

Throws an error if `type` isn't a recognized block material.

```lua
mc.setBlock(0, 100, 0, "DIAMOND_BLOCK")
mc.setBlock(0, 64, 0, "GLASS", "world_nether")
```
