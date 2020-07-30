# Package Diagram

## Create Package Diagram

To create a Package Diagram:

1. Select first an element where a new Package Diagram to be contained as a child.
2. Select **Model \| Add Diagram \| Package Diagram** in Menu Bar or select **Add Diagram \| Package Diagram** in Context Menu.

> **See also**
>
> [UML Package Diagram](http://www.uml-diagrams.org/package-diagrams-overview.html) - For more information about UML Package Diagram.

## Package

To create a Package on a diagram:

1. Select **Package** in **Toolbox**.
2. Drag on the diagram as the size of Package.

To create a Package \(model element only\) by Menu:

1. Select an Element where a new Package to be contained.
2. Select **Model \| Add \| Package** in Menu Bar or **Add \| Package** in Context Menu.

You can use **QuickEdit** for Package by double-click or press `Enter` on a selected Package.

* **Name Expression** : Edit name expression.

  _Syntax of Name Expression_

  ```text
  expression ::= [ '<<' stereotype `>>` ] [ visibility ] name
  stereotype ::= (identifier)
  visibility ::= '+' | '#' | '-' | '~'
  name ::= (identifier)
  ```

* **Visibility** : Change visibility property.
* **Add Note** : Add a linked note.
* **Add Sub-Package** : Add a sub-package.
* **Add Dependant Package** : Add a dependant package.
* **Add Depending Package** : Add a depending package.

## Model

To create a Model on a diagram:

1. Select **Model** in **Toolbox**.
2. Drag on the diagram as the size of Model.

To create a Model \(model element only\) by Menu:

1. Select an Element where a new Model to be contained.
2. Select **Model \| Add \| Model** in Menu Bar or **Add \| Model** in Context Menu.

You can use **QuickEdit** for Model Element \(See [Model Element](class-diagram.md#model-element)\).

## Subsystem

To create a Subsystem on a diagram:

1. Select **Subsystem** in **Toolbox**.
2. Drag on the diagram as the size of Subsystem.

To create a Subsystem \(model element only\) by Menu:

1. Select an Element where a new Subsystem to be contained.
2. Select **Model \| Add \| Subsystem** in Menu Bar or **Add \| Subsystem** in Context Menu.

You can use **QuickEdit** for Subsystem by double-click or press `Enter` on a selected Subsystem.

* **Name Expression** : Edit name expression.

  _Syntax of Name Expression_

  ```text
  expression ::= [ '<<' stereotype `>>` ] [ visibility ] name
  stereotype ::= (identifier)
  visibility ::= '+' | '#' | '-' | '~'
  name ::= (identifier)
  ```

* **Visibility** : Change visibility property.
* **Add Note** : Add a linked note.
* **Add Provided Interface** : Add a provided interface.
* **Add Required Interface** : Add a required interface.

## Containment

To make an Containment relation:

1. Select **Containment** in **Toolbox**.
2. Drag from an element \(to be contained\) and drop on a container element.

> **Note**
>
> There is no Containment model element. The Containment view element only show the containment relationship between two elements. \(Contained elements are shown as children in **Model Explorer**\)

