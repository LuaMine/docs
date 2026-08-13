# getGlobals()
Returns the current luaj `Globals` environment - the live Lua state all scripts run
in right now.

**Returns:** `org.luaj.vm2.Globals`, or `null` if scripts haven't loaded yet (e.g. very
early during server startup, before `ServerLoadEvent`).

```java
import org.luaj.vm2.Globals;
import org.luaj.vm2.LuaValue;

Globals globals = api.getGlobals();
if (globals != null) {
    LuaValue someGlobalFunction = globals.get("onPlayerJoin");
    if (!someGlobalFunction.isnil()) {
        // ...
    }
}
```

> **Note:** the `Globals` instance is replaced entirely on every `/minelua reload` (a
> fresh Lua environment is created and scripts re-run from scratch) - don't cache the
> result of `getGlobals()` across a reload. Call it again whenever you need it.
