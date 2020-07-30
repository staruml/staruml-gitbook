# Activity Diagram

## Create Activity Diagram

To create an Activity Diagram:

1. Select first an element where a new Activity Diagram to be contained as a child.
2. Select **Model \| Add Diagram \| Activity Diagram** in Menu Bar or select **Add Diagram \| Activity Diagram** in Context Menu.

> **See also**
>
> [UML Activity Diagram](http://www.uml-diagrams.org/activity-diagrams.html) - For more information about UML Activity Diagram.

## Action

To create an Action:

1. Select **Action** in **Toolbox**.
2. Drag on the diagram as the size of Action.

You can use **QuickEdit** for Action by double-click or press `Enter` on a selected Action.

* **Name Expression** : Edit name expression.

  _Syntax of Name Expression_

  ```text
  expression ::= [ '<<' stereotype `>>` ] [ visibility ] name
  stereotype ::= (identifier)
  visibility ::= '+' | '#' | '-' | '~'
  name ::= (identifier)
  ```

* **Add Input Pin** : Add an input pin.
* **Add Output Pin** : Add an output pin.
* **Add Note** : Add a linked note.
* **Add Trigger Event** : Add a trigger event.
* **Add Outgoing Control Flow** : Add an outgoing control flow with an action.
* **Add Incoming Control Flow** : Add an incoming control flow with an action.
* **Add Outgoing Object Flow** : Add an outgoing object flow with an object node.
* **Add Incoming Object Flow** : Add an incoming object flow with an object node.
* **Add Decision** : Add a decision with two additional actions.
* **Add Merge** : Add a merge with two additional actions.
* **Add Fork** : Add a fork with two additional actions.
* **Add Join** : Add a join with two additional actions.
* **Add Initial Node** : Add an initial node with a connected control flow.
* **Add Final Node** : Add an final node with a connected control flow.

## Trigger

To add a Trigger:

1. Select an Action.
2. Select **Model \| Add \| Trigger** in Menu Bar or **Add \| Trigger** in Context Menu.

## Initial Node

To create an Initial Node:

1. Select **Initial** in **Toolbox**.
2. Click at the position on the diagram.

## Activity Final Node

To create an Activity Final Node:

1. Select **Activity Final** in **Toolbox**.
2. Click at the position on the diagram.

## Fork Node

To create a Fork Node:

1. Select **Fork** in **Toolbox**.
2. Drag on the diagram as the size of Fork.

## Join Node

To create a Join Node:

1. Select **Join** in **Toolbox**.
2. Drag on the diagram as the size of Join.

## Merge Node

To create a Merge Node:

1. Select **Merge** in **Toolbox**.
2. Click at the position on the diagram.

## Decision Node

To create a Decision Node:

1. Select **Decision** in **Toolbox**.
2. Click at the position on the diagram.

## Swimlane \(Partition\)

To create a Swimlane \(Vertical or Horizontal\):

1. Select **Swimlane \(Vertical\)** or **Swimlane \(Horizontal\)** in **Toolbox**.
2. Drag on the diagram as the size of Swimlane.

You can use **QuickEdit** for Model Element \(See [Model Element](class-diagram.md#model-element)\).

## Interruptible Activity Region

To create an Interruptible Activity Region:

1. Select **Interruptible Activity Region** in **Toolbox**.
2. Drag on the diagram as the size of Interruptible Activity Region.

## Structured Activity Node

To create a Structured Activity Node:

1. Select **Structured Activity** in **Toolbox**.
2. Drag on the diagram as the size of Structured Activity Node.

You can use **QuickEdit** for Model Element \(See [Model Element](class-diagram.md#model-element)\).

## Input Pin

To create an Input Pin:

1. Select **Input Pin** in **Toolbox**.
2. Click on an Action where Input Pin to be attached.

## Output Pin

To create an Output Pin:

1. Select **Output Pin** in **Toolbox**.
2. Click on an Action where Output Pin to be attached.

## Send Signal

To create a Send Signal:

1. Select **Send Signal** in **Toolbox**.
2. Drag on the diagram as the size of Send Signal.

Send Signal is actually an Action whose kind is `sendSignal`.

## Accept Signal

To create an Accept Signal:

1. Select **Accept Signal** in **Toolbox**.
2. Drag on the diagram as the size of Accept Signal.

Accept Signal is actually an Action whose kind is `acceptSignal`.

## Accept Time Event

To create an Accept Time Event:

1. Select **Accept Time Event** in **Toolbox**.
2. Drag on the diagram as the size of Accept Time Event.

Accept Time Event is actually an Action whose kind is `timeEvent`.

## Flow Final Node

To create a Flow Final Node:

1. Select **Flow Final** in **Toolbox**.
2. Click at the position on the diagram.

## Object Node

To create a Object Node:

1. Select **Object Node** in **Toolbox**.
2. Drag on the diagram as the size of Object Node.

You can use **QuickEdit** for Object Node by double-click or press `Enter` on a selected Object Node.

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
* **Add Outgoing Object Flow** : Add an outgoing object flow with an object node.
* **Add Incoming Object Flow** : Add an incoming object flow with an object node.
* **Add Outgoing Control Flow** : Add an outgoing control flow with an action.
* **Add Incoming Control Flow** : Add an incoming control flow with an action.

## Central Buffer

To create a Central Buffer:

1. Select **Central Buffer** in **Toolbox**.
2. Drag on the diagram as the size of Central Buffer.

You can use **QuickEdit** for Object Node \(See [Object Node](activity-diagram.md#object-node)\).

## Datastore

To create a Datastore:

1. Select **Datastore** in **Toolbox**.
2. Drag on the diagram as the size of Datastore.

You can use **QuickEdit** for Object Node \(See [Object Node](activity-diagram.md#object-node)\).

## Expansion Region

To create a Expansion Region:

1. Select **Expansion Region** in **Toolbox**.
2. Drag on the diagram as the size of Expansion Region.

You can use **QuickEdit** for Model Element \(See [Model Element](class-diagram.md#model-element)\).

## Input Expansion Node

To create an Input Expansion Node:

1. Select **Input Expansion Node** in **Toolbox**.
2. Click on an Expansion Node where Input Expansion Node to be attached.

## Output Expansion Node

To create an Output Expansion Node:

1. Select **Output Expansion Node** in **Toolbox**.
2. Click on an Expansion Node where Output Expansion Node to be attached.

## Control Flow

To create a Control Flow:

1. Select **Control Flow** in **Toolbox**.
2. Drag from a node and drop on another node.

You can use **QuickEdit** for Relationship \(See [Relationship](class-diagram.md#relationship)\).

## Object Flow

To create an Object Flow:

1. Select **Object Flow** in **Toolbox**.
2. Drag from a node and drop on another node.

## Exception Handler

To create an Extension Handler:

1. Select **Extension Handler** in **Toolbox**.
2. Drag from a node and drop on another node.

## Activity Interrupt

To create an Activity Interrupt:

1. Select **Activity Interrupt** in **Toolbox**.
2. Drag from a node and drop on another node.

You can use **QuickEdit** for Relationship \(See [Relationship](class-diagram.md#relationship)\).

