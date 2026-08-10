# player:removeEffect(name)
Снимает с игрока эффект зелья, если он у него есть.

| Параметр | Тип    | Описание                                              |
|----------|--------|-----------------------------------------------------------|
| `name`   | string | Имя эффекта (`PotionEffectType` из Bukkit, например `"SPEED"`) |

```lua
player:removeEffect("SPEED")
```
