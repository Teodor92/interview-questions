# JavaScript(ES5/ES6) Interview Questions

## 1. Does JavaScript pass parameter by value or by reference?

| Level | Easy |
| ----- | --- |

> **It's always pass by value**, but for objects the value of the variable is a reference. Because of this, when you pass an object and change its members, those changes persist outside of the function. This makes it look like pass by reference. But if you actually change the value of the object variable you will see that the change does not persist, proving it's really pass by value.

## 2. What is the keyword **this** in JavaScript? What problems can it - cause?

| Level | Easy |
| ----- | --- |

> The `this` keyword refers to different things in different context and that is the may reason it can be troublesome. [This](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this) is a short summary of what `this` can mean in different contexts. The easiest rule of thumb - always prefer arrow functions as there behavior is the most 'normal'.

## 3. What’s the difference between a variable that is: `null`, `undefined`, or `undeclared`?

| Level | Easy |
| ----- | --- |

> - A variable is `undeclared` when it does not use the var keyword. It gets created on the global object (that is, the window), thus it operates in a different space as the declared variables. Note: This will not work in strict mode plus you really should not use global variables.
> - Something is `undefined` when it hasn’t been defined yet. If you call a variable or function without having actually created it yet the parser will give you an not defined error.
> - `null` is a variable that is defined to have a null value.

> Or in short:
> - `undeclared` variables don’t even exist
> - `undefined` variables exist, but don’t have anything assigned to them
> - `null` variables exist and have null assigned to them

## 4. What is `===` and `!==` operator?

| Level | Easy |
| ----- | --- |

> This is strict equality. For strict equality the objects being compared must have the same type and:
> - Two strings are strictly equal when they have the same sequence of characters, same length, and same characters in corresponding positions.
> - Two numbers are strictly equal when they are numerically equal (have the same number value). `NaN` is not equal to anything, including NaN. Positive and negative zeros are equal to one another.
> - Two Boolean operands are strictly equal if both are true or both are false.
> - Two objects are strictly equal if they refer to the same `Object`.
> - `Null` and `Undefined` types are `==` (but not `===`). [I.e. (`Null == Undefined`) is `true` but (`Null === Undefined`) is `false`]

## 5. What is the drawback of creating true private methods in - JavaScript?

| Level | Easy |
| ----- | --- |

