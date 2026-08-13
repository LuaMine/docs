# mc.spawnEntity(type, x, y, z, world)
Spawns an entity at the given coordinates.

| Param   | Type   | Description                                                    |
|---------|--------|--------------------------------------------------------------------|
| `type`  | string | Entity type name (e.g. `"ZOMBIE"`, `"COW"`, `"ARROW"`)               |
| `x`     | number | X coordinate                                                        |
| `y`     | number | Y coordinate                                                        |
| `z`     | number | Z coordinate                                                        |
| `world` | string | *(optional)* World name. Defaults to the server's first/primary world |

Throws an error if `type` isn't a recognized entity type.

```lua
mc.spawnEntity("ZOMBIE", 0, 101, 0)
```
