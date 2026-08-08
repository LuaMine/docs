# onChat(player, message)
Called when a player sends a chat message.

| Param     | Type     | Description          |
|-----------|----------|----------------------|
| `player`  | userdata | The chatting player  |
| `message` | string   | The chat message     |

Return the string `"cancel"` to cancel the message.

```lua
function onChat(player, message)
    if string.find(message, "badword") then
        return "cancel"
    end
end
```