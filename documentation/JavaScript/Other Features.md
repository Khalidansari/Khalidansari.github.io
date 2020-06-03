---
layout: default
---
# Other main features of JS

Source: https://www.w3schools.com/js/js_es6.asp

## Prototype

Instead of using classes, as Java does, JS simply allows to create objects without classes. The inheritence is through a reference to parent object. So each object will have a prototype member which will point to its parent. It is possible for child object to update parent prototype's properties which will then apply to all its children.

Though you cannot add new properties to an object without adding that property to its constructor, you can add it to its prototype. For example - assuming that nationality is not its property currently:

Not Allowed - Person.nationality = "English";
Allowed - Person.prototype.nationality = "English";
