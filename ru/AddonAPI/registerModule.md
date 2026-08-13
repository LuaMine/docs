# registerModule(name, module)
Регистрирует целую `LuaTable` функций как модуль, доступный через `require(name)` в
скриптах — тот же механизм, что LuaMine сам использует для `require("Minecraft")` и
`require("json")`, и которым [Re2Addon](https://github.com/LuaMine/LuaMine/tree/main/addons/re2addon)
открывает `require("re2")`.

| Параметр | Тип        | Описание                                    |
|----------|------------|--------------------------------------------------|
| `name`   | `String`   | Имя, которое скрипты передают в `require(...)`      |
| `module` | `LuaTable` | Таблица функций (и/или других значений)               |

```java
import org.luaj.vm2.LuaTable;
import org.luaj.vm2.LuaValue;
import org.luaj.vm2.lib.OneArgFunction;

LuaTable myModule = new LuaTable();
myModule.set("greet", new OneArgFunction() {
    @Override
    public LuaValue call(LuaValue arg) {
        return LuaValue.valueOf("Привет, " + arg.checkjstring() + "!");
    }
});
api.registerModule("mymodule", myModule);
```

```lua
local mymodule = require("mymodule")
mc.log(mymodule.greet("world"))  -- "Привет, world!"
```

Предпочитайте это [registerFunction](registerFunction.md), когда открываете больше
пары связанных функций — именованный модуль читается в скриптах лучше, чем несколько
похоже названных глобальных переменных, и избегает конфликтов имён с другими аддонами.

Зарегистрированные модули автоматически переживают `/minelua reload`: тот же самый
объект `LuaTable` заново вставляется в свежий `Globals` при каждом reload, так что
аддону нужно вызвать это только один раз, в своём `onEnable()`.
