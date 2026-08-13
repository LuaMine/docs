# Addon API от LuaMine

LuaMine предоставляет публичный Java API, позволяющий другим Bukkit/Spigot/Paper
плагинам расширять его скриптовые возможности — регистрировать собственные Lua-функции,
целые модули (`require("yourmodule")`) и команды, не форкая и не изменяя сам LuaMine.
[Re2Addon](https://github.com/LuaMine/LuaMine/tree/main/addons/re2addon)
(библиотека регулярных выражений `require("re2")`) — реальный пример, полностью
построенный на этом API.

## Зависимость от LuaMine

В `plugin.yml` вашего аддона:

```yaml
name: MyAddon
main: com.example.MyAddon
depend: [LuaMine]      # жёсткая зависимость - ваш плагин не загрузится без LuaMine
# или
softdepend: [LuaMine]  # мягкая зависимость - загрузится в любом случае, проверяйте null сами
```

## Получение экземпляра API

```java
import org.MineLua.LuaMineAPI;

LuaMineAPI api = LuaMineAPI.get();
if (api == null) {
    getLogger().warning("LuaMine not found!");
    getServer().getPluginManager().disablePlugin(this);
    return;
}
```

`LuaMineAPI.get()` возвращает `null`, если LuaMine ещё не завершил включение (или вовсе
не установлен) — всегда проверяйте перед использованием. Если вы указали
`depend: [LuaMine]`, Bukkit гарантирует, что `onEnable()` LuaMine уже отработал к моменту
вызова вашего — так что `null` в этом случае не должен встретиться на практике, но
проверка всё равно бесплатна.

## Что доступно

- [get()](get.md) — статический геттер, показанный выше
- [registerFunction(...)](registerFunction.md) — открыть одну Java-функцию для скриптов
- [registerModule(...)](registerModule.md) — открыть целую таблицу функций как `require("name")`
- [registerCommand(...)](registerCommand.md) — зарегистрировать команду, вызывающую Lua-функцию
- [getGlobals()](getGlobals.md) — текущее окружение luaj `Globals`
- [getCustomFunctions() / getCustomModules()](getCustomFunctions.md) — что сейчас зарегистрировано
- [reloadScripts()](reloadScripts.md) — вызвать перезагрузку скриптов из Java

Всё, что зарегистрировано через `registerFunction`/`registerModule`, автоматически
переживает `/minelua reload` — LuaMine сам заново вставляет их в свежий `Globals` при
каждом reload, аддону не нужно самому слушать событие перезагрузки.
