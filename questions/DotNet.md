# . NET Interview questions

## 2. What is difference between . NET Core and . NET Framework?

### `.NET Core`

* Free and open-source managed software framework for Windows, Linux and macOS systems.
* Cross-platform 
* Fully supports languages like `C#` , `F#` , `Visual Basic .NET` (from `.NET Core 5.0` in the future).
* Relies on `Package manager` to receive updates.

* Two main components:
    - `CoreCLR` - comparable to `CLR` (Common Language Runtime). `CoreCLR` is a complete runtime and virtual machine for managed execution of `.NET` programs and includes just-in-time compiler `RyuJIT` .
    - `CoreFX` - comparable to `FCL` (Framework Class Library) foundation for `Standard Libraries` . `CoreFX` shares a subset of `.NET Framework` API-s and comes with it's own API-s that are not part of the `.NET Framework` . 

* Supports:

     - `ASP.NET Core` web apps
     - command-line apps
     - libraries
     - UWP (Universal Windows Platform) apps
     - from `.NET 3.0` - WPF, Windows Forms

### `.NET Framework`

* Windows-only version of `.NET` for building any type of desktop app that runs on Windows.
* Includes a large class library called `FCL` (Framework Class Library).
* Provides language interoperability across several programming languages.
* Programs execute in software environment - `CLR` - application virtual machine. 
* Relies on `Windows Update` to receive updates.

* Two main components:

     - `CLR` (Common Language Runtime) - virtual machine that manages the execution of `.NET` programs and includes just-in-time compiler `RyuJIT` .
     - `FCL` (Framework Class Library) - provides user interface, data access, database connectivity, web application development, network communications. First implementation of `CLI` (Common Language Infrastructure).

## 3. What is CoreCLR?

* `.NET Core` command-line interface (CoreCLR) is a tool for developing, building, running and publishing `.NET Core` applications.
* Command structure is:

* the driver - `dotnet`
* command - example: `build` , `publish` , `new` , `run` , `test` , `add` , `remove` , etc.
* command arguments
* options

* We can install tools that are installed from `NuGet` packages and are run by the command prompt. 
* It is included in the `.NET Core SDK` .

## 4. What is JIT compiler?

* Just-in-time compiler is a part of `CLR` (Common Language Runtime) in `.NET` .
* Firstly a language-specific compiler converts the source code to the common intermediate language ( `CIL` ).
* Then the Just-in-time compiler converts that intermediate language to machine code.
* Speeds up code execution and performance.
* Provides support for multiple platforms.
* Machine code is specific to the computer environment that the JIT runs on.

## 5. What is the difference between AppDomain, Assembly, Process, and a Thread?

### AppDomain

* A class that represents an application domain - isolated environment where the application is executed.
* Derived from `MarshalByRefObject` .

### Assembly

* Fundamental unit of deployment, version control, reuse, activation, scoping and security permissions.
* Collection of types and addresses built to work together to form an executable (*.exe*) or a dynamic link library (*.dll*).
* Provide the `CLR` with the necessary information to build a `.NET` application.
* Assembly can be built from more that one source code files.
* Loaded into memory if they are required.
* We can obtain information about an assembly by using `Reflection` .

### Process

* A running application - from a small background task to big application.
* `Process` class provides access to local or remote processes.
* `Process` class can start, stop, control and monitor local system processes.
* Every process has at least one thread created by `CLR` .
* In `System.Diagnostics` namespace.
* A process can create more threads associated with that process.

### Thread

* Independent execution path, able to run simultaneously with other threads.
* Threads an be executed in the foreground or in the background (background thread does not keep a process running if all foreground threads have terminated).
* Worker threads that are managed by `CLR` can be executed by `ThreadPool` class.
* `Thread` class creates and controls a thread, sets its priority and gets it started.
* In `System.Threading.Thread` namespace.

## 6. What is an Object and a Class?

### Class

