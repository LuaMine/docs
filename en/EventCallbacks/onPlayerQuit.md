# onPlayerQuit(player)
Called when a player leaves the server.

| Param    | Type     | Description        |
|----------|----------|----------------------|
| `player` | userdata | The player who left  |

```lua
function onPlayerQuit(player)
    mc.broadcast("&7" .. mc.getName(player) .. " left the server")
end
```
