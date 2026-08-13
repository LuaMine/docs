# getGlobals()
Возвращает текущее окружение luaj `Globals` — живое Lua-состояние, в котором прямо
сейчас работают все скрипты.

**Возвращает:** `org.luaj.vm2.Globals`, или `null`, если скрипты ещё не загрузились
(например, на самом раннем этапе старта сервера, до `ServerLoadEvent`).

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

> **Примечание:** объект `Globals` полностью пересоздаётся при каждом
> `/minelua reload` (создаётся новое Lua-окружение, скрипты перезапускаются с нуля) —
> не кэшируйте результат `getGlobals()` через reload. Вызывайте его заново каждый раз,
> когда он нужен.
