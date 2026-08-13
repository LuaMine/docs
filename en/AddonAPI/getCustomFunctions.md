# getCustomFunctions() / getCustomModules()
Return what's currently registered through [`registerFunction`](registerFunction.md)
and [`registerModule`](registerModule.md) respectively - across *all* addons, not just
your own.

```java
import java.util.Map;
import org.luaj.vm2.LuaValue;

Map<String, LuaValue> functions = api.getCustomFunctions();
Map<String, LuaValue> modules = api.getCustomModules();

for (String name : modules.keySet()) {
    getLogger().info("Registered module: " + name);
}
```

Mostly useful for diagnostics/debugging (e.g. an admin command that lists what's
loaded), or for an addon that wants to check whether another addon has already
registered something before registering its own.