* Works as a blueprint for creating objects with specific properties.
* Data type that is a collection of data members and member functions. 
* Defines the kids of data and the functionality of its objects will have. 

### Object

* A class data type variable - an instance of the class.
* A block of memory that has been allocated and configured according to the class. 
* The objects/instances can be stored in a variable of a reference type or in a collection.

## 7. What are the fundamental OOP concepts? (The 4 pillars)

### Inheritance

* Ability to `receive` methods and properties from an existing class
* Ability to create a new class from a similar existing class.
* A process of object reusability.

### Polymorphism

* Each class implements the same methods, but they can change in different ways methods to specific characteristics.
* One function behaves in different ways in classes.
* Many forms of the single object.
* Static polymorphism (compile) - function overloading and operator overloading.
* Dynamic polymorphism (runtime) - function overriding.

### Abstraction

* Hides unnecessary details from type consumers - giving abstract design.
* Focus on what the object does rather that how it does it.

### Encapsulation

* Binds member function and data member into a single unit - class.
* Enclosing related operations and data into an object.
* Hiding the internal details for the object from the outside.

## 8. What is Managed and Unmanaged code?

### Managed code

* Resource, which is within the application domain.
* Code in `.NET framework` is managed and directly executed by `CLR` (no matter the language).
* Any managed code is not compiled into machine code, but to Intermediate language code, compiled and executed by runtime.
* `CLR` provides memory management, type safety, etc.
* Faster that unmanaged code.

### Unmanaged code

* Code outside of `.NET framework` and do not run under the control of `CLR` .
* Background compatibility with code of `VB` is an example of unmanaged code.
* From the language-specific native compiler the code is wrapped (COM Callable Wrapper or Runtime Callable Wrapper) to executable code.
* Languages like `C` / `C++` are unmanaged - they are loaded as binary to the memory by the operating system.

## 9. What is an Interface?

* An interface works as a contract between between its functionalities and the functionalities of the entities that implement the interface.
* An interface can contain declaration of methods, properties, indexers and events. Can not contain fields or implementations of methods. 
* Interface members are public by default, can not apply access modifiers. 
* A class or a struct can implement one or more interfaces. 
* From `C# 8.0` an interface can have a default implementation for members for classes / structs that don't provide an override method.
* From `C# 8.0` an interface may include also explicit access modifiers (public is default) and static fields. Instance fields are not permitted in interfaces. 

## 10. What are the different types of classes in C#?

### What is a class

* Data types that represent the state (properties) and behavior of an object (the actions it can perform).
* Can be declared by one of the five access modifiers: public, private, protected, internal, protected internal. The default is internal.
* Default access modifier of member methods is private. 

### Abstract classes

* Can have at least one abstract method. Can also have non-abstract methods.
* Can not create instances from an abstract class. 
* Its methods can either have an implementation or no implementation.
* Has only one subclass.
* Methods inside abstract class can not be private. 

### Partial classes

* It's properties, methods and events are divided into multiple source files. They are compiled into a single class at compile time.
* If a part of the class is sealed, the whole class becomes sealed.
* Can not be inherited. 
* All parts of the partial class must be prefixed with the partial keyword.

### Sealed classes

* Can not be inherited.
* Access modifiers can not be applied.
* To access the sealed members, an instance must be created. 

### Static classes

* Can have only static members.
* Can not make instances from a static class. 
* Can not be inherited.
* Only a static constructor can be declared. 
* Methods are called by using the class name, because an instance can not be created.

## 11. Explain code compilation in C#.

> I can not answer it.
> TODO

## 12. What are the differences between a Class and a Struct?

### Class

* Reference types of data, allocated on the heap and garbage-collected.
* Reference can be `null` .
* Two variables can contain a reference to the same object - one variable can be affected by another.
* Can inherit from another class.

### Struct

