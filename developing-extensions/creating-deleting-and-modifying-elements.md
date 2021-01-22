# Creating, Deleting and Modifying Elements

In this chapter, we're going to learn how to create and modify elements. The most important is that you **should not** create or modify elements directly like `var class1 = new UMLClass()` or `class1.name = "New Name"` because all changes should be done via _operations_ which supports by undo and redo.

## Creating elements

### Creating a model element

You can call `createModel` function of `app.factory` to create a model element with an option object.

The option object may have following fields:

* `id` : ID of factory function to create an element. To see the full ID list, execute `app.factory.getModelIds()`.
* `parent` : A parent element where the created element to be contained.
* `field` \(optional\) : Field name of the parent element \(default is `ownedElements`\).
* `modelInitializer` \(optional\) : A function to initialize the created model element.

```javascript
// Get a reference to top-level project
var project = app.repository.select("@Project")[0]

// Create a UMLModel element as a child of project
var model1 = app.factory.createModel({ id: "UMLModel", parent: project })

// Create a UMLClass element as a child of the model
var class1 = app.factory.createModel({ id: "UMLClass", parent: model1 })

// Create a UMLAttribute element and add to the field 'attributes' of the class
var attr1 = app.factory.createModel({ id: "UMLAttribute", parent: class1, field: "attributes" })

// Create a UMLClass with options
var options = {
  id: "UMLClass",
  parent: model1,
  modelInitializer: function (elem) {
    elem.name = "MyClass";
    elem.isAbstract = true;
  }
}
var class2 = app.factory.createModel(options);
```

You can see the created elements in **Model Explorer** and undo and redo are available for each creation.

### Creating a diagram

Call `createDiagram` function of `app.factory` to create a diagram with an option object:

The option object may have following fields:

* `id` : ID of Factory function to create a diagram. To see the full ID list, execute `app.factory.getDiagramIds()`.
* `parent` : A parent element where the created diagram to be contained.
* `options` \(optional\) : An object containing the below options.
* `diagramInitializer` \(optional\) : A function to initialize the created diagram.

```javascript
// Get a reference to top-level project
var project = app.repository.select("@Project")[0]

// Create a UMLModel element as a child of project
var model1 = app.factory.createModel({ id: "UMLModel", parent: project })

// Create a UMLClassDiagram as a child of the model
var diagram1 = app.factory.createDiagram({ id: "UMLClassDiagram", parent: model1 })

// Create a UMLClassDiagram with options
var options = {
  id: "UMLClassDiagram",
  parent: model1,
  diagramInitializer: function (dgm) {
    dgm.name = "MyDiagram";
    dgm.defaultDiagram = true;
  }
}
var diagram2 = app.factory.createDiagram(options)
```

### Creating a model element and a view element at once

Call `createModelAndView` function of `app.factory` to create a model element and a view element at once with an option object.

The option object may have following fields:

* `id` : ID of Factory function. To see the full ID list, execute `Factory.getModelAndViewIds()`.
* `parent` : A parent element where the created model element to be contained.
* `diagram` : A diagram element where the created view element to be contained.
* `modelInitializer` \(optional\) : A function to initialize the created model element.
* `viewInitializer` \(optional\) : A function to initialize the created view element.
* `x1`, `y1`, `x2`, `y2` \(optional\) : Rectangle coordinate to initialize position and size of the created view element.
* `tailView`, `headView` \(optional\) : If you try to create a relationship \(e.g. `UMLAssociation`\), the created view element connects these two view elements `tailView` and `headView`.
* `tailModel`, and `headModel` \(optional\) : If you try to create a relationship, the created model element connects these two model elements `tailModel` and `headModel`.
* `containerView` \(optional\) : A view element where the created view element to be contained.

The function `createModelAndView` returns the created view element, so you need to get the create model element by accessing `model` field. \(e.g. `classView1.model`\). Following code will create two classes and a association connecting the two classes.

```javascript
// Create a UMLClass and UMLClassView
var options1 = {
  id: "UMLClass",
  parent: diagram1._parent,
  diagram: diagram1,
  x1: 100,
  y1: 100,
  x2: 200,
  y2: 200
}
var classView1 = app.factory.createModelAndView(options1)

// Create another UMLClass and UMLClassView
var options2 = {
  id: "UMLClass",
  parent: diagram1._parent,
  diagram: diagram1,
  x1: 400,
  y1: 100,
  x2: 500,
  y2: 200
}
var classView2 = app.factory.createModelAndView(options2)

// Create an association connecting the two classes
var options3 = {
  id: "UMLAssociation",
  parent: diagram1._parent,
  diagram: diagram1,
  tailView: classView1,
  headView: classView2,
  tailModel: classView1.model,
  headModel: classView2.model
}
var assoView = app.factory.createModelAndView(options3)
```

