# Deployment Diagram

## Create Deployment Diagram

To create a Deployment Diagram:

1. Select first an element where a new Deployment Diagram to be contained as a child.
2. Select **Model \| Add Diagram \| Deployment Diagram** in Menu Bar or select **Add Diagram \| Deployment Diagram** in Context Menu.

> **See also**
>
> [UML Deployment Diagram](http://www.uml-diagrams.org/deployment-diagrams-overview.html) - For more information about UML Deployment Diagram.

## Node

To create a Node:

1. Select **Node** in **Toolbox**.
2. Drag on the diagram as the size of Node.

To create a Node \(model element only\) by Menu:

1. Select an Element where a new Node to be contained.
2. Select **Model \| Add \| Node** in Menu Bar or **Add \| Node** in Context Menu.

You can use **QuickEdit** for Node by double-click or press `Enter` on a selected Node.

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
* **Add Attribute** \(`Ctrl+Enter`\) : Add an attribute.
* **Add Operation** \(`Ctrl+Shift+Enter`\) : Add an operation.
* **Add Reception** : Add a reception.
* **Add Communicating Node** : Add a communicating node.
* **Add Deployed Component** : Add a deployed component.
* **Add Deployed Artifact** : Add a deployed artifact.

To suppress Attributes, see [Suppress Attributes](../user-guide/formatting-diagram.md#suppress-attributes).

To suppress Operations, see [Suppress Operations](../user-guide/formatting-diagram.md#suppress-operations).

To show or hide Operation Signatures, see [Show Operation Signature](../user-guide/formatting-diagram.md#show-operation-signature).

## Deployment

To create an Deployment:

1. Select **Deployment** in **Toolbox**.
2. Drag from an element \(to be deployed\) and drop on a Node.

You can use **QuickEdit** for Relationship \(See [Relationship](class-diagram.md#relationship)\).

## Communication Path

To create an Communication Path:

1. Select **Communication Path** in **Toolbox**.
2. Drag from a Node and drop on another Node.

You can use **QuickEdit** for Association \(See [Association](class-diagram.md#association)\).

