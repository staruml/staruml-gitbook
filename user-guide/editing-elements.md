# Editing Elements

## Editing Diagrams

### Create Diagram

To create a Diagram:

1. Select first an element where a new Diagram to be contained as a child in **Explorer**.
2. Select **Model \| Add Diagram \| \[DiagramType\]** in Menu Bar or select **Add Diagram \| \[DiagramType\]** in Context Menu.

### Delete Diagram

To delete a Diagram:

1. Select a Diagram to delete in **Explorer**.
2. Press `Ctrl+Delete` or select **Edit \| Delete from Model** in Menu Bar or **Delete from Model** in Context Menu.

### Open Diagram

To open a diagram, double-click a diagram in **Explorer**.

### Close Diagram

To close a diagram, click the close icon \(`x` mark\) of a diagram in **Working Diagrams** or press `F4` or select **View \| Close Diagram** in Menu Bar.

To close other diagram except a active diagram, press `Ctrl+F4` or select **View \| Close Other Diagrams** in Menu Bar.

To close all diagrams, press `Shift+F4` or select **View \| Close All Diagrams** in Menu Bar.

### Change Active Diagram

To change active diagram, select a diagram in **Working Diagram**.

To activate the next diagram, press `Ctrl+Shift+]` or select **View \| Next Diagram**.

To activate the previous diagram, press `Ctrl+Shift+[` or select **View \| Previous Diagram**.

## Editing Elements

### Create Element

You have following options to create Model Elements and View Elements.

To create an Element from **Toolbox**:

1. Select **\[ElementType\]** in **Toolbox**.
2. Drag on the diagram as the size of element, or link two elements if the element is a kind of relationship.

> **Note**
>
> In most cases, creating an element from **Toolbox** means creating the both Model Element and View Element. For example, if you create a Class in a Diagram from Toolbox, a Class Model Element and a Class View Model which referencing the Model Element will be created. See [Basic Concepts](basic-concepts.md)

If you have already _Model Elements_, you can create _View Elements_ referencing the _Model Element_ on a _Diagram_.

To create a _View Element_ by drag and drop:

1. Select a Model Element in **Explorer**.
2. Drag the Model Element and drop on a Diagram.

To create a _Model Element_ in **Explorer**:

