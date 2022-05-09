# Features
- Strongly typed
- Favors composition , doesn't use classes
- No semi colons

# Syntax
```go
package main
import "fmt"

func main(){
	// Code
}
```
## Variables
When declaring a variable, if not defined, defaults to the zero value of that type
When declaring a variable either use the shorthand of ```:=```
Otherwise it is necessary to declare the type:
```go
// Syntax:
	var myVariable[, ...] variableType[ =value ]
	const myVariable[, ...] variableType [ =value ]

// Example Usage:
	var i int // 0  -- Gets set to zero value since undefined on declaration
	var var1, var2 string = 'value1', 'value2'
	var3 := 3
	var4,var5 := true, "nein!!!"

// Variable types:
	bool 
	string
	int  int8  int16  int32  int64
	uint uint8 uint16 uint32 uint64 uintptr
	byte // alias for uint8
	rune // alias for int32
	     // represents a Unicode code point
	float32 float64
	complex64 complex128 // imaginary numbers

// Retreiving type
	varName.(type)
// Example Usage
	switch v := i.(type) {
	case T:
	    // here v has type T
	case S:
	    // here v has type S
	default:
	    // no match; here v has the same type as i
	}
```
## Type Assertions
```go
///syntax
	t, ok := i.(Type)
	
// Example Usage
	t, ok := i.(int) // returns true or false
```
## Operators
Fairly standard
[[Operators]]
## Arrays
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

## Flow Control
### Defer
Waits till the function is returning before calling this function.
Each defer in a function gets pushed to a stack and popped off.
```go
defer functionName()
```
### Loops
```go
// For loop
	for i := 0; i < 10; i++{
		// Code
	}
// While
	for i < 10 {
		// Code
	}
// While true
	for {
		// Code
	}
// Range
	for index, value:= range collectionName {
		// Code
		// Note* index and value are omittable via '_' character
	}
```
### Conditionals
```go
// If condition
	if expression {
		// Code
	} else {
		// Code
	}
// If w short statement
	if var var1:= val; expression {
		// Code
	}

// Switch statement 
// Evaluated top->bottom
// Note how no break statement is needed at the end, unlike other languages
	switch expression {
		case val:
			// Code
		default:
			// Code
	} 
// Can be used without condition to acheive same as long if/else chain
	switch {
		case expression:
			// Code
		case expression:
			// Code ...
		default:
			// Code
	}
```
## [[Functions]]
Can be passed like values (first class functions?)
Optionally define receiver type, if you want class-like methods
Optionally define type parameter constraints prior to parameters in [] brackets such as 'comparable'
``` go
// Syntax	
	func (receiver Type) fnName(arg1 argType) returnType{
		return
	}
	func fnName[T someType](s []T, x T) returnType {
	}

// Example Usage
func (c Circle) area (float){
return (c.radius**2) * math.pi
}
func Index[T comparable](s []T, x T) int {
return 0
}
```
## Structs
```go
// Syntax
	type structName struct {
		propertyName Type
		propertyName2 Type
	}
// Example usage
	type Vertex struct {
		X int
		Y int
	}
	fmt.Println(Vertex{1, 2})
	fmt.Println(Vertex.X)
	v := Vertex{1, 2}
	v := Vertex{X:1} // Y:0 implcitly
	p := &v
	p.X = 1e9
	fmt.Println(v)
```

# Maps
```go
// Syntax
	var m map[indexType]valueType // zero value of nil
	m = make(map[indexType]valueType)
	// or
	var m := make(map[keyType]valueType)
	m[key] = value
	// or
	var m := map[keyType]valueType{key:value, ...}


	delete(m, "key")

```

## Interfaces
Define a set of functions. Anything that implements this set of functions can then be used in place of the interface in any function calls / expressions
```go
type interfaceName interface{
	//func() Type
	//func2() Type
}
// Example Usage
type Shape interface{
	area() float64
}
type square struct{
	width float64
}
func (s square) area(){
	return s.width * s.width
}
```
Reader Interface
represents the read end of a stream of data.
Expected to return io.EOF error when stream ends
```go
func (T) Read(b []byte) (n int, err error)
```

## Channels
Allow for passing of data between sources.
Optionally, have buffer size 
```go
// Syntax
	ch := make(chan channelType, optBufferSize) // create a channel of type int
	ch <- 42             // Send a value to the channel ch.
	v, ok := <-ch            // Receive a value from ch
	close(ch)
```
Can use range on a channel to continuously listen till close
```go
for i:= range ch
```

## Concurrency
Running in parallel is easy with just a keyword ```go```
[[Concurrency in Go]]
Thread management
```go
var wg sync.WaitGroup
wg.Add(1)
go func(){ defer wg.Done()}()
wg.Wait()
```
Select statements for channels
Act like a switch statement.
Normally are blocking until a case  can run, using default case swaps to non-blocking.
```go
// Usage Example
select {
		case c <- x: // listener listening? Can send message?
			x, y = y, x+y
		case <-quit: // receiver signal on quick channel?
			fmt.Println("quit")
			return
		}
```
Thread safety
Use mutex from sync library to put locks on variables to lock access
```go
import "sync"
type SafeCounter struct {
	mu sync.Mutex
	v  map[string]int
}

// Inc increments the counter for the given key.
func (c *SafeCounter) Inc(key string) {
	c.mu.Lock()
	defer c.mu.Unlock()
	// Lock so only one goroutine at a time can access the map c.v.
	c.v[key]++
}
```

## Error handling
```go
	if err != nil {
	    return
	}
```

## Modules & Imports
```go
import (
	"fmt"
)
```

# Useful Libraries
| Library   | Use                  | Useful functions            |
| --------- | -------------------- | --------------------------- |
| fmt       | Printing to console  | fmt.Println(), fmt.Printf() |
| time      | Time functions       | time.Now()                  |
| math/rand | Randomness           | rand.Intn()                 |
| math      | Math                 | math.Sqrt(), math.pi,       |
| sync      | Handling concurrency | sync.WaitGroup , sync.Mutex |
| io        | input/output         | io.Reader                   |
| image     | images               | image.NewRGBA               |

