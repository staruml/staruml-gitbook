# Getting Started

Let's start to create an HelloWorld extension for StarUML. Full source codes of HelloWorld extension are available at [https://github.com/staruml/staruml-helloworld](https://github.com/staruml/staruml-helloworld).

## Create an extension

First we need to create an extension folder. Open your extensions folder.

* MacOS: `~/Library/Application Support/StarUML/extensions/user`
* Windows: `C:\Users\<user>\AppData\Roaming\StarUML\extensions\user`
* Linux: `~/.config/StarUML/extensions/user` 

Create a new folder `HelloWorld` in your extensions folder.

## Extension package layout

An extension may have following folder structure:

```text
my-extension/
├─ menus/
├─ keymaps/
├─ stylesheets/
├─ preferences/
├─ main.js
└─ package.json
```

* `/menus` See ...
* `/keymaps` See ...
* `/stylesheets` See ...
* `/preferences` See ...
* `main.js`
* `package.json` - See ...

## Create `main.js`

Create `main.js` in the new extension folder. `main.js` is the entry point to be executed when StarUML is started. `init()` function will be called when the extension is loaded. `init()` is optional, not mandatory.

```javascript
function init() {
  // ...
}

exports.init = init
```

## Application Context

To write an extension with Javascript, you need to use StarUML's open APIs. You can use most of API functions via the application context object `app`. The `app` includes objects providing useful APIs for commands, menus, keymaps, preferences, factory, dialogs, etc. For more about `app` object, see [API Reference](http://staruml.io/reference/3.0.0/api).

> **Note**
>
> StarUML is developed based on [electron](https://electronjs.org/) platform, so you can also use electron APIs in your extension.

## Add a command

A command is an execution unit which can be bound with a menu item as well as a keyboard shortcut. For more about command, see [Commands](commands.md).

In Hello World extension, we will add a command that showing "Hello, World!" message with id `helloworld:show-message` as bellow:

```javascript
function handleShowMessage () {
  window.alert('Hello, world!')
}

function init () {
  app.commands.register('helloworld:show-message', handleShowMessage)
}

exports.init = init
```

## Add a menu item

We will add a menu item named **Hello World** under **Tools** menu. To add a menu item, we need to create a folder `/menus` and a menu JSON file `helloworld.json` in the folder.

```text
staruml-helloworld/
├─ menus/
│  └─ helloworld.json
└─ main.js
```

The menu JSON file is as below:

```javascript
{
  "menu": [
    {
      "id": "tools",
      "submenu": [
        {
          "label": "Hello World",
          "id": "tool.helloworld",
          "command": "helloworld:show-message"
        }
      ]
    }
  ]
}
```

## Add a shortcut

We will also bind a keyboard shortcut `Ctrl+W` \(`Cmd+W` for MacOS\) to the command, so we need to create a folder `/keymaps` and a keymap JSON file `helloworld.json` in the folder.

```text
staruml-helloworld/
├─ menus/
│ └─ helloworld.json
├─ keymaps/
│ └─ helloworld.json
└─ main.js
```

The keymap JSON file is as below:

```javascript
{
  "cmdctrl-w": "helloworld:show-message"
}
```

Now when user selects the menu item or press `Ctrl+W` \(`Cmd+W` for MacOS\), the command `helloworld:show-message` will be executed to show alert dialog with message "Hello, World!".

## Run and Debug

If you finished editing `main.js`, then just restart StarUML. However, restarting whenever you modified codes is very tedious. So, just reload by pressing `Ctrl+R` \(`Cmd+R` for MacOS\) or selecting **Debug &gt; Reload** menu item.

It is useful to use **DevTools** to debug an extension. To open **DevTools**, select **Debug &gt; Show DevTools**. You can see all console errors and logs.

## Define `package.json`

If you consider to distribute your extension to other users, you need to create a `package.json` file containing metadata for the extension.

```javascript
{
  "name": "your_id.helloworld",
  "title": "HelloWorld",
  "description": "HelloWorld extension example.",
  "homepage": "https://github.com/staruml/staruml-helloworld",
  "version": "1.0.0",
  "keywords": ["example", "helloworld"],
  "author": {
    "name": "Minkyu Lee",
    "email": "niklaus.lee@gmail.com",
    "url": "https://github.com/niklauslee"
  },
  "license": "MIT",
  "engines": {
    "staruml": ">=3.0.0"
  }
}
```

Restart StarUML and then check whether your extension is properly shown in **Extension Manager** or not. \(select **Tools &gt; Extension Manager** and click **Installed** tab\).

## Distribute your extension

To allow other users to install your extension, there are several possible ways:

1. Distribute as ZIP archive. Zip the extension folder `staruml-helloworld` as `staruml-helloworld.zip` and just unzip the file in other user's the extensions folder explained above.
2. Distribute via Github URL. Users can install from Github URL. In **Extension Manager**, click **Install from URL** and enter the Github URL \(e.g. `https://github.com/staruml/staruml-helloworld`\) and press **Install** button.
3. Distribute via Extensions Registry. If you want to register official extensions registry. Please contact us \(support@staruml.io\)

