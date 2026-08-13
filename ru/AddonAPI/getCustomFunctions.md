# getCustomFunctions() / getCustomModules()
Возвращают то, что сейчас зарегистрировано через [`registerFunction`](registerFunction.md)
и [`registerModule`](registerModule.md) соответственно — по *всем* аддонам, не только
вашему.

```java
import java.util.Map;
import org.luaj.vm2.LuaValue;

Map<String, LuaValue> functions = api.getCustomFunctions();
Map<String, LuaValue> modules = api.getCustomModules();

for (String name : modules.keySet()) {
    getLogger().info("Зарегистрирован модуль: " + name);
}
```

В основном полезно для диагностики/отладки (например, админ-команда, выводящая список
загруженного), или для аддона, который хочет проверить, не зарегистрировал ли уже
что-то другой аддон, прежде чем регистрировать своё.
