# registerFunction(name, function)
Registers a single Java function so it's callable directly from Lua scripts as a
global function.

| Param      | Type                                   | Description                          |
|------------|-----------------------------------------|------------------------------------------|
| `name`     | `String`                                | The global name scripts will call it by     |
| `function` | `LuaValue` or `Function<LuaValue[], LuaValue>` | The implementation - two overloads, see below |

## Overload 1: `LuaValue` (luaj-native)

Use luaj's own function classes (`OneArgFunction`, `TwoArgFunction`, `VarArgFunction`,
etc.) for full control over argument checking and coercion:

```java
import org.luaj.vm2.LuaValue;
import org.luaj.vm2.lib.OneArgFunction;

api.registerFunction("myAddonFunction", new OneArgFunction() {
    @Override
    public LuaValue call(LuaValue arg) {
        return LuaValue.valueOf("Hello, " + arg.checkjstring() + "!");
    }
});
```

## Overload 2: Java lambda

A simpler shape for straightforward cases - takes the raw argument array and returns
a single `LuaValue`:

```java
api.registerFunction("add", (args) -> {
    int a = args[0].checkint();
    int b = args[1].checkint();
    return LuaValue.valueOf(a + b);
});
```

## Using it from a script

Once registered, the function is available as a plain global - no `require()` needed:

```lua
local greeting = myAddonFunction("world")
mc.log(greeting)  -- "Hello, world!"

local sum = add(5, 3)
mc.log(sum)       -- 8
```

Registering many related functions? Consider [registerModule](registerModule.md)
instead, so scripts get a namespaced `require("yourmodule")` table rather than a pile
of unrelated-looking globals.