* Value types of data, allocated either on the stack or inline (in containing types).
* Can not have a `null` reference (unless `Nullable` is used).
* Can can not have implicit constructor without parameters - they have a default one because they need to have a value. They can not have a destructor.
* Each variable contains its own copy of the data - one variable is not affected by another.
* Can not inherit from another struct or class, can not be a base of a class. So they can not be abstract. Structs are `sealed` type.
* Members can not be `protected` or `protected internal` .
* Can be instantiated without using `new` .

### Both struct and class

* Can contain methods and events. 
* Can implement interfaces.

## 13. What is the difference between the Virtual method and the Abstract method?

* Virtual methods have a default implementation and provide the option of the derived classes to override them with custom implementation.
* Abstract methods are in abstract classes. They contain only the definition and don't have an implementation of the method. The derived classes have to override the definitions. 

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

* Exception occurs when a problem / error arises during the execution of the program.
* Exception handling provides a way to transfer control from one part of the program to another.
* In `C#` exception handling is represented by classes that mainly derived from `System.Exception` .
* By using `try` , `catch` , `finally` blocks the core program is separated from the error-handling statement.
* Structure:

* `try` - a block that checks the statement and activates it. It is followed by one or more `catch` blocks that handle it.
* `catch` - exception handler that catches the problem at the exact place in the program. This is the place where we decide what to do with the exception.
* `finally` - executes a set of statements no matter of an exception is caught or not.
* `throw` - the program creates a new exception then the problem occurs and throws it. We can trow an object if it is derived from the `System.Exception` class.

* We can have user-defined exceptions that derived from the `Exception` class.

## 17. What are C# I/O classes? What are the commonly used I/O classes?

* The `System.IO` namespace provides with methods that allow reading / writing to files and data streams, and some basic file and directory support.

### Most common I/O classes

* `Directory` - has static methods for creating and moving directories and subdirectories. The class can not be inherited.
* `File` - has static methods for creating, copying, deletion, moving and opening of a single file.
* `IOException` - the exception that is thrown then an I/O error occurs. 
* `Path` - performs operations on `String` instances that contain file or directory path information.
* `TextReader` - reader that reads a sequential series of characters.
* `TextWriter` - writer that can write a sequential series of characters. The class is abstract.
* `StreamReader` - implements `TextReader` that reads characters from a byte stream in a particular encoding.
* `StreamWriter` - implements `TextWriter` for writing characters to a byte stream in a particular encoding.
* `FileStream` - reading from, doing some operation (writing to) and closing the file.

## 18. What is a Destructor in C#?

* Destructor is a method inside a class that destroys the object when it is no longer in use. 
* Called when the program exits.
* Called implicitly by the Garbage Collector in `.NET Framework` .
* The destructor is unique for every class and a class can not have more than one destructor. 
* Destructors don't accept any parameters and access modifiers. 
* A destructor doesn't have a return type and just like a constructor, it has the same name as the class. The only difference between them is the "~" before the destructor's name.
* A destructor can not be inherited or overloaded.
* Destructors are used only in classes, not in `Struct` .

## 19. What are Boxing and Unboxing?

### Boxing

* The process of converting a value type to the `object` type.
* CLR boxes a value type by wrapping the value inside a `System.Object` instance and stores it in the heap.
* Boxing is implicit.

``` csharp
    int number = 7;
    object obj = i;
```

### Unboxing

* Extracting the value type from the object.
* Unboxing is explicit. 

``` csharp
    obj = 123;
    number = (int)obj;
```

## 20. What is the difference between Continue and Break Statement?

* `Break` is used to jump out of the loop (exit).
* `Continue` breaks one iteration of the loop and continues to execute with the next iteration.

## 21. What is the difference between finally and finalize block?

### Finally

* A block of code in the end of exception handling that is executed no matter if the exception is caught or not.

### Finalize

* Method for unmanaged resources (like database connection or file headers) that is used to free them.
* Used to perform cleanup operations held on unmanaged resources held by object before the object is reclaimed by the garbage collector. 
* The method is protected and is accessed only through the class or derived class. We can override it.
* `C#` destructor automatically implements the `Finalize` method. The garbage collector is non-deterministic, you do not know precisely when the garbage collector performs finalization.

