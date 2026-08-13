# registerModule(name, module)
Registers a whole `LuaTable` of functions as a module, retrievable via `require(name)`
in scripts - the same mechanism LuaMine itself uses for `require("Minecraft")` and
`require("json")`, and how [Re2Addon](https://github.com/LuaMine/LuaMine/tree/main/addons/re2addon)
exposes `require("re2")`.

| Param    | Type       | Description                                    |
|----------|------------|---------------------------------------------------|
| `name`   | `String`   | The name scripts pass to `require(...)`              |
| `module` | `LuaTable` | A table of functions (and/or other values)             |

```java
import org.luaj.vm2.LuaTable;
import org.luaj.vm2.LuaValue;
import org.luaj.vm2.lib.OneArgFunction;

LuaTable myModule = new LuaTable();
myModule.set("greet", new OneArgFunction() {
    @Override
    public LuaValue call(LuaValue arg) {
        return LuaValue.valueOf("Hello, " + arg.checkjstring() + "!");
    }
});
api.registerModule("mymodule", myModule);
```

```lua
local mymodule = require("mymodule")
mc.log(mymodule.greet("world"))  -- "Hello, world!"
```

Prefer this over [registerFunction](registerFunction.md) whenever you're exposing more
than a couple of related functions - a namespaced module reads better in scripts than
several similarly-named globals, and avoids naming collisions with other addons.

Registered modules survive `/minelua reload` automatically: the same `LuaTable`
instance is re-injected into the fresh `Globals` on every reload, so your addon only
needs to call this once, in its own `onEnable()`.
