# TypeScript interview questions

## 1. Which are the different data types supported by TypeScript? What do they represent?

`boolean`, `number`, `string`, `object`, `Array`, `enum`, `any`, `void`, `never`, `unknown`

## 2. What are classes in TypeScript?

They are basically ES6 classes with additional features like access modifiers, indexers etc.

## 3. Does TypeScript support abstract classes? And what about interfaces? What is the difference?

Yes to both. The interface cannot have any implementation of it's methods in contrast to the abstract class. Additionally the abstract class can have fields.

## 4. What types of access modifiers exit in a TypeScript class? What does each do?

`private`, `public` and `protected`

## 5. How do you implement inheritance in TypeScript?

Same as ES6 inheritance.

## 6. How do you implement and interface for a specific class?

Using the `implements` keyword.

## 8. How do you call a base class constructor or a base class method form a child class?

Using the `super` keyword.

## 9. How can you expose a class/method/variable to the outside world?

Using the `exports` keyword. Same as ES6.

## 10. Does TypeScript support function overloading as JavaScript doesn’t support function overloading?

Not in a native way, but you can have a single implementation with multiple signatures.

## 11. What is an union, discriminated unions and intersection types?

A mix of multiple types using the `|` or `&` operators.
- Using the `&` creates a new type type holds **all the common properties** between type A and type B.
- Using the `|` creates a new type that holds **all the properties** for both type A and type B.

## 12. What is type inference?

Ability to infer the type from the existing code. There are 2 strategies:
- Best common type.
- Contextual typing.