## 22. What is an Array?

* Arrays are reference types that store multiple variables of the same data type.
* As with any other type - reference of value type, predefined or user-defined, it inherits from `Object` .
* Arrays are zero-indexed and elements can be accessed by index. 
* Array elements can be any type and by default are zero or `null` .
* In jagged arrays which are arrays of arrays, the elements are reference type and their default value is `null` . 
* Arrays derive from the abstract base type `Array` that implements `IEnumerable` and `IEnumerable<T>`
* Arrays can be accessed by `For` , `ForEach` , `While` loops.
* `System.Array` class includes method for creating, manipulating, searching and sorting arrays like `Sort` , `Clone` , `Copy` , `Equals` , `Empty` , `Find` , `FindIndex` , `Exists` , `GetValue` , `IndexOf` , etc.
* Arrays can be single-dimensional, multidimensional or jagged arrays:

``` csharp
     int[] singleArray = new int[5];
     int[,] multiArray = new int[2, 3];
     int[,] multiArray2 = new int { {1, 2, 3 }, {7, 8, 9}};
     int[] [] jaggedArray = new int [6][];
     jaggedArray[0] = new int[4]{1, 2, 3, 4, 5};
```

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

* A `string` is a object of type `String` that is a sequence of characters - text. 
* Strings are immutable - once created, they can not be assigned a new value. A new string variable must be made in order to hold that modification. In some cases it is better to use `StringBuilder` . 
* There is no null-terminating character at the end of the string.
* String has `Length` property - number of `Char` objects it contains, not the Unicode characters.  
* The `String` class provides methods for creating, manipulating and comparing strings like `String.Empty` , `String.Substring` , etc.
* Strings can use extension methods from the `Enumerable` class because it implements `IEnumerable<T>` .
* Default string comparison and equality: `String.CompareTo` , `String.Equals` (value), `String.Equality` (value).
* Reference string equality: `Object.ReferenceEquals` - if the two strings are the same objects.

## 25. What are Regular expressions?

* A pattern that is used to validate and parse an input text if it matches.
* Part of `.Net Framework` . 
* The Regex class is an immutable regular expression that is in the `System.Text.RegularExpression` namespace.  
* Defined by a special syntax.
* Common methods are: `Regex.IsMatch` , `Regex.Match` , `Regex.Replace` , etc.
* Example:

``` csharp
    string pattern = @"^[A-Z][a-zA-Z]*$";
    string firstName = "Victor";
    if(Regex.IsMatch(firstName, pattern){
        Console.WriteLine("It's a match!");
    }
 ```

## 26. What is Parsing? What is Casting?

### Parsing

* Conversion of string that represents a base type to that type.
* The reverse operation is formatting (converting a base type to its string representation).
* Most commonly strings are converted to numeric values ( `Parse` and `TryParse` ) and DateTime objects. We can also parse strings that represent `Char` , `Boolean` and `Enum` into data types.

### Casting

* Every data type has certain attributes such as the amount os memory space it takes, the range of possible values and the members that it makes available.
* Casting is a type conversion that can be automatically supported by . NET Framework or custom type conversion.

* Automatic type conversions:

    - from a derived class to a base class. Instance of any class or structure can be converted to an `Object` instance.
    - from a base class to the original derived class. Requires a casting operator.
    - from a type that implements an interface to an interface object that represents that interface. 
    - from an interface object back to the original type that implements that interface. Requires a casting operator.

* Custom type conversions:

    - `implicit` operator - widen conversions between types
    - `explicit` operator - narrow conversions between types
    - `IConvertible` interface, `Convert` class and `TypeConverter` class 

## 27. What is a Delegate?

* Reference type variable that holds the reference to a method.
* Used to pass methods as arguments to other methods (static or instance).
* Derived from `System.Delegate` class.
* When the delegate is instantiated, we can associate its instance with any method with the same parameter list and return type.
* Used for implementing events and call-back methods.
* Delegate objects can be composed with the `+` operator.

