# LuaMineAPI.get()
Статический геттер для экземпляра Developer API.

**Возвращает:** `LuaMineAPI`, или `null`, если LuaMine не загружен (или ещё не
завершил включение).

```java
import org.MineLua.LuaMineAPI;

LuaMineAPI api = LuaMineAPI.get();
if (api == null) {
    getLogger().warning("LuaMine not found!");
    getServer().getPluginManager().disablePlugin(this);
    return;
}
```

Вызывайте это из `onEnable()` вашего плагина, после указания `depend: [LuaMine]`
(или `softdepend: [LuaMine]` плюс собственная проверка на null) в `plugin.yml`.
