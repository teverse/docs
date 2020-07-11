This is an internal singleton, and tevapps that require this permission may be **rejected** from our app marketplace. 

We may remove or change these development APIs at any time, so please do not create any apps that are reliant on this singleton.

A default script that is loaded on startup binds the key combination `LSHIFT + F1`, this keybind will invoke `teverse.dev:promptTevGit()` and allow you to select a local tevgit repository. **Only do this if you know what you are doing**.

Another keybind is `LSHIFT + F2`, this keybind will invoke `teverse.dev:reloadAllShaders()` which recompiles all of the shaders used in a 3D game/scene. **Only do this if you know what you are doing**.