``` csharp
    public static void WriteToScreen(string str) {
        Console.WriteLine("The String is: {0}", str);
    }
    public delegate void printString(string s); // declaration
    printString firstString = new printString(WriteToScreen); // create delegate object
```

## 28. What are Events?

* User action or system generated notifications that the application needs to respond to.
* Using delegates events are declared and raised in a class and associated with event handlers.
* Events are the publisher-subscriber model in which:
    - Publisher class - containing the event. Publisher is the object containing the definition of the event and the delegate. Determines when the event is raised.
    - Subscriber class - accepts the event. Subscriber object is that accepts the event and provides an event handler. Determinate that action is taken in response to the event. One event can have many subscribers.

``` csharp
    // declare a delegate type for the event
    public delegate string BoilerLogHandler(string str);
 
    class EventProgram {
        // declare the event
        event MyDel MyEvent;
        
        public EventProgram() {
            this.MyEvent += new MyDel(this.WelcomeUser);
        }
        public string WelcomeUser(string username) {
            return "Welcome " + username;
        }
        static void Main(string[] args) {
            EventProgram obj1 = new EventProgram();
            string result = obj1.MyEvent("To Events");
            Console.WriteLine(result);
        }
    }
```

## 29. What is Reflection in C#?

* Allows an application to collect information about itself and also to manipulate on itself.
* Reflection describes assemblies, modules, types, members, parameters - to access metadata.
* `GetType` method returns the type of any variable.
* Reflection is used to build new types at runtime, late binding and access methods or types at runtime.
* If attributes are used, `Reflection` enables you to access them.
* In `System.Reflection` namespace.

## 30. What are generics? What is a Generic Class?

* Generics are classes, methods, structures, interfaces and methods that have placeholders (type parameters) that they store or use. 
* The type is specified when the generic class is instantiated.
* Generics are like templates - they provide generalization and reusability of classes and methods that don't have the specification of the data type until the class / method is declared.
* Frequently used with collections and methods on them.
* In `System.Collections.Generic` namespace are the most common generic-based collection methods.
* We can create custom generic types and methods.

``` csharp
    public class GenericList<T>
    {
    public void Add(T input) { }
    }
```

## 31. What are `async` and `await` ?

### Asynchronous programming

* Avoids activities that are potentially blocking and the application have to wait for them to finish.
* In an asynchronous process, the application can continue other work while that task finishes.
* Provides a way to improve responsiveness without bottlenecks.
* The `TAP` (Task Asynchronous programming model) provides more abstraction to asynchronous programming.
* Enables the code to start work and return a Task that represents the ongoing work.

### Async & await

* Asynchronous methods return a `Task<TResult>` or `Task` and are defined by the `async` modifier.
* Then in the body of the method, the process has been started (usually method ending in `Async` ).
* `Await` is an expression that marks a point where the method can't continue until the awaited asynchronous operation is finished.
* That means when you `await` some process, the program continues to execute if that process is not in use. When the process is finished, the control resumes and 

## 32. What is a `Deadlock` ?

* A situation in the multi-threading programming that two or more threads are frozen in their execution because they are waiting for each other to finish. 
* A *lock* is a shared object that can be Acquired by a Thread, and then Released. It is a way to synchronize between Threads. Usually a Lock is placed around a critical section when we want a single Thread at a time.
* Deadlock occurs when:
    - a limited number of a particular resource.
    - the ability to hold one resource and request another.
    - no preemption capability (using before the other thread). One thread can't force another thread to release a lock.
    - a circular wait condition.
* To avoid a Deadlock, the most common solutions are to use timeout value ( `System.Threading.Monitor` ), avoid unnecessary locks and avoid nested locks. 

## 33. What is a Race Condition?

