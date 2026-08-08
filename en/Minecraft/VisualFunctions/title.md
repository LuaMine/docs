# mc.title(player, title, subtitle)
Displays a title and subtitle to a player.

| Param      | Type     | Description                     |
|------------|----------|---------------------------------|
| `player`   | userdata | Player object                   |
| `title`    | string   | Main title (supports `&` codes) |
| `subtitle` | string   | Subtitle (supports `&` codes)   |

```lua
mc.title(player, "&aWelcome!", "&eEnjoy your stay")
```