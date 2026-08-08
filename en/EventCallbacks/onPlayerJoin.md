# onPlayerJoin(player)
Called when a player joins the server.

| Param    | Type     | Description       |
|----------|----------|-------------------|
| `player` | userdata | The joining player|

```lua
function onPlayerJoin(player)
    mc.broadcast("&aWelcome, " .. mc.getName(player) .. "!")
end
```