* Two (on more) threads access and try to change a single shared between them data at the same time.
* Race condition is when the outcome of the program is affected because of timing.
* Resources that are accessed and updated within multiple threads are Shared resources.
* The problem is solved by using thread-synchronization techniques:
    - Atomic Update - `.NET`  `Interlocked` class to carry all the operations in one single operation.
    - Data Partitioning - partitioning data for multiple threads. This technique can not be used when one slice of data depends on the other slice. 
    - Wait-Based Technique - a thread is safe until someone decides it's safe to proceed.  Used when the previous two techniques can not be adopted easily. `.NET` has Wait Based Primitives - `Monitor` , `Mutex` , `ReaderWriterLock` classes for that technique.

## 34. What is Serialization?

* Process of converting an object into a stream of bytes to store it in memory, database or file.
* Saves the state of object in order to recreate it later.
* The reverse process is deserialization. 
* The object is serialized into a stream (with information about the object - version, culture, assembly name) and is stored in the database, file or memory.
* The serialized object can be:
    - sent to a remote application by using a web service
    - passed to another domain 
    - passed through a firewall as a `JSON` or `XML` string
    - maintaining security or user-specific information across applications

## 35. Can multiple catch blocks be executed?

* There can be multiple `catch` blocks with `try` statement but only the one that first matches the exception will be executed. 
* Once the `catch` block is executed, the controls skip the other catch blocks and is transferred to `finally` block.
* The order of the `catch` blocks is important: from more specific exception to more general.

## 36. What are the different access levels?

### Accessibility levels for members are defined by access modifiers

* `public` - access is not restricted.
* `private` - access is limited to the containing type.
* `protected` - access is limited to the containing class or types derived from the containing type.
* `internal` - access is limited to the current assembly.
* `protected internal` - access is limited to the current assembly or types derived from the containing type.
* `private protected` - access is limited to the containing class or type derived from the containing class within the current assembly.

### Default accessibility

* class - members: `private` , allowed accessibility of members: all
* enum - members: `public` , allowed accessibility of members: none
* interface - members: `public` , allowed accessibility of members: none
* struct - members: `private` , allowed accessibility of members: `public` , `internal` , `private`
* Access modifiers are not allowed for namespaces.

## 37. What is the difference between static methods and instance methods?

### Static methods

* Declared with `static` keyword.
* Can be in static and non-static classes.
* Can be called on static classes, or if the class is an instance class - on the class itself (not the instance).

### Instance methods

* Require an object of its class to be created before it can be called.
* Has a class instance passed to it like an invisible: accessed by `this` .
* Can apply the method only to instantiated objects, not the class itself.

## 38. What is a constructor?

* A method that is called automatically when a new instance of the class / struct is created.
* It has the same name as the class / struct and is useful to set default values for the data members of the new object. 
* If we don't have a constructor, the compiler will automatically create one default without parameters. 
* Constructors don't return anything, not even a `void` .
* Constructors don't have access modifiers.
* We can have constructor overloading - many constructors with different parameters in one class.
* We can declare `static` constructor without parameters or access modifier that will be invoked automatically when we create the first instance of the class. In other words, it will be invoked only once no matter how many class instances we create.

## 39. What is the difference between ref & out parameters?

### Ref

* `Ref` is a keyword in `C#` . 
* Used for passing the arguments by reference.
* The parameters should be initialized before passed to ref.
* The data may go both directions.
* Useful when the calling method also need to change the value of passed parameter.

### Out

* `Out` is a keyword in `C#` . 
* Used for passing the arguments to methods as a reference type.
* Used when a method returns multiple values.
* The value of the parameter have to be initialized before returning to the calling method.
* The data only goes one direction.
* Useful when a method return multiple values.

## 40. Can we use `this` command within a static method?

* Static classes can not be instantiated. To call the static methods, we use the class name because we don't have an instance. 
* Static class can contain only static members. 
* Static classes can inherit only from `Object` .
* `This` points to an instance of the current class. In a static method there is no inheritance. Hence, we can not use `this` in a static method. 