For more information: [Type Inference](https://www.typescriptlang.org/docs/handbook/type-inference.html)

## 13. What are mapped types?

Mapped Types in TypeScript are a powerful feature that enables the creation of new types based on existing ones. They allow you to iterate over the keys of an existing type and transform them to construct a new type. This feature is highly useful for creating types that are variations of existing ones, such as making all properties of a type optional or readonly.

### Key Features

- **Dynamic Type Transformation:** Mapped Types can dynamically create new types based on existing types or interfaces, providing flexibility in type manipulation.
- **Useful for Bulk Property Modifications:** They are particularly handy when you need to modify multiple properties of a type in the same way, such as making them all optional or readonly.
- **Enhances Code Reusability:** Reduces redundancy by allowing you to create variations of types without duplicating code.

### Example Use Case

Suppose you have an interface representing a `User`, and you want to create a new type where all the properties of `User` are optional. Mapped Types make this task straightforward:

```typescript
interface User {
    id: number;
    name: string;
    email: string;
}

// Creating a Mapped Type where all properties of User are optional
type PartialUser = {
    [Property in keyof User]?: User[Property];
};

// PartialUser now has all properties of User, but they are optional
```

## 14. What are Template Literal Types?

Template Literal Types in TypeScript are a sophisticated feature introduced in TypeScript 4.1. They allow us to define types using template literal strings, offering more flexibility and control over string types. This feature is especially useful when working with string patterns that follow a specific format.

### Key Features

- **String Manipulation:** Template Literal Types enable complex string manipulation at the type level. They can be used to concatenate literal types, embed expressions, and more.
- **Pattern Matching:** These types excel in defining patterns that strings must adhere to. For example, you can define a type for email addresses, URLs, or custom formats.
- **Type Inference:** TypeScript can infer types based on template literals, which is beneficial for maintaining type safety in string operations.
- **Conditional Types:** They can be combined with conditional types to create more dynamic and responsive type behaviors.

### Example Use Case

Imagine you need to define a type for a string that must start with 'http://' or 'https://'. With Template Literal Types, you can do this easily:

```typescript
type URL = `http://${string}` | `https://${string}`;
```

## 15. What are Index Accessed Types?

Index Accessed Types, also known as Lookup Types, are a feature in TypeScript that allow for accessing the type of a property in an object or an interface. This feature is particularly useful for maintaining type safety in dynamic code structures.

### Key Features

- **Dynamic Type Access:** Index Accessed Types enable us to access types dynamically based on the properties of an object or interface.
- **Enhanced Type Safety:** They help in ensuring type safety by allowing us to extract and reuse the type of a specific property, thereby reducing redundancy and potential errors.
- **Versatility:** These types are versatile and can be used with arrays, tuples, and other types, making them a crucial tool for generic programming.

### Example Use Case

Suppose you have an interface representing a user and you want to extract the type of a specific property, say 'name', from this interface. With Index Accessed Types, you can do this effortlessly:

```typescript
interface User {
    id: number;
    name: string;
    email: string;
}

type UserNameType = User['name']; // UserNameType is now of type string
```

## 16. What are Conditional Types?

Conditional Types in TypeScript allow us to define types that can change based on certain conditions. This feature adds a level of logic to type definitions, enabling more dynamic and adaptable type behaviors. It's akin to using 'if' statements at the type level.

### Key Features

- **Type Flexibility:** Conditional Types provide the ability to create types that change based on certain conditions, offering more flexibility in how types are defined and used.
- **Improved Type Inference:** They enable TypeScript to infer types in more complex scenarios, particularly in generic programming.
- **Combination with Other Types:** Conditional Types can be combined with other TypeScript features like generics, mapped types, and tuple types to create more sophisticated type solutions.

### Example Use Case

Imagine you have a generic function that should return different types based on the input. Conditional Types can be used to define this behavior precisely:

```typescript
type Numeric = number;
type Textual = string;

// Define a Conditional Type
type ResponseType<T> = T extends number ? Numeric : Textual;

// Usage in a function
function processInput<T>(input: T): ResponseType<T> {
    if (typeof input === 'number') {
        return (input * 2) as ResponseType<T>; // Returns a Numeric type
    }
    return `Processed: ${input}` as ResponseType<T>; // Returns a Textual type
}
```

## 17. What are Recursive types?

Recursive Types in TypeScript allow for the definition of types that can refer to themselves, directly or indirectly. This is particularly useful for modeling data structures that are naturally recursive, like trees, linked lists, or any hierarchical data.

### Key Features

- **Self-referencing:** Recursive Types are capable of referencing themselves within their definition, enabling the creation of complex and nested data structures.
- **Modeling Hierarchical Data:** They are ideal for accurately modeling hierarchical or recursive data structures in a type-safe manner.
- **Enhanced Readability and Maintainability:** Recursive Types help in making code that deals with complex data structures more readable and maintainable.

### Example Use Case

Consider a scenario where you need to represent a file system with folders and files, where each folder can contain more folders and files. This is a perfect use case for Recursive Types:

```typescript
// Define a Recursive Type for a file system structure
type FileSystemItem = {
    name: string;
    type: 'file' | 'folder';
    children?: FileSystemItem[]; // Recursive reference
};

// Example usage
const fileSystem: FileSystemItem = {
    name: 'root',
    type: 'folder',
    children: [
        {
            name: 'Documents',
            type: 'folder',
            children: [
                {
                    name: 'resume.docx',
                    type: 'file'
                }
            ]
        },
        {
            name: 'photo.jpg',
            type: 'file'
        }
    ]
};
```

## 18. What are Conditional Recursive Types?

Conditional Recursive Types in TypeScript are an advanced feature that blends the flexibility of conditional types with the self-referencing nature of recursive types. This combination allows for defining types whose structure can change based on certain conditions and can reference themselves recursively.

### Key Features

- **Dynamic Recursive Structures:** They enable the creation of complex data structures whose shape can change based on certain conditions, and can be recursively defined.
- **Powerful Type Modelling:** Ideal for modeling intricate data patterns and scenarios where the type's structure depends on certain conditions and may involve self-referencing.
- **Enhanced Type Safety and Flexibility:** These types provide a high degree of type safety and flexibility, especially in scenarios involving complex, nested, or hierarchical data.

### Example Use Case

Imagine a scenario where you need to model a navigation menu. This menu has items that can either be simple links or dropdowns containing more items. Conditional Recursive Types can elegantly represent this:

```typescript
// Define a Conditional Recursive Type for a navigation menu
type MenuItem = {
    label: string;
    type: 'link' | 'dropdown';
    href?: string;
    items?: MenuItem[]; // Recursive reference
} extends infer T ? (T extends { type: 'link' } ? Omit<T, 'items'> : T) : never;

// Example usage
const menu: MenuItem[] = [
    { label: 'Home', type: 'link', href: '/home' },
    {
        label: 'About',
        type: 'dropdown',
        items: [
            { label: 'Team', type: 'link', href: '/team' },
            { label: 'History', type: 'link', href: '/history' }
        ]
    }
];
```

## 19. What is Type Narrowing?

Type Narrowing in TypeScript is a key concept where the compiler refines the type of a variable within a certain scope based on type checks or guards. This process reduces the possible types a value can be, making it easier to work with and more predictable in terms of its behavior and attributes.

### Key Features

- **Improves Type Safety:** Type Narrowing enhances type safety by ensuring that operations on variables are valid for their actual type.
- **Handles Union Types:** It is particularly useful when dealing with union types, where a variable can be one of several types.
- **Reduces Errors:** By narrowing types, TypeScript can catch potential runtime errors during compile time.

### Example Use Case

Consider a function that takes an input of a union type (`string | number`) and you want to perform different operations based on the actual type of the input:

```typescript
function processInput(input: string | number) {
    if (typeof input === 'string') {
        console.log('Input is a string:', input.toUpperCase());
    } else {
        console.log('Input is a number:', input.toFixed(2));
    }
}
```

## 20. What is the `in` operator?

The `in` operator in TypeScript is used for type narrowing and to check if a property exists on an object. This operator is particularly useful when you're dealing with types that might have different sets of keys, such as in union types. It helps in ensuring that the code behaves correctly by verifying the existence of properties before accessing them.

### Key Features

- **Type Safety:** The `in` operator enhances type safety by checking for the existence of a property on an object before performing operations on it.
- **Type Narrowing:** It is used to narrow down from a broader type to a more specific type based on the presence of certain keys.
- **Handles Union Types with Different Shapes:** Ideal for union types where objects might have different properties.

### Example Use Case

Imagine you have a union type representing either a `Circle` or a `Square`, and you need to write a function that behaves differently based on the shape provided:

```typescript
type Circle = {
    radius: number;
};

type Square = {
    sideLength: number;
};

type Shape = Circle | Square;

function getArea(shape: Shape): number {
    if ('radius' in shape) {
        // Type of shape is narrowed to Circle
        return Math.PI * shape.radius ** 2;
    } else {
        // Type of shape is narrowed to Square
        return shape.sideLength ** 2;
    }
}
```
