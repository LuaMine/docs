# registerCommand(name, function, description, usage)
Registers a Bukkit command (already declared in your addon's `plugin.yml`) that calls
into a Lua function when run.

| Param         | Type       | Description                                             |
|---------------|------------|-------------------------------------------------------------|
| `name`        | `String`   | Command name, matching a command declared in your `plugin.yml` |
| `function`    | `LuaValue` | The name of the Lua function to call, as a `LuaValue.valueOf("functionName")` string |
| `description` | `String`   | Command description                                          |
| `usage`       | `String`   | Usage message                                                 |

```java
api.registerCommand("mycmd", LuaValue.valueOf("onMyCommand"), "My command", "/mycmd <args>");
```

The command must already exist in your addon's `plugin.yml`:

```yaml
commands:
  mycmd:
    description: My command
    usage: /mycmd <args>
```

The Lua function is looked up **by name** from the current script `Globals` each time
the command runs (not captured once at registration time), so scripts can freely
redefine it across `/minelua reload` and the command picks up the latest version:

```lua
function onMyCommand(sender, ...)
    -- sender is the CommandSender (console or player)
    -- ... are the command arguments as strings
    mc.log("Command executed!")
end
```

> **Note:** this is a different mechanism from scripts calling
> [`mc.registerCommand`/`mc.command(...)`](../Minecraft/CommandFunctions/registerCommand.md)
> themselves - this one is for *addons* (Java plugins) to register a command whose
> handler lives in a script, using a command your addon already declared statically in
> `plugin.yml`.
