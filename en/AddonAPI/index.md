# LuaMine Addon API

LuaMine exposes a public Java API so other Bukkit/Spigot/Paper plugins can extend its
scripting capabilities - registering their own Lua functions, whole modules
(`require("yourmodule")`), and commands, without needing to fork or modify LuaMine
itself. [Re2Addon](https://github.com/LuaMine/LuaMine/tree/main/addons/re2addon) (the
`require("re2")` regex library) is a real example built entirely on this API.

## Depending on LuaMine

In your addon's `plugin.yml`:

```yaml
name: MyAddon
main: com.example.MyAddon
depend: [LuaMine]      # hard dependency - your plugin won't load without LuaMine
# or
softdepend: [LuaMine]  # soft dependency - loads either way, check for null yourself
```

## Getting the API instance

```java
import org.MineLua.LuaMineAPI;

LuaMineAPI api = LuaMineAPI.get();
if (api == null) {
    getLogger().warning("LuaMine not found!");
    getServer().getPluginManager().disablePlugin(this);
    return;
}
```

`LuaMineAPI.get()` returns `null` if LuaMine hasn't finished enabling yet (or isn't
installed at all) - always check before using it. If you used `depend: [LuaMine]`,
Bukkit guarantees LuaMine's `onEnable()` has already run by the time yours runs, so
this should never actually be `null` in that case - but check anyway, it's cheap
insurance.

## What's available

- [get()](get.md) - the static accessor shown above
- [registerFunction(...)](registerFunction.md) - expose a single Java function to scripts
- [registerModule(...)](registerModule.md) - expose a whole table of functions as `require("name")`
- [registerCommand(...)](registerCommand.md) - register a command that calls into a Lua function
- [getGlobals()](getGlobals.md) - the current luaj `Globals` environment
- [getCustomFunctions() / getCustomModules()](getCustomFunctions.md) - what's currently registered
- [reloadScripts()](reloadScripts.md) - trigger a script reload from Java

Everything registered through `registerFunction`/`registerModule` survives
`/minelua reload` automatically - LuaMine re-injects them into the fresh `Globals` on
every reload, so your addon doesn't need to listen for reloads itself.
