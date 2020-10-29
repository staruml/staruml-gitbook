# Customization

## Custom Keymaps

If you want to make custom keymaps, you can create `keymap.json` at the user configuration path:

* `/Users/<user>/Library/Application Support/StarUML` for Mac OS.
* `C:\Users\<user>\AppData\Roaming\StarUML` for Windows.
* `~/.config/StarUML` for Linux.

You can get how to edit the custom keymap file \(`keymap.json`\) at [Keymaps](../developing-extensions/keymaps.md).

Here is an example:

```javascript
{
  "cmdctrl-alt-1": null,
  "cmdctrl-alt-g": "view:show-grid"
}
```

The first entry is to release the `Ctrl+Alt+1` \(`Cmd+Option+1` in MacOS\) key binding and the second entry is to change key binding of **View &gt; Show Grid** \(Command ID is `view:show-grid`\) to `Ctrl+Alt+G` \(`Cmd+Option+G` in MacOS\).

If you want to know all command IDs, enter the following expression at **Console** \(Debug &gt; Show DevTools &gt; Console tab\).

```javascript
Object.keys(app.commands.commands)
```

## Custom Fonts

If you want to use custom fonts, you can add a font folder in the custom fonts folder:

* `/Users/<user>/Library/Application Support/StarUML/fonts` for Mac OS.
* `C:\Users\<user>\AppData\Roaming\StarUML\fonts` for Windows.
* `~/.config/StarUML/fonts` for Linux.

1. Create a font folder \(e.g. `my-font`\) at the custom fonts folder.
2. Place a font description file \(`font.json`\) and the TrueType font files `.ttf` in the font folder.

The font description file looks as below:

```javascript
[
  {
    "name"       : "MyFont",
    "regular"    : "MyFont-Regular.ttf",
    "italic"     : "MyFont-Italic.ttf",
    "bold"       : "MyFont-Bold.ttf",
    "boldItalic" : "MyFont-BoldItalic.ttf"
  }
]
```

StarUML should be restarted to recognize the added custom fonts.

## Custom Diagram Canvas Size

> Increasing the diagram canvas size will cause severe performance degradation. In some low-spec computers, StarUML will be crashed. Then, reduce the size of the diagram canvas.

We strongly recommend to keep the small number of elements in a diagram. If you have many elements, then split the diagram into multiple diagrams with a single point of view. Nevertheless, you need to have wider diagram canvas size, you can set the maximum canvas width and height in the configuration file.

Find `config.json` at the user configuration path. If couldn't find, then create one.

* `/Users/<user>/Library/Application Support/StarUML` for Mac OS.
* `C:\Users\<user>\AppData\Roaming\StarUML` for Windows.
* `~/.config/StarUML` for Linux.

Edit the maximum width and height number of the diagram canvas as below:

```javascript
{
  "diagramCanvasWidth": 5000, // Default is 4000
  "diagramCanvasHeight": 3500 // Default is 3000
}
```

StarUML should be restarted to affect the changed diagram canvas size.

