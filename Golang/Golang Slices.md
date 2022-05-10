##  Slices
Slices are dynamically sized.
Slices act like pointers, if multiple slices point to the same element, they all are affected.
```go
// Slice Syntax
	var var1 []Type // Zero type of nil
	var var2 [][]Type // Nestable / multidimensional
	var var3 = []Type{elements...}
	var var4 = variableName[low:high] 
			   // Note*  low is inclusive; high is exclusive
			   //        Low and High bounds are omittable
// Slice Functions
	append(s []T, vs ...T) // returns the slice
	len(s []T) // Length
	cap(s []T) // Capacity (of underlying array)
// Example Usage
	var s []int = primes[1:4]
	fmt.Println(len(primes))
	board := [][]string{
			 []string{"_", "_", "_"},
			 []string{"_", "_", "_"},
			 []string{"_", "_", "_"},
			 }
	board[0][0] = "X"

```
### Type Casting
```go
// Syntax:
	var var1 Type = Type(valueToConvert)
	var2 := Type(valueToConvert)

// Example Usage:
	f := float64(123)
```
### Pointers
Simply a different way of declaring them
```go
// Syntax
	var var1 *Type
// Or to get it from the address of another variable
	var var2 = &someVariable
// Dereferencing
	*var1 = *var2 * 2
// Example Usage
	i:=42
	p:=&i
	fmt.Prinln(*p)
```