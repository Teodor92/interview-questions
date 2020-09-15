# . NET Interview questions

## 1. What is the . NET Core?

> I can partially answer it.
> TODO

## 2. What is difference between . NET Core and . NET Framework?

> I can partially answer it.
> TODO

## 3. What is CoreCLR?

> I can partially answer it.
> TODO

## 4. What is JIT compiler?

> I can not answer it.
> TODO

## 5. What is the difference between AppDomain, Assembly, Process, and a Thread?

> I can not answer it.
> TODO

## 6. What is an Object and a Class?

###### Class

* Works as a blueprint for creating objects with specific properties.
* Data type that is a collection of data members and member functions. 
* Defines the kids of data and the functionality of its objects will have. 

###### Object

* A class data type variable - an instance of the class.
* A block of memory that has been allocated and configured according to the class. 
* The objects/instances can be stored in a variable of a reference type or in a collection.

## 7. What are the fundamental OOP concepts? (The 4 pillars)

> I can answer it.
> TODO

## 8. What is Managed and Unmanaged code?

> I can not answer it.
> TODO

## 9. What is an Interface?

* An interface works as a contract 
* Contains a declaration of functionalities. The entities that implement the interface must provide the implementation of that declarations. 
* An interface can contain declaration of methods, properties, indexers and events. Can not contain fields or implementations of methods. 
* Interface members are public by default, can not apply access modifiers. 
* A class or a struct can implement one or more interfaces. 
* From `C# 8.0` an interface can have a default implementation for members for classes / structs that don't provide an override method.
* From `C# 8.0` an interface may include also explicit access modifiers (public is default) and static fields. Instance fields are not permitted in interfaces. 

## 10. What are the different types of classes in C#?

###### What is a class

* Data types that represent the state (properties) and behavior of an object (the actions it can perform).
* Can be declared by one of the five access modifiers: public, private, protected, internal, protected internal. The default is internal.
* Default access modifier of member methods is private. 

###### Abstract classes

* Can have at least one abstract method. Can also have non-abstract methods.
* Can not create instances from an abstract class. 
* Its methods can either have an implementation or no implementation.
* Has only one subclass.
* Methods inside abstract class can not fe private. 

###### Partial classes

* It's properties, methods and events are divided into multiple source files. They are compiled into a single class at compile time.
* If a part of the class is sealed, the whole class becomes sealed.
* Can not be inherited. 
* All parts of the partial class must be prefixed with the partial keyword.

###### Sealed classes

* Can not be inherited.
* Access modifiers can not be applied.
* To access the sealed members, an instance must be created. 

###### Static classes

* Can have only static members.
* Can not make instances from a static class. 
* Can not be inherited.
* Only a static constructor can be declared. 
* Methods are called by using the class name, because an instance can not be created.

## 11. Explain code compilation in C#.

> I can not answer it.
> TODO

## 12. What are the differences between a Class and a Struct?

###### Class

* Reference types of data, allocated on the heap and garbage-collected.
* Reference can be `null` .
* Two variables can contain a reference to the same object - one variable can be affected by another.
* Can inherit from another class.

###### Struct

* Value types of data, allocated either on the stack or inline (in containing types).
* Can not have a `null` reference (unless `Nullable` is used).
* Can can not have implicit constructor without parameters - they have a default one because they need to have a value. They can not have a destructor.
* Each variable contains its own copy of the data - one variable is not affected by another.
* Can not inherit from another struct or class, can not be a base of a class. So they can not be abstract. Structs are `sealed` type.
* Members can not be `protected` or `protected internal` .
* Can be instantiated without using `new` .

###### Both struct and class

* Can contain methods and events. 
* Can implement interfaces.

## 13. What is the difference between the Virtual method and the Abstract method?

> I can answer it.
> TODO

## 14. What is a Namespaces in C#?

* Help organize many files and resources.
* Declaring own namespaces controls the scope of class and method names in large code projects.
* The name of the namespace is specified by the `using` directive.
* The unnamed namespace -  global namespace is the "root" namespace. `global::System` will always refer to the . NET System namespace.
* Namespaces have implicitly have public access and this is not modifiable. 
* Namespace alias qualifier `::` - to access a member of an aliased namespace.

## 15. What is `using` statement in C#?

* Defines a scope at the end oof which the object will be disposed. 
* Ensures the correct use of `IDisposable` objects which provides a mechanism for releasing unmanaged resources.
* From `C# 8.0` ensures the correct use of `IAsyncDisposable` objects which provides a mechanism for releasing unmanaged resources asynchronously.

