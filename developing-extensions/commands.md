# Commands

In this chapter, we're going to learn how to make commands.

## Making a command

A command is an execution unit that can be called by menu item, keyboard shortcuts or any parts of applications via API. All menu items such as **File &gt; Open...**, **Edit &gt; Copy** have corresponding commands. So you must make a command first before to add a menu item. As shown in [Getting Started](getting-started.md), we will make a simple command showing a message in alert dialog.

First you have to defined an unique ID for a command. Typical command ID have the form `<group>:<function>` where `<group>` is the group name of commands and `<function>` is the function name of the command. An extension may have a set of commands, so typically the group name is the extension name. For example, the ID of the command showing a message of HelloWorld extension is `helloworld:show-message`.

And then, we will define a handler function to be executed when the command is called.

```javascript
function handleShowMessage() {
  window.alert('Hello, world!')
}
```

Finally, we need to register this command to application by calling `app.commands.register` method. The first parameter is the ID of the command and the second is the handler function.

```javascript
app.commands.register('helloworld:show-message', handleShowMessage)
```

## Calling a command

Now we have a new `helloworld:show-message` command. It can be called manually as follow:

```javascript
app.commands.execute('helloworld:show-message')
```

All functionalities of StarUML are defined as commands so that you can call without defining duplicated functionality.

```javascript
var ids = Object.keys(app.commands.commands)
console.log(ids); // you can see all available command IDs
app.commands.execute('project:open') // execute `project:open` command
```

## Passing parameters

You can pass one or more parameters to the command. We will fix the handle function so that it can receive a parameter \(two or more parameters are possible\).

```javascript
function handleShowMessage(message) {
  if (message) {
    window.alert(message)
  } else {
    window.alert('Hello, world!')
  }
}
```

Then, you can pass a string to the parameter as follow:

```javascript
app.commands.execute('helloworld:show-message', 'New Message')
```

