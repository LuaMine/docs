# LuaMineAPI.get()
Static accessor for the Developer API instance.

**Returns:** `LuaMineAPI`, or `null` if LuaMine isn't loaded (or hasn't finished enabling yet).

```java
import org.MineLua.LuaMineAPI;

LuaMineAPI api = LuaMineAPI.get();
if (api == null) {
    getLogger().warning("LuaMine not found!");
    getServer().getPluginManager().disablePlugin(this);
    return;
}
```

Call this from your own plugin's `onEnable()`, after declaring `depend: [LuaMine]`
(or `softdepend: [LuaMine]` plus your own null-check logic) in `plugin.yml`.
