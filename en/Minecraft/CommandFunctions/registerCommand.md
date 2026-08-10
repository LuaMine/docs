# mc.registerCommand(name, function, description, usage)
Registers a custom command that runs a Lua function when invoked.

| Param         | Type     | Description                                            |
|---------------|----------|----------------------------------------------------------|
| `name`        | string   | Command name, without the leading `/`                    |
| `function`    | function | Called as `function(sender, args)` when the command runs  |
| `description` | string   | *(optional)* Shown in `/help`                             |
| `usage`       | string   | *(optional)* Usage message, defaults to `/name`           |

The callback receives `sender` (the `CommandSender` who ran the command — a player or
the console) and `args`, a 1-indexed Lua table of the arguments typed after the command
name.

Calling `registerCommand` again with a name that's already registered replaces the
function that runs for it — this is what happens automatically when scripts are
reloaded with `/minelua reload`, so redefining a command in your script and reloading
always picks up the latest version.

```lua
mc.registerCommand("greet", function(sender, args)
    local name = args[1] or "friend"
    mc.sendMessage(sender, "&aHello, " .. name .. "!")
end, "Greets someone", "/greet <name>")
```

> **Note:** `sender` is the raw `CommandSender` Java object (not the same wrapped table
> that event callbacks like `onPlayerJoin` receive), so it doesn't have the `player:xxx()`
> methods described in [Player Functions](../PlayerFunctions/index.yaml). Use the
> `Minecraft.xxx(player, ...)` free functions (e.g. `mc.sendMessage(sender, ...)`,
> `mc.kick(sender, ...)`) which work with both.
