# Defining Preferences

In this chapter, we're going to learn how to define preferences. When you developing your own extensions, you may want to allow users to make preferred settings.

To define your own preferences, use `app.preferences`.

## Defining preference schema

Before we get in detail, it's better to take a look at an example. Following is a part of preference schema of [Java extension](https://github.com/staruml/staruml-java).

```javascript
var javaPreferences = {
  id: "java",
  name: "Java",
  schema: {
    "java.gen": {
      text: "Java Code Generation",
      type: "section"
    },
    "java.gen.useTab": {
      text: "Use Tab",
      description: "Use Tab for indentation instead of spaces.",
      type: "check",
      default: false
    },
    "java.gen.indentSpaces": {
      text: "Indent Spaces",
      description: "Number of spaces for indentation.",
      type: "number",
      default: 4
    },
    ...
  }
}
...
app.preferences.register(javaPreferences)
```

This preference schema will be shown in **Preferences Dialog** as the below image.

![PreferenceDialog](https://github.com/staruml/staruml-dev-docs/blob/master/images/PreferenceDialog.png?raw=true)

As shown in the above example, a preference schema have a _unique ID_, _name_, and a set of _preference items_. You can register a preference schema by `app.preferences.register` function.

A preference item should have the following properties.

* **key** : Unique identifier of preference item. It should be unique in all of the preference schemas, so it's strongly recommend to include all the IDs of preference schema and section \(e.g. `java.gen.useTab`, `java.gen.indentSpaces`\).
* **text** : Name of preference item. It will be shown in **Preferences Dialog** instead of `key`.
* **description** : Short description of preference item.
* **type** : Type of preference item. Available types will be described later.
* **default** : Default value of preference item.
* **width** _\(optional\)_ : Width of widget for preference item in **Preferences Dialog**. 
* **options** _\(optional\)_ : Options users can select one of. This property is mandatory for `Combo` or `Dropdown` preference items. This property should be defined as an array of objects having two fields: `value` and `text`. \(e.g. `[ { value: 0, text: "female" }, { value: 1, text: "male" } ]` \)

Available types of preference item are as follow.

* **section** : Just for grouping preference items, so it has no actual preference value.
* **string** : Allows users can edit a text \(a string value\).
* **check** : Allows users can check or uncheck \(a boolean value\).
* **number** : Allows users can edit a number value \(an integer value\).
* **combo** : Allows users can edit or select a value from the defined options.
* **dropdown** : Allows users can select from the defined options.
* **color** : Allows users can select a color value. This type of preference item allow to set `default` property value to `null`. It means nothing selected. Additionally, allow to define `defaultButton` property like as `defaultButton: { text: "Use Default Color" }`. When it defined, a button is shown in front of color widget in **Preferences Dialog** and changes to default color when it pressed.

## Reading preference values

You can read value of a particular preference item by calling `get` function with key of the preference item. It returns user selected value or default value. If passed undefined key, it returns `null` value.

```javascript
app.preferences.get("java.gen.useTab") // false
app.preferences.get("java.gen.indentSpaces") // 4
app.preferences.get("java.gen.undefined-item") // null
```

## Writing preference values

You can also write value for a particular preference item by calling `set` function with key and value. Note that you have to pass value of correct type conform to the type of preference item. For example, do not pass string value to a preference item of **check** type.

```javascript
app.preferences.set("java.gen.useTab", true)
app.preferences.set("java.gen.indentSpaces", 2)
app.preferences.get("java.gen.useTab") // true
app.preferences.get("java.gen.indentSpaces") // 2
```