> In ES5 creating true private method in javascript is very memory inefficient because a new copy of the method would be created for each instance.
> This will change with ES9 as there is a [Stage 3 proposal](https://github.com/tc39/proposal-private-methods) for private methods:

## 6. What is a potential pitfall with using `typeof bar === "object"` to - determine if bar is an object? How can this pitfall be avoided?

| Level | Easy |
| ----- | --- |

> `Null` and `Array` is also considered objects! In order to avoid this behavior check explicitly for these cases.

## 7. What is a closure? How to create one in JavaScript?

| Level | Easy |
| ----- | --- |

> When a function (foo) declares other functions (bar and baz), the family of local variables created in foo is not destroyed when the function exits. The variables merely become invisible to the outside world.
> Foo can therefore cunningly return the functions bar and baz, and they can continue to read, write and communicate with each other through this closed-off family of variables ("the closure") that nobody else can meddle with, not even someone who calls foo again in future.
[Source](https://stackoverflow.com/a/111111/2109394)

## 8. What is an anonymous function?

| Level | Easy |
| ----- | --- |

> Anonymous function are just functions declarations without a name. Every time you write the function keyword, anywhere in your code, giving it a name right after is actually optional. Omitting the name makes the function, well, anonymous.

## 9. What is duck/weak typing?

| Level | Medium |
| ----- | --- |

> It is a term used in dynamic languages that do not have strong typing. The idea is that you don't need a type in order to invoke an existing method on an object - if a method is defined on it, you can invoke it. The name comes from the phrase "If it looks like a duck and quacks like a duck, it's a duck".

## 10. What are higher order functions? Provide an example in the - context of JavaScript?

| Level | Easy |
| ----- | --- |

> Functions in JavaScript are first-class objects. You can pass them into other functions as arguments just like any other object and these parameter functions are called higher order functions.

## 11. What is function currying? How would you implement currying for - any functions?

| Level | Medium |
| ----- | --- |

> Currying is when you break down a function that takes multiple arguments into a series of functions that take part of the arguments.
>
> ```javascript
> function add (a, b) {
>  return a + b;
> }
>
>add(3, 4); // returns 7
> // Same function using curring.
>function add (a) {
>  return function (b) {
>    return a + b;
>  }
>}
> ```

## 12. What is the difference between a **function declaration** and a - **function expression**?

| Level | Easy |
| ----- | --- |

> They are mostly similar except:
> - Function declarations load before any code is executed.
> - Function expressions load only when the interpreter reaches that line of code.

## 13. What is the difference between a function and an arrow function?

| Level | Easy |
| ----- | --- |

> There are two major differences:
> - Lexical `this` and `arguments` - Arrow functions don't have their own this or arguments binding. Instead, those identifiers are resolved in the lexical scope like any other variable. That means that inside an arrow function, this and arguments refer to the values of this and arguments in the environment the arrow function is defined in (i.e. "outside" the arrow function).
> - Arrow functions cannot be called with `new`

## 14. What is JavaScript Self-Invoking anonymous function or - Self-Executing anonymous function?

| Level | Easy |
| ----- | --- |

> - Immediately invoked functions are typically used to create a local function scope that is private and cannot be accessed from the outside world and can define it's own local symbols without affecting the outside world.

## 15. What are promises?

| Level | Easy |
| ----- | --- |

> A promise is an object that may produce a single value some time in the future: either a resolved value, or a reason that it’s not resolved (e.g., a network error occurred). A promise may be in one of 3 possible states: fulfilled, rejected, or pending. Promise users can attach callbacks to handle the fulfilled value or the reason for rejection.

## 16. How do you check if an object is an array or not?

| Level | Easy |
| ----- | --- |

> `Array.isArray()`

## 17. What is the difference between **call** and **apply**?

| Level | Easy |
| ----- | --- |

> The difference is that apply lets you invoke the function with arguments as an array; call requires the parameters be listed explicitly. A useful mnemonic is "A for array and C for comma."

## 18. What is function hoisting in JavaScript?

| Level | Easy |
| ----- | --- |

> In short function hoisting means that functions are moved to the top of their scope. NEVER depend on hoisting as it can produce unexpected behavior.

## 19. What is the difference between classical inheritance and - prototypal inheritance?

| Level | Easy |
| ----- | --- |

> A very complex question but in short:
> - Class Inheritance: A class is like a blueprint — a description of the object to be created. Classes inherit from classes and create subclass relationships: hierarchical class taxonomies.
> - Prototypal Inheritance: A prototype is a working object instance. Objects inherit directly from other objects.

## 20. When should you use **let** and when **var**? What is the difference - between the two?

| Level | Easy |
| ----- | --- |

> You should always prefer `let` over `var`.
> - `let` has block scoping and `var` is function scoped - this may lead to strange behavior as variable declared in a block scope can be accessed ousted of it.
> - `let` can be update but not redeclared.
> - Just like `var`, `let` declarations are hoisted to the top. Unlike `var` which is initialized as undefined, the `let` keyword is not initialized. So if you try to use a let variable before declaration, you'll get a `Reference Error`.

## 21. What is the difference between a **let** variable and a **const** - variable? Provide an example.

| Level | Easy |
| ----- | --- |

> `const` cannot be updated or re-declared BUT there is some specific behavior:
> - value types are constants.
> - reference types have there reference constant BUT there values can be changed. So you can add elements to a `const` Array.

## 22. What does **destructuring assignment** mean?

| Level | Easy |
| ----- | --- |

> Destructuring assignment is a special syntax that allows us to “unpack” arrays or objects into a bunch of variables, as sometimes they are more convenient. Destructuring also works great with complex functions that have a lot of parameters, default values, and soon we’ll see how these are handled too.

## 23. How to achieve encapsulation in the context of JavaScript?

| Level | Easy |
| ----- | --- |

> - In the context of module based Functional programing - we can do that by exporting only public functions from our modules and leaving the other ones as private.
> - In the context of OOP we can mimic the private members of class or use the new es9 private methods and accessors feature.

## 24. What are generators? What is lazy evaluation?

| Level | Easy |
| ----- | --- |

> A generator is a function that can stop midway and then continue from where it stopped. In short, a generator appears to be a function but it behaves like an iterator.

> Lazy Evaluation is an evaluation model which delays the evaluation of an expression until its value is needed. That is, if we don’t need the value, it won’t exist. It is calculated as we demand it. Generators are lazy evaluated.

## 25. What is the difference between synchronous, asynchronous and - parallel function calls? How can do each one in JavaScript?

| Level | Easy |
| ----- | --- |

> - Synchronous programing is the default paradigm. Things execute one after another.
> For the other two types you can imagine the following scenario:
> - Asynchronous: Go away and do this task, when you're finished come back and tell me and bring the results. I'll be getting on with other things in the mean time.

> - Parallel: I want you to do this task. If it makes it easier, get some folks in to help. This is urgent though, so I'll wait here until you come back with the results. I can do nothing else until you come back.

> In JavaScript we can use callbacks, Promises and async/await to do async programing and WebWorkers to do parallel programming.

## 26. Why is it bad to use global variables? Give examples.

| Level | Easy |
| ----- | --- |

> The main reason is the shared state problem:

> The problem with global variables is that since every function has access to these, it becomes increasingly hard to figure out which functions actually read and write these variables.

> To understand how the application works, you pretty much have to take into account every function which modifies the global state. That can be done, but as the application grows it will get harder to the point of being virtually impossible (or at least a complete waste of time).

> If you don't rely on global variables, you can pass state around between different functions as needed. That way you stand a much better chance of understanding what each function does, as you don't need to take the global state into account.

## 27. What is event bubbling?

| Level | Easy |
| ----- | --- |

> When an event is triggered on an element, for example a mouse click on a button, the same event is also triggered on all of that element’s ancestors. This process is known as event bubbling;

## 28. What is event delegation and what problem does it solve?

| Level | Medium |
| ----- | --- |

> Event delegation makes use of two often overlooked features of JavaScript events: event bubbling and the target element. When an event is triggered on an element, for example a mouse click on a button, the same event is also triggered on all of that element’s ancestors. This process is known as event bubbling; the event bubbles up from the originating element to the top of the DOM tree.
> The target element of any event is the originating element, the button in our example, and is stored in a property of the event object. Using event delegation it’s possible to add an event handler to an element, wait for an event to bubble up from a child element and easily determine from which element the event originated.

## 29. What is the difference between throttling and debouncing?

| Level | Medium |
| ----- | --- |

> - Throttling will delay executing a function. It will reduce the notifications of an event that fires multiple times.
> - Debouncing will bunch a series of sequential calls to a function into a single call to that function. It ensures that one notification is made for an event that fires multiple times.

> If you have a function that gets called a lot - for example when a resize or mouse move event occurs, it can be called a lot of times. If you don't want this behaviour, you can Throttle it so that the function is called at regular intervals. Debouncing will mean it is called at the end (or start) of a bunch of events.

## 30. What is the event loop?

| Level | Medium |
| ----- | --- |

> TODO: A very large topic. Not sure if it's a good question.

## 31. What data types exit in JavaScript?

| Level | Easy |
| ----- | --- |

> Six data types that are primitives:
> - Boolean
> - Null
> - Undefined
> - Number
> - String
> - Symbol (new in ECMAScript 6)
>
> and Object

## 32. What are the most common module systems in JavaScript?

| Level | Easy |
| ----- | --- |

> - The CommonJS module system - `module.export` syntax
> - The ES6 module system - `import/export` syntax

## 33. Why is using `eval` bad?

| Level | Easy |
| ----- | --- |

> - Improper use of eval opens up your code for injection attacks
> - Debugging can be more challenging (no line numbers, etc.)
> - eval'd code executes slower (no opportunity to compile/cache eval'd code)

## 34. Can you explain the „scope chain“?

TODO:
