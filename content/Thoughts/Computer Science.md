---
publish: true
created: 2026-05-29T08:57:36.072+05:30
modified: 2026-06-01T12:13:51.809+05:30
---

Server Side Rendering - SSR also called as universal rendering or Isomorphic rendering

Abstraction : The purpose of an abstraction is to understand the universe with very little information.

Notations

- Class Diagram
- State Diagram
- Interaction Diagram

---

## Class Diagram

- Class diagram represents the object and it's properties-attributes and methods
- Objects that are created from the same class are identical but not the same
  Example :

```js
const rectangle1 = new Shape();
const rectangle2 = new Shape();
```

The above 2 objects are created using the same class but they are 2 different objects.

Each object knows it's class, most OO programming languages can determine the class of the object at run time. **An objects class is an implicit property of the object.**

Same operation may perform different actions in different object, such operations are called **polymorphic**.
_Example_. `rectange.area()` would do different action then `circle.area()`, even if both objects are created from same class.
