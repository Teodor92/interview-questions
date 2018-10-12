# Functional Programing Design

## 1. What is a function?

> A function is a process which takes some input, called arguments, and produces some output called a return value. Functions may serve the following purposes:

> - Mapping: Produce some output based on given inputs. A function maps input values to output values.
> - Procedures: A function may be called to perform a sequence of steps. The sequence is known as a procedure, and programming in this style is known as procedural programming.
> - I/O: Some functions exist to communicate with other parts of the system, such as the screen, storage, system logs, or network.

## 2. What is a side effect?

> A side effect is anything a method does besides computing and returning a value. Any change of instance or class field values is a side effect, as is drawing something on the screen, writing to a file or a network connection.

> Strictly speaking, a "function" is defined as not having side effects - which is why Java uses the word "method" instead. A real function with no return value would be pointless.

> Obviously, a method that does not have a return value must have some sort of side effect that justifies its existence. Set methods are an example - the side effect is changing the object's internal state.

## 3. What is a pure function?

> - Given the same input, will always return the same output.
> - Produces no side effects.

> A dead giveaway that a function is impure is if it makes sense to call it without using its return value. For pure functions, that’s a noop.

## 4. What are the pros and cons of functional programming versus - object-oriented programming?

> TODO