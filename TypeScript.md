# TypeScript interview questions

- Which are the different data types supported by TypeScript? What do they represent?
> `boolean`, `number`, `string`, `object`, `Array`, `enum`, `any`, `void`, `never`, `unknown`

- What are classes in TypeScript?
> They are basically ES6 classes with additional features like access modifiers, indexers etc.

- Does TypeScript support abstract classes? And what about interfaces? What is the difference?
> Yes to both. The interface cannot have any implementation of it's methods in contrast to the abstract class. Additionally the abstract class can have fields.

- What types of access modifiers exit in a TypeScript class? What does each do?
> `private`, `public` and `protected`

- How do you implement inheritance in TypeScript?
> Same as ES6 inheritance.

- How do you implement and interface for a specific class?
> Using the `implements` keyword.

- How do you call a base class constructor or a base class method form a child class?
> Using the `super` keyword.

- How can you expose a class/method/variable to the outside world?
> Using the `exports` keyword. Same as ES6.

- Does TypeScript support function overloading as JavaScript doesn’t support function overloading?
> Not in a native way, but you can have a single implementation with multiple signatures.

- What is an union type?
> A mix of multiple types using the `|` or `&` operators.