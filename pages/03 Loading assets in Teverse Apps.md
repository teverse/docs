# Loading assets in Apps with Teverse
Bundling assets with Teverse is easy, just put them inside your App's client or server folder and you're good to go! Teverse has structured TevApps in a flexible way in order to allow developers to bundle many assets that their app can utilise. 

All resources in Teverse can be bundled within your app. For example, Teverse's Lua API allows you to locate assets such as: images, audio and meshes using the "fs:" resource locator prefix.

```lua
local img = teverse.construct("guiImage", {
    image = "fs:assets/image1.png",
    parent = teverse.interface
})
```

This snippet of code creates a guiImage using Teverse's Lua API and it demonstrates use of the "fs:" prefix. When code is ran on the client side, "fs:" points directly to the TevApp's client folder, the opposite is true when the code is ran on a server. This ensures proper seperation between your client and server assets. 

In the example above, the developer created an additional folder named 'assets' in their client folder. This allows for better organisation of your assets and you are free to use whatever structure you can think of.

Another Teverse snippet shown below loads a glTF mesh file from the TevApp's client folder and renders it in the middle of the scene.

```lua
local block = teverse.construct("block", {
    position = vector3(0, 0, 0),
    mesh = "fs:meshes/ybotdance2.glb"
})

block.scale = block.meshScale
```

In the above snippet, Teverse searches under the client directory for a 'meshes' folder, before looking for a glTF file named 'ybotdance2.glb'. If Teverse successfully parses this mesh, it is shown in the scene. However, if loading fails then an appropriate warning or error message will be written to the log and the block may appear invisible. Setting the block's `scale` to it's `meshScale` will set the mesh to it's native size so no stretching is visible.