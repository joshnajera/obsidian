Arrays have fixed sizes.

```go
// Array Syntax
var1 := [numElements]Type{elements...}
// Or
var var2 [numElements]Type
var2[element] = value
// Or
var3 := make([]Type, numStartingElements)


// Example Usage
var a [2]string
a[0] = "Hello"
a[1] = "World"
primes := [6]int{2, 3, 5, 7, 11, 13}

```