## 41. What is the difference between constants and read-only?

### Constant

* The value of the constant field stays the same throughout the program after once assigned. 
* Constant fields and locals are not variables, they are a number, string, null reference or boolean values. 
* The value can not be changed.	
* We can only assign values in declaration part.
* Compile time constant.
* Can be declared inside a method (local).
* Can not be used with static modifiers.

### Read-only

* Declares a readonly variable that you can assign it only when you declare it or in a constructor of the same class.
* The value can be changed.	
* We can assign values in declaration and in the constructor part.
* Runtime constant.
* Can not be declared inside a method.
* Can be used with static modifiers.

## 42. What are value types and reference types?

### Value types

* Holds a data value within its own memory space - directly contains value.
* Passing to other method: separate copy is created. So changing the one copy doesn't affect the other copy.
* Value data types in `C#` : `bool` , `byte` , `char` , `decimal` , `double,`  `enum,`  `float` , `int` , `long` , `sbyte` , `short` , `struct` , `uint` , `ulong,`  `ushort` .

### Reference types

* Doesn't store the value directly, only the address it is being stored. 
* The reference is the pointer to where the memory for the variable is being stored.
* Passing to other method: passes the variable's address, not its copy. So if we change the value of one variable, it will also reflect in the calling method.
* Reference data types in `C#` are: `string` , `array` , `class` , `delegate` .
* Default value is `null` .

## 43. What is method overloading?

* A way to redefine a method in more that one form.
* A way to implement polymorphism that allows objects or methods to act in a different way depending on the context they are used.
* Methods have different signatures - can have the same name but with a different list of parameters (their type, number, order).
* If we define two methods with the same signature - their name, number, type and order of parameters, a compiler error occurs. 
* The only the return type is different, but the signature of two methods is the same, a throw a compile-time error is thrown. 

## 44. Can a private virtual method can be overridden?

* Virtual methods contain a default implementation and can be overridden by the derived class. 
* Private methods can only be accessed by the class defining them, but not the derived class. To have a method that the derived class can access, it should be `protected` in the base class.
* Virtual methods that can be overridden by the derived class are useless if defined `private` in the base class. The reason is they can not be accessed by the derived class. The solution is the virtual methods to have `protected` access modifier.

## 45. How do you inherit a class into other class in C#? Can you inherit multiple classes? What about interfaces?

* We can inherit from a class with the `:` symbol.
* `C#` supports single inheritance only.
* All types in the `.NET` type system inherit from `Object` .
* If we don't want other classes to inherit from a class, we use `sealed` .
* Not inherited from a class are:

    - static constructors
    - instance constructors
    - finalizers - called by the runtime's garbage collector to destroy an instance

* Interfaces solve the problem with the single class inheritance. Interfaces work as a contract between the instances that implement them and the declared functionalities. One class can implement many interfaces.

## 46. What is the base class in . NET from which all the classes are derived from?

* At the top of the class hierarchy is the `Object` class in the `System` namespace.   
* Inheritance from `Object` is implicit. 
* Every method defined in `Object` is inherited by all objects - `Equals` , `ToString` , `Finalize` , `GetHashCode` .

## 47. Why can't you specify the accessibility modifier for methods inside the interface?

* We can not apply access modifiers to interface members and methods - they are public by default. 

## 48. How can we set the class to be inherited, but prevent the method from being over-ridden?

* If we want a method from the base class to be able to be overridden, we use `virtual` to declare it.
* If a method is not virtual, then it can't be overridden in the derived class. So we just declare the method in the base class without `virtual` .
* We can use `sealed override` in the derived class and prevent the method from further overriding in the following derived class.

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

### `Is` operator

* Used to check if the run-type of an object is compatible with a given type.
* Boolean type and returns `true` if the object is the same and `false` if not.
* Only for reference, boxing and unboxing conversions. 

### `As` operator

* Used to perform conversion between compatible reference types or Nullable types.
* Returns the object if it is compatible with the given type or `null` if not.
* Only for reference and boxing conversions. 

