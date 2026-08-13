# mc.hasPermission(sender, node)
Checks whether a player or command sender has the given permission node.

| Param    | Type     | Description                                                        |
|----------|----------|------------------------------------------------------------------------|
| `sender` | userdata | A player (wrapped, from an event callback, or a `player:xxx()` object) or the raw `sender` passed to a command callback |
| `node`   | string   | The permission node to check (e.g. `"myplugin.admin"`)                   |

**Returns:** boolean. Returns `false` (rather than erroring) if `sender` can't be
resolved to something permission-checkable.

```lua
function onPlayerJoin(player)
    if mc.hasPermission(player, "myplugin.vip") then
        mc.sendMessage(player, "&6Welcome back, VIP!")
    end
end

mc.registerCommand("admin", function(sender, args)
    if not mc.hasPermission(sender, "myplugin.admin") then
        mc.sendMessage(sender, "&cYou don't have permission.")
        return
    end
    -- ...
end)
```
