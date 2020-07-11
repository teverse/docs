Every connected client is represented through this class. You can access a list of connected clients through the [networking singleton](/docs/class/networking).

For example, you could iterate over the list of connected clients to your networked tevapp with the following snippet:
```lua
for _, client in pairs(teverse.networking.clients) do
    print(client.name .. " is in our game!")
end
```

To access clients, ensure that your tevapp manifest contains the networking permission otherwise the singleton will not be accessible within your app/game.