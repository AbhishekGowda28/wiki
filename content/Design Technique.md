---
publish: true
created: 2026-03-21T11:10:35.188+05:30
modified: 2026-05-18T15:34:50.914+05:30
---

**Design Skills,** is combination of **Design principles** and **Design Patterns.**

Design Principles are general guidelines, like to reuse the code, to have openness in the class to be extended and such things.

Design Patterns on the other hand are specific guidelines/solutions for solving a problem.

- Inheritance is a core principle of Object Oriented Programming. We can identify inheritance with **IS-A** relation. Example Square **IS-A** Shape. Circle **IS-A** Shape. We would be templated to use is-a relation on everything, we need to be careful when doing so.

  - Separate what varies: Seperating out what varies into a different interface would give flexibility.

  - Programming to an interface, not to an implementation. First think about what is intended, think it in terms of interface then think how it can be added/extended to a class.

## Design Patterns

Design patterns are specific solutions or thinking for a familiar or family of problems

- Object is an instance of a class
- A concrete reference refers to any occurrence of an object during the run time
- Always `Subclass` implements `SuperClass`

### Strategy Pattern

- A family of algorithm that are encapsulated away into an interface which is composed with the object at run time.

### Adaptor Pattern

The pattern that convert the interface a class that the other class (client class) expects. The allows the classes to work together otherwise because of the incompatible interfaces.

### Observer Pattern

- In the patterns design objects are loosely coupled. One object will be a subscriber and other will be publisher. Subscriber registers to publisher for events and when their are events from publisher, subscribers will get them. This goes on until, subscriber de-registers from the publisher.

### Decorator Pattern

Again here we make use of compositions. Here the base objects is decorated or encapsulated onto other classes, where the base object gets decorated with each pass of the object.

```java
class Coffee {
	public static void main(){
		Baverage baverage = new BaseBaverage();
		baverage = new Mocha(baverage); // Decorating the base object with new properties
		baverage = new Sugar(baverage); // Here again, we are updating the previous object `baverage` with addition of Sugar
	}
}

```

## Design Principles

Design principles are generalization guidelines that needs to be followed. Generally these are the SOLID principles that were coined by Uncle Bob.

- S: Single responsibility principle
- O: Open and Close principle
- L: Liskov Substitution principle
- I: Interface segregation principle
- D: Dependency inversion principle

#### Open & Close principle

The class should be open to extension but closed to modification

---

### Links

- https://www.linkedin.com/learning/programming-foundations-design-patterns-2
