# GoLang Interview Questions

## 1. What’s the difference between a goroutine and an operating system thread?

- Go provides built-in channels for goroutines to communicate safely between themselves.
- More goroutines can run on a typical system than system threads. For example, with Java, you can run many thousands of threads. With Go, you can run many millions of goroutines.
- Goroutines startup more quickly than operating system threads.
Multiple Goroutines are multiplexed onto OS threads, rather than a 1:1 mapping.
- You can write massively concurrent servers without having to resort to event programming.
- Goroutines are not hardware-dependent like threads.
- Goroutines are more lightweight, largely due to segmented stacks in memory

## 2. Can constants be computed in Go?

- Constants **can not** be computed at runtime, their value must be known at compile time. That said, constants can be computed at compile-time, typically as a derivative of other constants.

```golang
const hours = 7643

const minutes = hours * 60
```

## 3. What is the shortest way you can swap 2 variables?

```golang
var1, var2 = var2, var1
```

## 4. Do you have any preferences for error handling methodologies in Go?

Errors in Go are an interface type, where any type that implements the single `Error()` method can be considered an error.

Whenever a function has a possibility to go wrong, like a network call or a type conversion, the function should return an error as its last return variable. The caller should check the error value, and any value other than nil is considered an error.

Idiomatic Go developers should prefer guard clauses over if-else chains, especially when handling errors. Errors should also be wrapped in a meaningful way as they are passed up the call stack if appropriate.

## 5. What is a pointer and when would you use it?

A pointer holds the memory address of a value.
- `&` generates a pointer to its operand.
- `*` dereferences a pointer (exposes the underlying value).

Pointers can be used to:
- Allow a function to directly mutate a value that is passed to it
- To increase performance in edge cases. Sometimes passing a large struct of data results in inefficient copying of data
- To signify the lack of a value. For example, when unmarshalling JSON data into a struct it can be useful to know if a key was absent rather than it being present with the zero value.

## 6. Are channels and maps safe for concurrent access?

Channels are safe for concurrent access, for this reason they have blocking operations. Maps are unsafe for concurrent access and require a locking mechanism like a mutex to be safely used across goroutines.

## 7. How would you sort a slice of custom structs?

I would build a new type that represents a slice of that struct type. For example:

```golang
type fruitSlice[]fruit

type car struct {
   size int
   color string
}
```

Then I would fulfill the standard library’s `sort.Interface`:

```golang
type Interface interface {
   Len() int
   Less(i, j int) bool
   Swap(i, j int)
}
```

I would then be able to use the `sort.Sort` function:

```golang
sort.Sort(fruitSlice(cars))
```

## 8. Does Go support generic programming?

Ask about the persons view on generic programming.

## 9. Is `nil` only valid on pointer types?

Nope! `nil` is the zero value for pointers, interfaces, maps, slices, channels, and function types. `nil` represents an uninitialized value.

## 10. How do you export functions from a package?

Exported function in Go just need to be capitalized.

## 11. How do we perform inheritance with Golang?

This is a bit of a trick question: there is no inheritance in Golang because it does not support classes.

However, you can mimic inheritance behavior using composition to use an existing struct object to define a starting behavior of a new object. Once the new object is created, functionality can be extended beyond the original struct.

## 12. What kind of typing does GoLang use? Duck Typing/Structural Typing/Nominal Typing?

GO is a Structural-typed language. Nice article - [https://medium.com/higher-order-functions/duck-typing-vs-structural-typing-vs-nominal-typing-e0881860bf10](https://medium.com/higher-order-functions/duck-typing-vs-structural-typing-vs-nominal-typing-e0881860bf10)

## 13. Can you return multiple values from a function?

Yes. A Go function can return multiple values, each separated by commas in the return statement.

## 14. What are wrapped errors?

Wrapped errors in Go refer to the practice of adding additional context to an existing error before passing it up the call stack. This is particularly useful in error handling and debugging.

### Key Points

- **Error Wrapping:** In Go, you can wrap an error using the `%w` verb with `fmt.Errorf`. This allows you to add more context to the original error.
- **Retrieving the Original Error:** You can use the `errors.Unwrap` function to retrieve the original error from a wrapped error.
- **Error Checking:** Go provides the `errors.Is` and `errors.As` functions for checking the type or value of an error, including wrapped errors. `errors.Is` is used to check if any error in the error chain matches a specific error. `errors.As` is used to check if any error in the error chain matches a specific error type.
- **Use Case:** Wrapping errors is useful when you want to maintain the original error information but also provide additional context about what was happening when the error occurred.

### Example

```go
import (
    "errors"
    "fmt"
)

func someFunction() error {
    err := anotherFunction() // assume this returns an error
    if err != nil {
        // Wrapping the error with additional context
        return fmt.Errorf("failed to execute anotherFunction: %w", err)
    }
    return nil
}

// In the caller function
err := someFunction()
if err != nil {
    // Checking the specific error type or value
    if errors.Is(err, someSpecificError) {
        // handle specific error
    }
}