1. Select first an element where a new Model Element to be contained as a child in **Explorer**.
2. Select **Model \| Add \| \[ElementType\]** in Menu Bar or select **Add \| \[ElementType\]\`** in Context Menu.

### Delete Elements

> **See also**
>
> [Basic Concepts](basic-concepts.md) - Before deleting elements, you need to distinguish the difference of Model Element, View Element, and Diagram.

To delete View Elements in a Diagram.

1. Select View Elements to be deleted in a Diagram.
2. Press `Delete` or Select **Edit \| Delete** in Menu Bar or **Delete** in Context Menu.

> **Note**
>
> Deleting View Elements do not delete Model Elements.

To delete Model Elements:

1. Select Elements to be deleted in a Diagram or in **Explorer**.
2. Press `Ctrl+Delete` or Select **Edit \| Delete from Model** in Menu Bar or **Delete from Model** in Context Menu.

> **Note**
>
> Model Elements are always deleted with corresponding View Elements.

### Select Elements

To select view elements in **Diagram Editor**:

You can select an Element in Diagram just by clicking on an Element. If you want to select additional elements while keeping current selections, click on element with pressing `Shift`. When you drag an area, Elements overlaps the area will be selected. Pressing `Shift` also work with dragging.

If you want to select all elements in the Diagram, press `Ctrl+A` or select **Edit \| Select All** in Menu Bar or **Select All** in Context Menu.

> **Note**
>
> Selecing an Element on a Diagram means selection of the both Model Element and View Element.

To select a model element in **Explorer**:

In **Explorer**, you can select a Model Element by clicking on an Element.

If you want to select an element in **Explorer** corresponding to the a selected element in Diagram, press `Ctrl+E` or select **Edit \| Select In Explorer** in Menu Bar or **Select In Explorer** in Context Menu.

### Copy and Paste

When copying or cutting elements for pasting, a clear distinction has to be made between model elements and view elements. If a model element is copied, it has to be pasted under a model element. In this case, all the sub-elements contained in the selected element are copied together. View elements can be copied within the same diagram or to different diagrams. Copied view elements can be pasted in diagrams only; they cannot be pasted to model elements. Copying and pasting may also be restricted depending on the view element types and diagram types.

To copy and paste view elements in **Diagram Editor**

1. Select view elements in a diagram to copy. \(You can select multiple elements. See [Select Elements](editing-elements.md#select-elements)\)
2. Press `Ctrl+C` or select **Edit \| Copy** in Menu Bar or **Copy** in Context Menu. \(To cut view elements, press `Ctrl+X` or select **Edit \| Cut** in Menu Bar or **Cut** in Context Menu\)
3. Open the diagram where the copied view elements to be pasted. \(See open diagram??\)
4. Press `Ctrl+V` or select **Edit \| Paste** in Menu Bar or **Paste** in Context Menu. The copied view elements will be pasted to the active diagram.

To copy and paste a model element in **Explorer**:

1. Select a model element to copy in **Explorer**.
2. Press `Ctrl+C` or select **Edit \| Copy** in Menu Bar or **Copy** in Context Menu. \(To cut view elements, press `Ctrl+X` or select **Edit \| Cut** in Menu Bar or **Cut** in Context Menu\)
3. Select a model element where the copied element will be pasted in **Explorer**.
4. Press `Ctrl+V` or select **Edit \| Paste** in Menu Bar or **Paste** in Context Menu. The copied view elements will be pasted to the active diagram. The copied model element can be pasted in where an element is able to contain.

> **Note**
>
> Some elements are not allowed to copy, cut, and paste.

### Undo and Redo

To undo an action, press `Ctrl+Z` or select **Edit \| Undo** in Menu Bar.

To redo an undo-ed action, press `Ctrl+Y` or select **Edit \| Redo** in Menu Bar.

### Edit Properties

You can edit properties of model elements in **Property Editor**.

### Documenting Elements

You can edit documentation of model elements in **Documentation Editor**.

## Extending Elements

### Assign Stereotype

To assign defined stereotype to elements \(e.g. defined in UML Standard Profile\):

1. Select model elements to assign stereotype.
2. Click the magnifier icon on the right side of `stereotype` property in **Property Editor**.
3. Select a stereotype in **Element Picker Dialog**.

To assign temporal stereotype to elements:

1. Select model elements to assign stereotype.
2. Enter stereotype name in `stereotype` property in **Property Editor**.

### Add Constraints

To add a Constraint to an element:

1. Select model elements to add a constraint.
2. Select **Model \| Add \| Constraint** in Menu Bar or select **Add \| Constraint** in Context Menu.
3. Edit constraint in `specification` property in **Property Editor**.

### Add Tags

Tag is an element to add extended properties to Model Elements

To add a Tag to an element:

1. Select an Element in **Explorer** or in a Diagram.
2. Select **Model \| Add \| Tag** in Menu Bar or select **Add \| Tag** in Context Menu.

Properties of Tag:

* `name` : Name of Tag
* `kind` : Kind of Tag. `kind` could be one of `string`, `reference`, `boolean`, `number`, or `hidden`. if `hidden` is chosen, this Tag will not be shown on View Element.
* `value` : Value of Tag when `kind` is `string`.
* `reference` : Reference value of Tag when `kind` is `reference`.
* `checked` : Boolean value of Tag when `kind` is `boolean`.
* `number` : Number value of Tag when `kind` is `number`.

To show or hide Tags on View Elements, see [Show Property](formatting-diagram.md#show-property).

## Finding Model Elements

To find model elements by keyword:

1. Press `Ctrl+F` or Select **Model \| Find...** in Menu Bar.
2. Enter keyword in Edit Box.
3. Check **Case sensitive** if you want to find keyword case sensitively, and check **Find in documentation** if you want to find keyword in documentation of elements.
4. Matched elements will be shown on a Bottom Panel.

