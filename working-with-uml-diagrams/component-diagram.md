# Component Diagram

![Component Diagram \(from uml-diagrams.org\)](../.gitbook/assets/components.png)

## Create Component Diagram

To create a Component Diagram:

1. Select first an element where a new Component Diagram to be contained as a child.
2. Select **Model \| Add Diagram \| Component Diagram** in Menu Bar or select **Add Diagram \| Component Diagram** in Context Menu.

> **See also**
>
> [UML Component Diagram](http://www.uml-diagrams.org/component-diagrams.html) - For more information about UML Component Diagram.

## Component

To create a Component:

1. Select **Component** in **Toolbox**.
2. Drag on the diagram as the size of Component.

To create a Component \(model element only\) by Menu:

1. Select an Element where a new Component to be contained.
2. Select **Model \| Add \| Component** in Menu Bar or **Add \| Component** in Context Menu.

You can use **QuickEdit** for Component by double-click or press `Enter` on a selected Component.

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
* **Add Constraint** : Add a constraint.
* **Add Attribute** \(`Ctrl+Enter`\) : Add an attribute.
* **Add Operation** \(`Ctrl+Shift+Enter`\) : Add an operation.
* **Add Reception** : Add a reception.
* **Add Provided Interface** : Add a provided interface.
* **Add Required Interface** : Add a required interface.
* **Add Port** : Add a port.
* **Add Part** : Add a part.

To suppress Attributes, see [Suppress Attributes](../user-guide/formatting-diagram.md#suppress-attributes).

To suppress Operations, see [Suppress Operations](../user-guide/formatting-diagram.md#suppress-operations).

To show or hide Operation Signatures, see [Show Operation Signature](../user-guide/formatting-diagram.md#show-operation-signature).

## Artifact

To create a Artifact:

1. Select **Artifact** in **Toolbox**.
2. Drag on the diagram as the size of Artifact.

To create a Artifact \(model element only\) by Menu:

1. Select an Element where a new Artifact to be contained.
2. Select **Model \| Add \| Artifact** in Menu Bar or **Add \| Artifact** in Context Menu.

You can use **QuickEdit** for Classifier \(See [Classifier](class-diagram.md#classifier)\).

To suppress Attributes, see [Suppress Attributes](../user-guide/formatting-diagram.md#suppress-attributes).

To suppress Operations, see [Suppress Operations](../user-guide/formatting-diagram.md#suppress-operations).

To show or hide Operation Signatures, see [Show Operation Signature](../user-guide/formatting-diagram.md#show-operation-signature).

## Component Realization

To create an Component Realization:

1. Select **Component Realization** in **Toolbox**.
2. Drag from an element \(realizing\) and drop on a Component \(to be realized\).

You can use **QuickEdit** for Relationship \(See [Relationship](class-diagram.md#relationship)\).

