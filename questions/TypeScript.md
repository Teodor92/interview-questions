# TypeScript interview questions

## 1. Which are the different data types supported by TypeScript? What do they represent?

| Level | P1+ |
| ----- | --- |

> `boolean`, `number`, `string`, `object`, `Array`, `enum`, `any`, `void`, `never`, `unknown`

## 2. What are classes in TypeScript?

| Level | P1+ |
| ----- | --- |

> They are basically ES6 classes with additional features like access modifiers, indexers etc.

## 3. Does TypeScript support abstract classes? And what about interfaces? What is the difference?

| Level | P1+ |
| ----- | --- |

> Yes to both. The interface cannot have any implementation of it's methods in contrast to the abstract class. Additionally the abstract class can have fields.

## 4. What types of access modifiers exit in a TypeScript class? What does each do?

| Level | P1+ |
| ----- | --- |

> `private`, `public` and `protected`

## 5. How do you implement inheritance in TypeScript?

| Level | P1+ |
| ----- | --- |

> Same as ES6 inheritance.

## 6. How do you implement and interface for a specific class?

| Level | P1+ |
| ----- | --- |

> Using the `implements` keyword.

## 8. How do you call a base class constructor or a base class method form a child class?

| Level | P1+ |
| ----- | --- |

> Using the `super` keyword.

## 9. How can you expose a class/method/variable to the outside world?

| Level | P1+ |
| ----- | --- |

> Using the `exports` keyword. Same as ES6.

## 10. Does TypeScript support function overloading as JavaScript doesn’t support function overloading?

| Level | P1+ |
| ----- | --- |

> Not in a native way, but you can have a single implementation with multiple signatures.

## 11. What is an union type?

| Level | P2+ |
| ----- | --- |

> A mix of multiple types using the `|` or `&` operators.