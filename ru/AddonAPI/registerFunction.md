# registerFunction(name, function)
Регистрирует одну Java-функцию так, чтобы её можно было вызывать напрямую из
Lua-скриптов как глобальную функцию.

| Параметр   | Тип                                             | Описание                                |
|------------|--------------------------------------------------|--------------------------------------------|
| `name`     | `String`                                          | Глобальное имя, по которому её будут вызывать скрипты |
| `function` | `LuaValue` или `Function<LuaValue[], LuaValue>`   | Реализация — два варианта перегрузки, см. ниже |

## Вариант 1: `LuaValue` (нативный для luaj)

Используйте собственные классы функций luaj (`OneArgFunction`, `TwoArgFunction`,
`VarArgFunction` и т.д.) для полного контроля над проверкой и приведением аргументов:

```java
import org.luaj.vm2.LuaValue;
import org.luaj.vm2.lib.OneArgFunction;

api.registerFunction("myAddonFunction", new OneArgFunction() {
    @Override
    public LuaValue call(LuaValue arg) {
        return LuaValue.valueOf("Привет, " + arg.checkjstring() + "!");
    }
});
```

## Вариант 2: Java-лямбда

Более простая форма для несложных случаев — принимает "сырой" массив аргументов и
возвращает одно `LuaValue`:

```java
api.registerFunction("add", (args) -> {
    int a = args[0].checkint();
    int b = args[1].checkint();
    return LuaValue.valueOf(a + b);
});
```

## Использование из скрипта

После регистрации функция доступна как обычная глобальная переменная — `require()` не нужен:

```lua
local greeting = myAddonFunction("world")
mc.log(greeting)  -- "Привет, world!"

local sum = add(5, 3)
mc.log(sum)       -- 8
```

Регистрируете много связанных функций? Рассмотрите [registerModule](registerModule.md) —
тогда скрипты получат аккуратную таблицу через `require("yourmodule")`, а не кучу
похоже названных глобальных переменных.
