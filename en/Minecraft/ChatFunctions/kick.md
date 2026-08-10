# mc.kick(player, reason)
Kicks a player from the server.

| Param    | Type     | Description                     |
|----------|----------|---------------------------------|
| `player` | userdata | Player object                   |
| `reason` | string   | Kick reason (supports `&` codes) |

```lua
mc.kick(player, "&cYou were kicked!")
```

> **Note:** Also available as `player:kick(reason)`.
