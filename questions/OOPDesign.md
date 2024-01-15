# OOP Design

## 1. What is OOP and what are the 4 pillars of OOP?

1. **Encapsulation:**
   - **Description:** Encapsulation is the bundling of data (attributes) and methods that operate on the data into a single unit, or class. It restricts direct access to some of an object's components, which is a means of preventing accidental interference and misuse of the methods and data.
   - **Benefits:** Increases security and hides the implementation details from the user.

2. **Abstraction:**
   - **Description:** Abstraction involves hiding complex implementation details and showing only the necessary features of the object. It helps in reducing programming complexity and effort.
   - **Benefits:** Simplifies the view of an object, and separates the interface from the implementation.

3. **Inheritance:**
   - **Description:** Inheritance is a mechanism where a new class is derived from an existing class. The new class, known as a subclass, inherits attributes and methods of the existing class, known as a superclass.
   - **Benefits:** Promotes code reuse, and establishes a relationship between different classes.

4. **Polymorphism:**
   - **Description:** Polymorphism means 'many forms'. It allows objects of different classes to be treated as objects of a common superclass. It can be achieved by overriding (same method names in different classes) or overloading (same method name, different parameters).
   - **Benefits:** Enhances flexibility and integration by allowing the same interface for different underlying forms (data types).

## 2. What is an object and what is a class?

### Class

- **Definition:** A class is a blueprint or template for creating objects. It defines a set of properties (attributes) and methods (functions) that the created objects will have.
- **Characteristics:**
  - **Attributes:** Represent the data or state. Example: In a class `Car`, attributes could be `color`, `brand`, and `model`.
  - **Methods:** Represent the behavior or functionality. Example: In a class `Car`, methods could be `drive()` and `brake()`.
- **Role:** A class is a conceptual model or a prototype that defines the structure and behavior of objects but does not represent any actual data or state on its own.

### Object

- **Definition:** An object is an instance of a class. When a class is defined, no memory is allocated until an object of that class is created.
- **Characteristics:**
  - **Instance:** Each object is an instance of a class, containing real data or state.
  - **Unique Identity:** Every object has a unique identity and its own set of values for the class attributes.
- **Example:** If `Car` is a class, then a specific car like `myCar = new Car('red', 'Toyota', 'Corolla')` is an object of the `Car` class.

### Relationship Between Class and Object

- A class can be seen as a template, while an object is a concrete instance of that class.
- Classes define the properties and behavior that their objects share, and an object is a specific instance of a class, with actual values for the properties.

## 3. What is multiple inheritance and what is specific about it?

Multiple inheritance is a feature of some object-oriented programming languages in which a class can inherit behaviors and characteristics from more than one parent class. This contrasts with single inheritance, where a class may only inherit from one parent class.

- **Combining Features:** Allows a class to inherit attributes and methods from more than one superclass.
- **Complexity:** Can make the class structure more complex and harder to manage.
- **Diamond Problem:** A notable issue where a class inherits from two classes that both inherit from a common superclass, potentially causing ambiguity in which version of the superclass's attributes and methods the subclass should inherit.

## 4. What does “favor object composition over class inheritance” mean?

It means that code reuse should be achieved by assembling smaller units of functionality into new objects instead of inheriting from classes and creating object taxonomies.
In other words, use can-do, has-a, or uses-a relationships instead of is-a relationships. Using this approach we:
- Avoid class hierarchies.
- Avoid brittle base class problem.
- Avoid tight coupling.
- Avoid rigid taxonomy (forced is-a relationships that are eventually wrong for new use cases).
- Avoid the gorilla banana problem (“what you wanted was a banana, what you got was a gorilla holding the banana, and the entire jungle”).
- Make code more flexible.

## 5. What is the diamond problem?

A notable issue where a class inherits from two classes that both inherit from a common superclass, potentially causing ambiguity in which version of the superclass's attributes and methods the subclass should inherit.

## 6. What is the Banana Monkey Jungle problem?

The Banana Monkey Jungle problem is a metaphor used in software engineering to describe a situation where a developer wants a 'banana' (a specific piece of functionality) but ends up getting the 'monkey' (the module or class that contains the functionality) and the entire 'jungle' (the whole environment or framework on which the module depends).

### Key Points

- **Software Reuse Issue:** This problem highlights the challenges in reusing a small part of a software module or framework. The desired functionality (the banana) cannot be easily extracted without bringing along a large, often unnecessary, set of additional dependencies (the monkey and the jungle).
- **Complex Dependencies:** It emphasizes how software dependencies can become complex and intertwined, making it difficult to isolate individual components.
- **OOP and Inheritance:** Often cited in the context of object-oriented programming, particularly with deep inheritance hierarchies, where inheriting from a superclass might bring along more functionality than desired.

### Implications

- **Increased Complexity:** The unnecessary complexity and overhead can make the system more difficult to understand, maintain, and scale.
- **Challenge in Modular Design:** It underscores the importance of creating modular, decoupled software components that can be reused independently.

### Solutions

- **Composition Over Inheritance:** Favor composition over inheritance to avoid deep and complex inheritance hierarchies.
- **Modular Design:** Design software in a modular fashion, where dependencies are minimized, and components can be used independently.
- **Clear Interfaces:** Define clear interfaces and contracts for modules to ensure they can be used without pulling in unnecessary dependencies.
