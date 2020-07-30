# Working with Selections

In this chapter, we're going to learn how to get selected elements, force to select particular elements, and do something by listening to selection changed events.

## Getting selected elements

Users can select elements in a diagram or in **Model Explorer**. Sometimes we may need to access only the selected elements.

We need to distinguish between **selected views** and **selected models**. If you select the **Book** class in a diagram, then there is a selected view \(`UMLClassView`\) and a selected model \(`UMLClass`\). If you select the **Author** class in **Model Explorer**, then there is a selected model \(`UMLClass`\) and no selected views.

We can access selected elements using `app.selections` as following:

```javascript
var selectedViews = app.selections.getSelectedViews()
var selectedModels = app.selections.getSelectedModels()
var selected = app.selections.getSelected() // === selectedModels[0]
```

## Enforce to select particular elements

To select a model element in **Model Explorer**, use **ModelExplorerView** module. \(Assume that `Book.mdj` used in [Accessing Elements](https://github.com/staruml/staruml-gitbook/tree/de0346ed28133c9def39873bb4f98979a1698049/developing-extensions/AccessingElements/README.md) were loaded\)

```javascript
var book = app.repository.select("Model::Book")[0]
app.modelExplorer.select(book)
```

To scroll automatically so as to show the element, pass `true` value as the second parameter.

```javascript
app.modelExplorer.select(book, true)
```

To select a view element in diagram, use `app.diagrams`. You can find more functions about selection in [API Reference](http://staruml.io/reference/3.0.0/api).

```javascript
var diagram = app.repository.select("@Diagram")[0]
var view1 = diagram.ownedViews[0]

app.diagrams.selectInDiagram(view1)
```

## Listening selection changed event

Now we will show how to listen and handle a selection change event. An array of selected model elements and an array of selected view elements are passed to the second and the third parameters respectively to the callback function.

```javascript
app.selections.on('selectionChanged', function (models, views) {
  console.log("Selected number of model elements: ", models.length)
  console.log("Selected number of view elements: ", views.length)
})
```

