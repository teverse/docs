In Teverse, the user views the 3D scene through a camera. You can control the camera's position, orientation and field of view to alter what part of the scene the user can see. 

Currently, there can only be one camera in the scene and cameras can not be instantiated in Teverse. However, we are planning to allow developers to create instances of Cameras in the future. 

With our Lua API, you can access the camera singleton through `teverse.scene.camera`. It is important to note that your **tevapp manifest** should have permissions to access the scene singleton on the client side.

teverse.scene.camera:screenToWorld accepts an absolute `vector2` that specifies a location on the screen. This method then returns a three dimensional `vector3` that's relative to the camera's position. This 3D vector behaves as a look vector from the camera to the cursor that you can use for raycasting.

To cast a ray from the camera's "eye" to the user's mouse cursor, you should increase the distance of screenToWorld by multiplying it by a large number before adding the result to the camera's position. **Remember that the result from screenToWorld in Teverse is a relative vector!** An example snippet is shown below:

```lua
local camera = teverse.scene.camera
local mPos = camera:screenToWorld(teverse.input.mousePosition)
local obj, pos, normal = teverse.scene:raycastOne(camera.position, camera.position + (mPos * 10000))
```

Should you want to convert a `guiCoord` to a `vector2` when using this `screenToWorld` method, you can do something similiar to the snippet shown below:

```lua
local coord = guiCoord(0.5, 0, 0.5, 0)
local vec2 = coord:get2D(teverse.input.screenSize)
local mPos = teverse.scene.camera:screenToWorld(vec2)
```

