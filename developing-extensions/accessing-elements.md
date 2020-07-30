# Accessing Elements

In this chapter, we're going to learn how to access elements. Before you read this chapter, you need to have clear understanding of the difference between software model and diagram as well as model elements and view elements. If you don't know about this, please read [Basic Concepts](../user-guide/basic-concepts.md) first.

In the following sections, we will use an example software model as shown in the below figure. Actual model file can be obtained from here: [https://github.com/staruml/staruml-dev-docs/blob/master/samples/Book.mdj](https://github.com/staruml/staruml-dev-docs/blob/master/samples/Book.mdj). There are two classes **Book** and **Author** and a association **wrote** connecting between the two classes. In addition, there is a diagram named **Main** which containing three view elements, each corresponds to **Book**, **Author**, **wrote** respectively. All these elements and a diagram are contained by a model named **Model** which is also contained by the top-level project element named **Book Sample**.

![Book Sample](https://github.com/staruml/staruml-dev-docs/blob/master/images/Book-sample.png?raw=true)

## Getting a top-level project

First we will access to the top-level project element. The top-level project element can be obtained by using `app.project`.

```javascript
var project = app.project.getProject()
console.log(project.name) // "Book Sample"
```

> **Note**
>
> all Javascript code examples can be executed in console \(select **Debug &gt; Show DevTools** and then click **Console** tab\).

The obtained element is just a Javascript object, so you can access to any fields such as `project.name` or `project.ownedElements[0]`. Printing the element itself in console like `console.log(project)` is helpful to get all information about the element.

## Inspecting elements

Then, how can we know which classes of elements are available and which attributes or operations are available for each class of elements? You can find documentations of the metamodel at [Metamodel documentation](http://staruml.io/reference/3.0.0/metamodel) or additionally at [API Reference](http://staruml.io/reference/3.0.0/api).

You can access to any elements via the top-level project. Containment structure is shown in **Explorer** of the above capture image.

```javascript
var model = project.ownedElements[0]
console.log(model.name) // "Model"

var mainDiagram = model.ownedElements[0] 
console.log(mainDiagram.name) // "Main"

var book = model.ownedElements[1]
var author = model.ownedElements[2]
console.log(book.name) // "Book"
console.log(author.name) // "Author"

var association = book.ownedElements[0]
console.log(association.name) // "wrote"
console.log(association.end1.name) // "publications"
console.log(association.end1.multiplicity) // "1..*"
console.log(association.end2.name) // "authors"
console.log(association.end2.multiplicity) // "1..*"

var bookISBN = book.attributes[0]
console.log(bookISBN.name) // "ISBN"
console.log(bookISBN.type) // "String"
console.log(bookISBN.visibility) // "public"
console.log(bookISBN.isID) // true
```

So far we inspected model elements only, now you will see the view elements contained by the diagram **Main**.

```javascript
var bookView = mainDiagram.ownedViews[0]
console.log(bookView.left) // 32
console.log(bookView.top) // 20
console.log(bookView.width) // 114
console.log(bookView.height) // 103
console.log(bookView.fillColor) // "#ffffff"
console.log(bookView.model.name) // "Book"
console.log(bookView.model === book) // true

var authorView = mainDiagram.ownedViews[1]
...
```

Each element has a corresponding Javascript class definition. The class definitions are in a global variable `type`.

```javascript
console.log(project instanceof type.Project) // true
console.log(model instanceof type.UMLModel) // true
console.log(mainDiagram instanceof type.UMLClassDiagram) // true
console.log(book instanceof type.UMLClass) // true
console.log(bookISBN instanceof type.UMLAttribute) // true
console.log(association instanceof type.UMLAssociation) // true
console.log(bookView instanceof type.UMLClassView) // true
```

## Retrieving elements by query

Accessing elements from the top-level project is very inconvenient and tedious. How can we get all elements of `UMLClass` type? To retrieve elements easily, StarUML provides a very simple query expression.

Following are several examples for query expression. To see the full specification of query expression, refer to [https://github.com/staruml/metadata-json/wiki/SelectorExpression](https://github.com/staruml/metadata-json/wiki/SelectorExpression).

```javascript
app.repository.select("@Project")
// returns elements of type.Project: [Project]

app.repository.select("@UMLClass")
// returns elements of type.UMLClass: [Book, Author]

app.repository.select("Model::Book")
// returns elements named "Book" contained by an element named "Model": [Book]

app.repository.select("Book.attributes")
// returns elements in 'attributes' field of an element named "Book": [ISBN, title, summary, publisher]

app.repository.select("@UMLAttribute[type=String]")
// returns elements of type.UMLAttribute only if whose 'type' field has "String" value: [ISBN, title, summary, publisher, name, biography]
```