## 51. What are indexers?

* Allow instances of a class to be indexed line an array.
* `This` keyword is used to define the indexer.
* Can have more that one formal parameter, example: accessing a two-dimensional array.
* Can be overloaded.

``` csharp
    class SampleCollection<T>
    {
    // Declare an array to store the data elements.
        private T[] arr = new T[100];

        // Define the indexer to allow client code to use [] notation.
        public T this[int i]
        {
            get { return arr[i]; }
            set { arr[i] = value; }
        }
    }

    class Program
    {
        static void Main()
        {
            var stringCollection = new SampleCollection<string>();
            stringCollection[0] = "Hello, World";
            Console.WriteLine(stringCollection[0]);
        }
    }
```

## 52. What is difference between the `throw` and `throw ex` ?

### Throw

* Used to preserve the original error stack information.
* Good practice to use it instead of `throw ex` .

### Throw ex

* Used to replace stack trace of exception with a stack trace starting at the re-throw point.
* Used to intentionally hide stack trace information.

## 53. What are C# attributes and its significance?

* Adds information and metadata about some entity in code. 
* Part of `.Net Framework` .
* We can apply one or more attributes to assemblies, modules, classes and properties. 
* Attributes can accept arguments just like methods.
* Attributes are used surrounded by square brackets ([]) above the entity they describe. 
* We can define custom attributes.
* Reflection can be used to obtain metadata about the program by accessing the attributes at run-time.
* Examples: `Description` , `DefaultValue` , `Serializable` , `DllImport` (exposed by an unmanaged dynamic-link library (DLL) as a static entry point), `Conditional` (method call should be ignored unless a specified conditional compilation symbol is defined), `AssemblyVersion` , `Obsolete` (raise a warning about code that should no longer be used), etc.

## 54. How to implement a singleton design pattern in C#? And what about a thread safe singleton?

### Singleton pattern

* A singleton is a class that allows only once instance of itself to be created.
* Usually singletons don't allow any parameters to be specified when creating the instance.
* They are created with a single constructor, which is private and parameterless.
* This way the creation of subclasses is prevented.
* Typically the instance is not created until needed.
* The class is sealed (not necessary, but may help the JIT).
* A static variable which holds a reference to the single created instance, if any.
* A public static means of getting the reference to the single created instance, creating one if necessary.

### Non-thread safe (bad example)

``` csharp
public sealed class Singleton
    {
    private static Singleton instance=null;

    private Singleton()
    {
    }

    public static Singleton Instance
    {
        get
        {
            if (instance==null)
            {
                instance = new Singleton();
            }
        return instance;
        }
    }
}
```

### Simple thread safety

``` csharp
public sealed class Singleton
{
    private static Singleton instance = null;
    private static readonly object padlock = new object();

    Singleton()
    {
    }

    public static Singleton Instance
    {
        get
        {
            lock (padlock)
            {
                if (instance == null)
                {
                    instance = new Singleton();
                }
                return instance;
            }
        }
    }
}
```

### Thread safety - lazy

``` csharp
public sealed class Singleton
{
    private Singleton()
    {
    }

    public static Singleton Instance { get { return Nested.instance; } }

    private class Nested
    {
    // Explicit static constructor to tell C# compiler
    // not to mark type as beforefieldinit
        static Nested()
        {
        }

        internal static readonly Singleton instance = new Singleton();
    }
}
```

## 55. Explain `Finalize` vs `Dispose` usage?

### Finalize

* Called by the garbage collector when it reclaims an object.
* Should release unmanaged resources only.
* Execution is "non-deterministic" - we can not rely on another object still being available in Finalizers.
* Not for value types.
* Finalizers should be `protected` methods.

### Dispose

* Called by the application to release valuable native resources when they are no longer needed.
* Execution is "deterministic" - after making a call to the `Disposable` method, the object is made unusable.
* We should avoid creating disposable value types.
