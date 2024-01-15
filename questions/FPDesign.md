# Functional Programming Design

## 1. What is a function?

A function is a process which takes some input, called arguments, and produces some output called a return value. Functions may serve the following purposes:

- Mapping: Produce some output based on given inputs. A function maps input values to output values.
- Procedures: A function may be called to perform a sequence of steps. The sequence is known as a procedure, and programming in this style is known as procedural programming.
- I/O: Some functions exist to communicate with other parts of the system, such as the screen, storage, system logs, or network.

## 2. What is a side effect?

A side effect is anything a method does besides computing and returning a value. Any change of instance or class field values is a side effect, as is drawing something on the screen, writing to a file or a network connection.

Strictly speaking, a "function" is defined as not having side effects - which is why Java uses the word "method" instead. A real function with no return value would be pointless.

Obviously, a method that does not have a return value must have some sort of side effect that justifies its existence. Set methods are an example - the side effect is changing the object's internal state.

## 3. What is a pure function?

- Given the same input, will always return the same output.
- Produces no side effects.

A dead giveaway that a function is impure is if it makes sense to call it without using its return value. For pure functions, that’s a noop.

## 4. What are the pros and cons of functional programming versus - object-oriented programming?

### Functional Programming

Pros:

- **Immutability:** Emphasizes immutable data, reducing side effects and making code more predictable.
- **First-Class Functions:** Treats functions as first-class citizens, enabling higher-order functions.
- **Conciseness:** Tends to be more concise and expressive.
- **Parallel Processing:** Well-suited for parallel processing due to stateless nature.
- **Easier Testing and Debugging:** Pure functions (no side effects) are simpler to test and debug.

Cons:

- **Steep Learning Curve:** Concepts like immutability and higher-order functions can be challenging to learn.
- **Performance Issues:** Immutable data structures can lead to performance overhead.
- **Less Intuitive for Stateful Applications:** Managing state can be less intuitive compared to OOP.

### Object-Oriented Programming

Pros:

- **Modularity:** Allows for creating modular, reusable code using classes and objects.
- **Intuitiveness:** Models real-world entities, which can be more intuitive.
- **Encapsulation:** Enhances code security and avoids unintended interactions.
- **Inheritance and Polymorphism:** Facilitates code reuse and extension.
- **Widely Used:** Widely adopted and understood, with abundant learning resources.

Cons:

- **Overhead:** Can introduce complexity and overhead if not well designed.
- **Mutability:** Objects are typically mutable, which can lead to side effects.
- **Tight Coupling:** Poor design can result in tight coupling, reducing modularity.
- **Boilerplate Code:** Often requires writing more boilerplate code.
- **Less Efficient for Parallel Processing:** Stateful nature makes parallel processing more challenging.