## 16. How is Exception Handling implemented in C#?

> I can not answer it.
> TODO

## 17. What are C# I/O classes? What are the commonly used I/O classes?

> I can not answer it.
> TODO

## 18. What is a Destructor in C#?

> I can not answer it.
> TODO

## 19. What are Boxing and Unboxing?

> I can not answer it.
> TODO

## 20. What is the difference between Continue and Break Statement?

* `Break` is used to jump out of the loop (exit).
* `Continue` breaks one iteration of the loop and continues to execute with the next iteration.

## 21. What is the difference between finally and finalize block?

> I can not answer it.
> TODO

## 22. What is an Array?

> I can answer it.
> TODO

## 23. What is a Jagged Array?

* Array which elements are arrays.
* The elements of a jagged array can be of different dimensions and sizes.
* Example of a single-dimensional array with three elements, each of which is a single-dimensional array:

``` csharp
    int[] [] jaggedArray = new int [3] [];
    jaggedArray[0] = new int[5];
    jaggedArray[1] = new int[4];
    jaggedArray[2] = new int[2];
```

## 24. What is a String?

> I can answer it.
> TODO

## 25. What are Regular expressions?

> I can partially answer it.
> TODO

## 26. What is Parsing?

> I can answer it.
> TODO

## 27. What is a Delegate?

> I can not answer it.
> TODO

## 28. What are Events?

> I can not answer it.
> TODO

## 29. What is Reflection in C#?

> I can not answer it.
> TODO

## 30. What are generics? What is a Generic Class?

> I can partially answer it.
> TODO

## 31. What are `async` and `await` ?

> I can partially answer it.
> TODO

## 32. What is a `Deadlock` ?

> I can partially answer it.
> TODO

## 33. What is a Race Condition?

> I can not answer it.
> TODO

## 34. What is Serialization?

> I can partially answer it.
> TODO

## 35. Can multiple catch blocks be executed?

> I can not answer it.
> TODO

## 36. What are the different access levels?

> I can answer it.
> TODO

## 37. What is the difference between static methods and instance methods?

> I can answer it.
> TODO

## 38. What is a constructor?

> I can answer it.
> TODO

## 39. What is the difference between ref & out parameters?

> I can partially answer it.
> TODO

## 40. Can we use `this` command within a static method?

* Static classes can not be instantiated. To call the static methods, we use the class name because we don't have an instance. 
* Static class can contain only static members. 
* Static classes can inherit only from `Object` .
* `This` points to an instance of the current class. In a static method there is no inheritance. Hence, we can not use `this` in a static method. 

## 41. What is the difference between constants and read-only?

> I can answer it.
> TODO

## 42. What are value types and reference types?

> I can answer it.
> TODO

## 43. What is method overloading?

> I can answer it.
> TODO

## 44. Can a private virtual method can be overridden?

> I can answer it.
> TODO

## 45. How do you inherit a class into other class in C#? Can you inherit multiple classes? What about interfaces?

> I can answer it.
> TODO

## 46. What is the base class in . NET from which all the classes are derived from?

* At the top of the class hierarchy is the `Object` class in the `System` namespace.   
* Inheritance from `Object` is implicit. 
* Every method defined in `Object` is inherited by all objects - `Equals` , `ToString` , `Finalize` , `GetHashCode` .

## 47. Why can't you specify the accessibility modifier for methods inside the interface?

* We can not apply access modifiers to interface members and methods - they are public by default. 

## 48. How can we set the class to be inherited, but prevent the method from being over-ridden?

> I can not answer it.
> TODO

## 49. How to use nullable types in . NET?

* Nullable types are all the values for the value type T and an additional `null` value. 
* Used when we need to represent missing or undefined value.
* Example:    


``` csharp
     double? pi = null; 
```

* We can check if the variable has the value of its underlying type with `Nullable<T>.HasValue` .
* `Nullable<T>.Value` gets the value of the underlying type if the `HasValue` is `true` .

## 50. What is difference between "is" and "as" operators in c#?

> I can not answer it.
> TODO

## 51. What are indexers?

> I can not answer it.
> TODO

## 52. What is difference between the `throw` and `throw ex` ?

> I can not answer it.
> TODO

## 53. What are C# attributes and its significance?

> I can partially answer it.
> TODO

## 54. How to implement a singleton design pattern in C#? And what about a thread safe singleton?

> I can not answer it.
> TODO

## 55. Explain `Finalize` vs `Dispose` usage?

> I can not answer it.
> TODO
