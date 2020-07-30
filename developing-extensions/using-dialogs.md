# Using Dialogs

In this chapter, we're going to learn how to use dialogs.

## File Dialogs

You can use **Open Dialog** and **Save Dialog** to allow users to choose files or directories.

Following is an example of **Open Dialog** for choosing a text `*.txt` file.

```javascript
var filters = [
  { name: "Text Files", extensions: [ "txt" ] }
]
var selected = app.dialogs.showOpenDialog("Select a text file...", null, filters)
// Returns an array of paths of selected files
```

Following is an example of **Save Dialog** for getting a file name.

```javascript
var filters = [
  { name: "Text Files", extensions: [ "txt" ] }
]
var selected = app.dialogs.showSaveDialog("Save text as...", null, filters)
// Returns a file path to save
```

## Message Dialogs

There are three types of message dialogs to show error, alert, and info.

```javascript
// Error Dialog
app.dialogs.showErrorDialog("This is error message.")

// Alert Dialog
app.dialogs.showAlertDialog("This is alert message.")

// Info Dialog
app.dialogs.showInfoDialog("This is info message.")
```

## Input Dialogs

Here are code examples to show dialogs to get user inputs.

**Input Dialog** \(single line text\)

```javascript
app.dialogs.showInputDialog("Enter your name.").then(function ({buttonId, returnValue}) {
  if (buttonId === 'ok') {
    console.log("Your name is", returnValue)
  } else {
    console.log("User canceled")
  }
})
```

**Text Dialog** \(multi line text\)

```javascript
app.dialogs.showTextDialog("Enter your biography.", "Edit here...").then(function ({buttonId, returnValue}) {
  if (buttonId === 'ok') {
    console.log("Your bio is", returnValue)
  } else {
    console.log("User canceled")
  }
})
```

**Confirm Dialog**

```javascript
var buttonId = app.dialogs.showConfirmDialog("Are you sure?")
```

**Select Radio Dialog**

```javascript
var options = [
  { text: "First", value: 1 },
  { text: "Second", value: 2 },
  { text: "Third", value: 3 }
]
app.dialogs.showSelectRadioDialog("Select one of the following items.", options).then(function ({buttonId, returnValue}) {
  if (buttonId === 'ok') {
    console.log(returnValue)
  } else {
    console.log("User canceled")
  }
})
```

**Select Dropdown Dialog**

```javascript
var options = [
  { text: "First", value: 1 },
  { text: "Second", value: 2 },
  { text: "Third", value: 3 }
]
app.dialogs.showSelectDropdownDialog("Select one of the following items.", options).then(function ({buttonId, returnValue}) {
  if (buttonId === 'ok') {
    console.log(returnValue);
  } else {
    console.log("User canceled")
  }
})
```

**Color Dialog**

```javascript
// Initial color is red (#ff0000).
app.dialogs.showColorDialog("#ff0000").then(function ({buttonId, returnValue}) {
  if (buttonId === 'ok') {
    console.log(returnValue);
  } else {
    console.log("User canceled")
  }
})
```

**Font Dialog**

```javascript
var font = {
  face: "Helvetica",
  size: 20,
  color: "#ff0000"
}
app.dialogs.showFontDialog(font).then(function ({buttonId, returnValue}) {
  if (buttonId === 'ok') {
    console.log(returnValue);
  } else {
    console.log("User canceled")
  }
})
```

## Element Dialogs

If you need to ask users to pick an model element, **Element Picker Dialog** can be used as follow:

```javascript
app.elementPickerDialog.showDialog("Select a Class", null, type.UMLClass).then(function ({buttonId, returnValue}) {
  if (buttonId === 'ok') {
    console.log("You selected: ", returnValue)
  }
})
```

![ElementPickerDialog](https://github.com/staruml/staruml-dev-docs/blob/master/images/ElementPickerDialog.png?raw=true)

Or, you may need to constrain a list of elements which can be selected by users. Then you can use **Element List Picker Dialog**.

```javascript
var classes = app.repository.select("@UMLClass")
var dlg = app.elementListPickerDialog.showDialog("Select a set of Class", classes).then(function ({buttonId, returnValue}) {
  if (buttonId === 'ok') {
    console.log("You selected: ", returnValue)
  }
})
```

![ElementListPickerDialog](https://github.com/staruml/staruml-dev-docs/blob/master/images/ElementListPickerDialog.png?raw=true)

## Toast

**Toast** is a way to show a short message in some seconds. It appears on the top of diagram area and disappears automatically after some seconds.

```javascript
app.toast.error("This is an error message") // Red color
app.toast.warning("This is a warning message") // Yellow color
app.toast.info("This is an info message") // Black color
```

