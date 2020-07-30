# Menus

Menus are defined in one or more JSON files. A menu file can define or extend **application menu** and **context menus**. All menu files are loaded in alphabetical order.

```javascript
{
  "menu": [],
  "context-menu": []
}
```

The menu JSON files should be placed in `menus/` folder of the extension.

```text
my-extension/
└─ menus/
   └─ menu.json
```

## Application Menu

Now we're going to explain how to add menu items in application menu that is placed in the top of the screen except in Windows which placing on the top of the StarUML window.

### Adding a top-level menu items

We will add a top-level menu item `Menu1` and three sub menu items `Sub Menu1`, `Sub Menu2` and `Sub Menu3`. There will be a separator between `Sub Menu2` and `Sub Menu3`.

We assumes that the commands corresponds to menu items were already defined. To add commands, please refer [Adding Commands](https://github.com/staruml/staruml-gitbook/tree/a4e7d94a6d3e900751c092bd56ef0f5f8b857276/developing-extensions/adding-commands.md).

```javascript
{
  "menu": [
    {
      "id": "menu1",
      "label": "Menu1",
      "submenu": [
        {
          "label": "Sub Menu1",
          "id": "menu1.submenu1",
          "command": "example:function1"
        },
        {
          "label": "Sub Menu2",
          "id": "menu1.submenu2",
          "command": "example:function2"
        },
        { "type": "separator" },
        {
          "label": "Sub Menu3",
          "id": "menu1.submenu3",
          "command": "example:function3"
        }
      ]
    }
  ]
}
```

Each menu item may have following properties:

* **id** : Unique id of the menu item. If `id` is omitted, `command` id will be used for the id.
* **label** : Label for the menu item.
* **command** : A command id to be executed when the menu item selected.
* **submenu** : Submenu items of this menu item.
* **type** : Type of the menu item. One of the values `separator` \| `checkbox`.
* **position** : Position of the menu item to be added. One of the values `first` \| `last` \(default\) \| `before` \| `after`.
* **relative-id** : Relative menu item id for position `before` and `after`.

If you want to add a separator:

```javascript
{ "type": "separator" }
```

### Adding menu items in existing menu items

You can add menu items to an existing menu such as **File**, **Edit**, **Tools**, etc.

We're going to add two sub menu items under the existing **Tools** menu item. All menu items have unique ID. If `id` matches an existing id of menu item, submenu items will be added under the existing menu item.

```javascript
{
  "menu": [
    {
      "id": "tools",
      "submenu": [
        {
          "label": "Tool Sub Menu1",
          "id": "tools.submenu1",
          "command": "example:function1"
        },
        {
          "label": "Tool Sub Menu2",
          "id": "tools.submenu2",
          "command": "example:function2"
        }
      ]
    }
  ]
}
```

### Changing states of menu items

Each menu item has three states _checked_, _enabled_, and _visible_. Here we're going to show how to change the states of existing menu items. You will be able to see the changed state in the both application menu and context menus.

Checked state can be changed only for the menu item defined with type is `checkbox`. To change checked states of menu items as follow.

```javascript
// Change checked states
var checkedStates = {
  'format.show-shadow': true,  //checked
  'format.auto-resize': false  // unchecked
}
app.menu.updateStates(null, null, checkedState)
```

You can also change the visible and enabled states of the menu item **Edit &gt; Select All** as follow:

```javascript
// Change visible state
app.menu.updateStates({ 'edit.select-all': false }, null, null)  // hide
app.menu.updateStates({ 'edit.select-all': true }, null, null)   // show

// Change enabled state
app.menu.updateStates(null, { 'edit.select-all': false }, null)  // disabled
app.menu.updateStates(null, { 'edit.select-all': true }, null)   // enabled
```

## Context Menu

Adding menu items to context menus is basically same with application menu. One difference is that there is only one application menu, but there may be multiple context menus. So the context menus are defined in the menu JSON files as follow:

```javascript
{
  "context-menu": {
    "<dom-selector-for-context-menu1>": [],
    "<dom-selector-for-context-menu2>": [],
    ...
  }
}
```

[DOM selector](https://www.w3.org/TR/selectors-api/) is used to specify a context menu. This means the context menu will be popup when user click mouse right button on the DOM element specified by the DOM selector.

There are three predefined context menus with DOM selectors.

* `#diagram-canvas` : [Diagram Area](../user-guide/user-interface.md#diagram-area)
* `#model-explorer-holder .treeview` : [Model Explorer](../user-guide/user-interface.md#model-explorer)
* `#working-diagrams ul.listview` : [Working Diagrams](../user-guide/user-interface.md#working-diagrams).

### Adding menu items in a predefined context menu

We're going to add a menu item to a predefined context menu of **Diagram Area**.

```javascript
{
  "context-menu": {
    "#diagram-canvas": [
      {
        "label": "Submenu1 for Diagram Area",
        "id": "example.submenu1",
        "command": "example:function1"
      }
    ]
  }
}
```

Click mouse right button on diagram area, you will see the added menu item in the context menu.

### Adding a new context menu

StarUML even allows adding a new Context Menu for a specific DOM element. In here, instead of adding new DOM element we will use an existing DOM element, [Statusbar](../user-guide/user-interface.md#statusbar), which doesn't have any context menu.

**Statusbar** is defined as a DIV element like as `<div id="statusbar" ...></div>`. You can find in **Elements** tab of **DevTools** \(**Debug &gt; Show DevTools**\). We can add a new Context Menu having only one menu item for **Statusbar** as follow:

```javascript
{
  "context-menu": {
    "#statusbar": [
      {
        "label": "Submenu1 for StatusBar",
        "id": "example.submenu1",
        "command": "example:function1"
      }
    ]
  }
}
```

Click mouse right button on **Statusbar**, you will see the new context menu.

