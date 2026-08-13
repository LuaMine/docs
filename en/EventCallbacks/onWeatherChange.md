# onWeatherChange(world, isRaining)
Called when a world's weather changes.

| Param       | Type    | Description                          |
|-------------|---------|-----------------------------------------|
| `world`     | string  | Name of the world where weather changed   |
| `isRaining` | boolean | `true` if it's changing to rain, `false` if clearing |

```lua
function onWeatherChange(world, isRaining)
    if isRaining then
        mc.broadcast("&9It started raining in " .. world)
    end
end
```
