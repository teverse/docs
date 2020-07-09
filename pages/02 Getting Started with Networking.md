# Creating multiplayer experiences with Teverse
Teverse makes it easy to create cross-platforn multiplayer experiences with our Lua API. We manage distribution of your apps with our global network of high performance servers. 

## Setting up a new app with networking support
**You should read setting up new apps [here](https://teverse.com/docs/Getting-Started-with-Apps.md).**

[Download networked.zip](https://github.com/teverse/docs/raw/master/assets/networked.zip) - In this example, there is a main.lua script for both the server and client. Note that the server folder is never accessible by clients but the client folder is downloaded to a user's computer. 

### Important Disclaimer
In Teverse the server is authorative, we protect your app's code by never sending the contents of the server/ folder to your users. However, in current versions of Teverse, your app's client code is downloaded directly to the user's device, meaning your client side code is completely unprotected (similiar to how browsers operate with JavaScript). 

## Sharing data between clients and a server
### Sending data from client to server
A client can send a message to the server with one line of code:
```lua
    -- client
    teverse.networking:sendToServer("messageName", "Hello World")
```

We receive this message on the server with the following code:
```lua
    -- server
    teverse.networking:on("messageName", function(client, data)
        print(client.name .. " sent " .. data)
    end)
```

With the simple output above, we'd get the following output on the server:
```
    Jay sent Hello World
```

`messageName` is the name of the message and you can use any name for your messages. However, do **not** prefix your message names with an underscore, as this is reserved by our engine and may break your scripts in a future update.

### Sending data from server to client
This works the same as client to server communication however there are two additional methods to think about on the server side:

```lua
    -- server
    -- Send "Hello World" to everyone subscribed to the "messageName" message
    teverse.networking:broadcast("messageName", "Hello World")
```

```lua
    -- server
    local client = teverse.networking:getClient("Jay")

    -- Send "Hello Jay" to Jay if they're subscribed to the "messageName" message
    teverse.networking:sendToClient(client, "messageName", "Hello World")
```

A client can subscribe to a message the same way demonstrated above, but note the lack of a client parameter to the callback function.
```lua
    -- client
    teverse.networking:on("messageName", function(data)
        print("The server sent " .. data)
    end)
```