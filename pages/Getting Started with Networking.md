# Creating multiplayer experiences with Teverse
Teverse makes it easy to create cross-platforn multiplayer experiences with our Lua API. We manage distribution of your apps with our global network of high performance servers. 

## Setting up a new app with networking support
**You should read setting up new apps [here](https://teverse.com/docs/Getting-Started-with-Apps.md).**

[Download networked.zip](https://github.com/teverse/docs/raw/master/assets/networked.zip) - In this example, there is a main.lua script for both the server and client. Note that the server folder is never accessible by clients but the client folder is downloaded to a user's computer. 

### Important Disclaimer
In Teverse the server is authorative, we protect your app's code by never sending the contents of the server/ folder to your users. However, in current versions of Teverse, your app's client code is downloaded directly to the user's device, meaning your client side code is completely unprotected (similiar to how browsers operate with JavaScript). 

## Example: Creating a chatroom
This example is coming soon