# Setting up your first app on Teverse
It's very simple to get started, all you need is a free Teverse.com account! Simply navigate to the Apps section as shown below and click the blue add button on the top right. 

![Test](https://github.com/teverse/docs/raw/master/assets/create-app.png)

You need to specify a unique package ID, this can ony contain alphanumeric characters aswell as hyphens. This package ID can **not** be changed after creating the app.

After successfully creating your app on the website, keep a note of the package ID, you'll need it to upload your app to the system.

## Setting up the project
Create a new folder on your machine, a good practise is to name this folder the same as your package id.

You should [Download ExampleApp.zip](https://github.com/teverse/docs/raw/master/assets/hello-world.tevapp)
and extract the contents to your new folder. The structure of your app should now be as follows:
 - your-package-id *(DIRECTORY)*
    - manifest.json
    - client *(DIRECTORY)*
        - scripts *(DIRECTORY)*
            - main.lua

Once your app's folder structure matches the above, you'll need to update your manifest.json file to contain the correct package ID.


    {
        "schema": 1,
        "id": "UPDATE THIS",
        "networked": false,
        "version": "0.0.1",
        "permissions": {
            "client": {
                "construct": true
            }
        }
    }


## Uploading your app
In the teverse client, run your unpackaged app, you will be prompted to choose a directory. You must select the directory holding the manifest.json file.

![Unpackaged App](https://github.com/teverse/docs/raw/master/assets/unpackagedApp.png)

Once your app is running, you'll have the option to "share" your app from the bottom of the screen. Clicking this will instantly upload your app to our cloud.

![Uploaded App](https://github.com/teverse/docs/raw/master/assets/uploaded.png)

## Sharing your app
Once uploaded, you can submit your app for review so anyone can run it. Selecting this checkbox will begin the process of sharing your app for public use. **Note that all apps submitted at this time are open-sourced, and your source code is not protected. Multiplayer apps will protect server-side code.**

![Uploaded App](https://github.com/teverse/docs/raw/master/assets/editApp.png)