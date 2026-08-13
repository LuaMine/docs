# reloadScripts()
Triggers a full script reload from Java - the same thing `/minelua reload` does.

```java
api.reloadScripts();
```

Reloads every `.lua` file in `plugins/LuaMine/scripts/` and calls the global `main()`
function afterward, exactly like the console/in-game command. Useful if your addon
wants to offer its own reload command, or needs to force a reload after changing
something scripts depend on.
