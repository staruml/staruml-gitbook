Managing Extensions
===================

<!-- toc -->

![Extension Manager Dialog](/assets/extension-manager-dialog.png)

## Install Extension

To install an extension from Extension Registry:

1. Show **Extension Manager** by selecting **Tools | Extension Manager...**.
2. Select **Registry** button.
3. Find an extension to install by search.
4. Press **Install** button of the extension.

To install an extension directly from Github repository:

1. Show **Extension Manager** by selecting **Tools | Extension Manager...**.
2. Select **Install From Url** button.
3. Enter Url of the Github project on input box
4. press **Install** button.

To install an extension manually:

1. Get an extension as a `.zip` file.
2. Extract the file on the extensions path.
    * `/Users/<user>/Library/Application Support/StarUML/extensions/user` for Mac OS.
    * `C:\Users\<user>\AppData\Roaming\StarUML\extensions\user` for Windows.
    * `~/.config/StarUML/extensions/user` for Linux.
3. Check a folder in the extensions path and :file:`main.js` file in the folder.
4. Restart StarUML.


## Uninstall Extension

To uninstall an extension:

1. Show **Extension Manager** by selecting **Tools | Extension Manager...**.
2. Select **Installed** button.
3. Find an extension to uninstall by search.
4. Press **Remove** button of the extension.

To uninstall an extension manually:

1. Go to the extensions path.
    * `/Users/<user>/Library/Application Support/StarUML/extensions/user` for Mac OS.
    * `C:\Users\<user>\AppData\Roaming\StarUML\extensions\user` for Windows.
    * `~/.config/StarUML/extensions/user` for Linux.
2. Remove the extension folder to uninstall.
3. Restart StarUML.


## Update Extension

To update an extension:

1. Show **Extension Manager** by selecting **Tools | Extension Manager...**.
2. Select **Registry** button.
3. **Update** button will be shown if the extension has updates.
4. Press **Update** button of the extension.

To update an extension manually:

1. Uninstall extension of old version manually.
2. Install extension of new version manually.
3. Restart StarUML.
