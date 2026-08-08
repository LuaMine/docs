# mc.wait(ticks, callback)
Executes a callback function after a delay in server ticks (20 ticks = 1 second).

| Param      | Type     | Description                 |
|------------|----------|-----------------------------|
| `ticks`    | number   | Delay in server ticks       |
| `callback` | function | Function to call after delay|

```lua
mc.wait(20, function()
    mc.broadcast("&e1 second has passed!")
end)
```
