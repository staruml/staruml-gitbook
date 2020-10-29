# Statechart Diagram

![Statechart Diagram \(from uml-diagrams.org\)](../.gitbook/assets/bank-atm-state-model-bank-atm-bank-atm-state-model_21.png)

## Create Statechart Diagram

To create a Statechart Diagram:

1. Select first an element where a new Statechart Diagram to be contained as a child.
2. Select **Model \| Add Diagram \| Statechart Diagram** in Menu Bar or select **Add Diagram \| Statechart Diagram** in Context Menu.

> **See also**
>
> [UML Statechart Diagram](http://www.uml-diagrams.org/state-machine-diagrams.html) - For more information about UML Statechart Diagram.

## State

To create a Simple State:

1. Select **Simple State** in **Toolbox**.
2. Drag on the diagram as the size of Simple State.

To create a Composite State:

1. Select **Composite State** in **Toolbox**.
2. Drag on the diagram as the size of Composite State.

To create a Submachine State:

1. Select **Submachine State** in **Toolbox**.
2. Drag on the diagram as the size of Submachine State.
3. Select a StateMachine in **Element Picker Dialog**.

To create an Orthogonal State:

1. Select **Orthogonal State** in **Toolbox**.
2. Drag on the diagram as the size of Orthogonal State.

You can use **QuickEdit** for State by double-click or press `Enter` on a selected State.

* **Name Expression** : Edit name expression.

  _Syntax of Name Expression_

  ```text
  expression ::= [ '<<' stereotype `>>` ] [ visibility ] name
  stereotype ::= (identifier)
  visibility ::= '+' | '#' | '-' | '~'
  name ::= (identifier)
  ```

* **Add ConnectionPointReference** : Add a connection point reference.
* **Add Region** : Add a region.
* **Add Note** : Add a linked note.
* **Add Constraint** : Add a constraint.
* **Add Entry Activity** : Add an entry activity.
* **Add Do Activity** : Add an do activity.
* **Add Exit Activity** : Add an exit activity.
* **Add Internal Transition** : Add an internal transition.

## Internal Activity

To add an Entry Activity:

1. Select a State.
2. Select **Model \| Add \| Entry Activity** in Menu Bar or **Add \| Entry Activity** in Context Menu.
3. Select a kind of Activity to create \(one of OpaqueBehavior, Activity, StateMachine, or Interaction\).

To add a Do Activity:

1. Select a State.
2. Select **Model \| Add \| Do Activity** in Menu Bar or **Add \| Do Activity** in Context Menu.
3. Select a kind of Activity to create \(one of OpaqueBehavior, Activity, StateMachine, or Interaction\).

To add an Exit Activity:

1. Select a State.
2. Select **Model \| Add \| Exit Activity** in Menu Bar or **Add \| Exit Activity** in Context Menu.
3. Select a kind of Activity to create \(one of OpaqueBehavior, Activity, StateMachine, or Interaction\).

You can use **QuickEdit** for Model Element \(See [Model Element](class-diagram.md#model-element)\).

## Internal Transition

To add an Internal Transition:

1. Select a State.
2. Popup Quic Edit for State by double click or press `Enter` on a selected State.
3. Select **Add Internal Transition** button in Quick Edit.

You can use **QuickEdit** for Internal Transition by double-click or press `Enter` on a selected Internal Transition.

* **Name Expression** : Edit name expression.

  _Syntax of Name Expression_

  ```text
  expression ::= [ '<<' stereotype `>>` ] [ visibility ] name
  stereotype ::= (identifier)
  visibility ::= '+' | '#' | '-' | '~'
  name ::= (identifier)
  ```

* **Add Trigger Event** : Add a trigger event.
* **Add Effect Behavior** : Add an effect behavior.

## Region

To add a Region:

1. Select a State.
2. Select **Model \| Add \| Region** in Menu Bar or **Add \| Region** in Context Menu.

## Initial State

To create a Initial State:

1. Select **Initial State** in **Toolbox**.
2. Click at the position on the diagram.

You can use **QuickEdit** for Model Element \(See [Model Element](class-diagram.md#model-element)\).

## Choice

To create a Choice:

1. Select **Choice** in **Toolbox**.
2. Click at the position on the diagram.

You can use **QuickEdit** for Model Element \(See [Model Element](class-diagram.md#model-element)\).

## Join

To create a Join:

1. Select **Join** in **Toolbox**.
2. Drag on the diagram as the size of Join.

You can use **QuickEdit** for Model Element \(See [Model Element](class-diagram.md#model-element)\).

## Fork

To create a Fork:

1. Select **Fork** in **Toolbox**.
2. Drag on the diagram as the size of Fork.

You can use **QuickEdit** for Model Element \(See [Model Element](class-diagram.md#model-element)\).

## Junction

To create a Junction:

1. Select **Junction** in **Toolbox**.
2. Click at the position on the diagram.

You can use **QuickEdit** for Model Element \(See [Model Element](class-diagram.md#model-element)\).

## Shallow History

To create a Shallow History:

1. Select **Shallow History** in **Toolbox**.
2. Click at the position on the diagram.

You can use **QuickEdit** for Model Element \(See [Model Element](class-diagram.md#model-element)\).

## Deep History

To create a Deep History:

1. Select **Deep History** in **Toolbox**.
2. Click at the position on the diagram.

You can use **QuickEdit** for Model Element \(See [Model Element](class-diagram.md#model-element)\).

## Entry Point

To create a Entry Point:

1. Select **Entry Point** in **Toolbox**.
2. Click at the position on the diagram.

You can use **QuickEdit** for Model Element \(See [Model Element](class-diagram.md#model-element)\).

## Exit Point

To create a Exit Point:

1. Select **Exit Point** in **Toolbox**.
2. Click at the position on the diagram.

You can use **QuickEdit** for Model Element \(See [Model Element](class-diagram.md#model-element)\).

## Terminate

To create a Terminate:

1. Select **Terminate** in **Toolbox**.
2. Click at the position on the diagram.

You can use **QuickEdit** for Model Element \(See [Model Element](class-diagram.md#model-element)\).

## Final State

To create a Final State:

1. Select **Final State** in **Toolbox**.
2. Click at the position on the diagram.

You can use **QuickEdit** for Model Element \(See [Model Element](class-diagram.md#model-element)\).

## Connection Point Reference

To create a Connection Point Reference:

1. Select **Connection Point Reference** in **Toolbox**.
2. Click on a State where Connection Point Reference to be contained.

You can use **QuickEdit** for Model Element \(See [Model Element](class-diagram.md#model-element)\).

## Transition

To create a Transition \(or Self Transition\):

1. Select **Transition** \(or **Self Transition**\) in **Toolbox**.
2. Drag from a State and drop on another State. \(Just click on a State if you want to create a Self Transition.\)

You can use **QuickEdit** for Transition by double-click or press `Enter` on a selected Transition.

* **Transition Expression** : Edit transition expression.

  _Syntax of Transition Expression_

  ```text
  transition ::= [ trigger-list ] [ '[' guard ']' ] [ '/' effect ]
  trigger-list ::= trigger [ ',' trigger ]
  trigger ::= (identifier)
  guard ::= (string)
  effect ::= (identifier)
  ```

* **Add Note** : Add a linked note.
* **Add Constraint** : Add a constraint.
* **Add Trigger Event** : Add a trigger event.
* **Add Effect Behavior** : Add an effect behavior.