### Creating a view element of an existing model element

Call `createViewOf` function of `app.factory` to create a view element of an existing model element with an option object.

The option object may have following fields:

* `model` : A model element referenced by the created view element.
* `diagram` : A diagram element where the created view element to be contained.
* `viewInitializer` \(optional\) : A function to initialize the created view element.
* `x`, `y` \(optional\) : Position of the created view element.
* `containerView` \(optional\) : A view element where the created view element to be contained.

```javascript
var options = {
  model: classView1.model,
  diagram: diagram1,
  x: 500,
  y: 500,
}
app.factory.createViewOf(options)
```

You will see the one more class view element at \(500, 500\).

### Adding tags to an element

If you want to extend an element with additional tags, you can create tags by calling `createModel` function with `Tag` parameter of `app.factory`. There are five kinds of Tag: String, Number, Boolean, Reference, and Hidden. Hidden tags are not shown in diagrams, but other tags are shown as properties. \(Check **Format &gt; Show Property** menu\). Following code will create a string tag to the selected element.

```javascript
// Get a selected element
var selected = app.selections.getSelected()

// Options for creating a tag
var options = {
  id: "Tag",
  parent: selected,
  field: "tags",
  modelInitializer: function (tag) {
    tag.name = "Tag1";
    tag.kind = type.Tag.TK_STRING; // or TK_BOOLEAN, TK_NUMBER, TK_REFERENCE, TK_HIDDEN
    tag.value = "String Value...";
    // tag.checked = true; // for TK_BOOLEAN
    // tag.number = 100; // for TK_NUMBER
    // tag.reference = ...; // for TK_REFERENCE
  }
}

// Create a tag to the selected element
var tag1 = app.factory.createModel(options)
```

## Deleting elements

To delete some elements, call `app.engine.deleteElements` function with model and view elements as arguments.

```javascript
// Delete selected model elements
var models = app.selections.getSelectedModels()
app.engine.deleteElements(models, [])

// Or, delete selected view elements
var views = app.selections.getSelectedViews()
app.engine.deleteElements([], views)

// Delete all selected model and view elements
var models = app.selections.getSelectedModels()
var views = app.selections.getSelectedViews()
app.engine.deleteElements(models, views)
```

## Modifying elements

### Change property value

You **should not** modify a property of an element directly like `class1.name = "New Name"` because all changes should be done via _operations_ which supports by undo and redo.

To change property value, use `app.engine.setProperty()` function as below:

```javascript
// Get a selected element
var selected = app.selections.getSelected()
// Change property value
app.engine.setProperty(selected, 'name', 'New Name')
```

## Examples

### Sequence Diagram

Here is an example to create a Sequence Diagram including two Lifelines and a Message.

```javascript
var project = app.repository.select("@Project")[0]

var model1 = app.factory.createModel({ id: "UMLModel", parent: project })

// Create a Sequence Diagram
var options = {
  id: "UMLSequenceDiagram",
  parent: model1,
  diagramInitializer: function (dgm) {
    dgm.name = "MyDiagram";
  }
}
var diagram1 = app.factory.createDiagram(options)

// Create a Lifeline
var options1 = {
  id: "UMLLifeline",
  parent: diagram1._parent,
  diagram: diagram1,
  x1: 50,
  y1: 20,
  x2: 50,
  y2: 20
}
var lifelineView1 = app.factory.createModelAndView(options1)

// Create another Lifeline
var options2 = {
  id: "UMLLifeline",
  parent: diagram1._parent,
  diagram: diagram1,   
  x1: 150,
  y1: 20,
  x2: 150,
  y2: 20
}
var lifelineView2 = app.factory.createModelAndView(options2)

// Create a Message connecting the above two Lifelines
var options3 = {
  id: "UMLMessage",
  parent: diagram1._parent,
  diagram: diagram1, 
  x1: 50,
  y1: 100,
  x2: 150,
  y2: 100,
  tailView: lifelineView1,
  headView: lifelineView2,
  tailModel: lifelineView1.model,
  headModel: lifelineView2.model
}
var messageView1 = app.factory.createModelAndView(options3)
```

