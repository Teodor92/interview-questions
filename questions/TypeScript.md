# TypeScript interview questions

## 1. Which are the different data types supported by TypeScript? What do they represent?

> `boolean`, `number`, `string`, `object`, `Array`, `enum`, `any`, `void`, `never`, `unknown`

## 2. What are classes in TypeScript?

> They are basically ES6 classes with additional features like access modifiers, indexers etc.

## 3. Does TypeScript support abstract classes? And what about interfaces? What is the difference?

> Yes to both. The interface cannot have any implementation of it's methods in contrast to the abstract class. Additionally the abstract class can have fields.

## 4. What types of access modifiers exit in a TypeScript class? What does each do?

> `private`, `public` and `protected`

## 5. How do you implement inheritance in TypeScript?

> Same as ES6 inheritance.

## 6. How do you implement and interface for a specific class?

> Using the `implements` keyword.

## 8. How do you call a base class constructor or a base class method form a child class?

> Using the `super` keyword.

## 9. How can you expose a class/method/variable to the outside world?

> Using the `exports` keyword. Same as ES6.

## 10. Does TypeScript support function overloading as JavaScript doesn’t support function overloading?

> Not in a native way, but you can have a single implementation with multiple signatures.

## 11. What is an union type?

> A mix of multiple types using the `|` or `&` operators.