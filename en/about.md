# About

LuaMine is a [Bukkit/Spigot](https://www.spigotmc.org/) plugin that integrates [Lua](https://www.lua.org/) scripting into Minecraft servers using the [luaj](https://github.com/luaj/luaj) JVM library. Server administrators can write Lua scripts to handle events, manipulate players, schedule tasks, and more — all without compiling Java code.

## Features

- **Lua Scripting** — Write `.lua` scripts in a dedicated `scripts/` folder
- **Event Hooks** — React to player join, chat, block break, interact, and combat events
- **Rich API** — Broadcast messages, manage players, schedule delayed tasks, play sounds, show titles
- **Hot Reload** — Reload all scripts at runtime via `/minelua reload`
- **Zero Restarts** — Scripts are loaded on server start; changes take effect after reload