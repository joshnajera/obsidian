```go
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

```

In [[Golang Conditionals#Switch Statement|Switch Statements]]
```go
///syntax
	t, ok := i.(Type)
	
// Example Usage
	t, ok := i.(int) // returns true or false


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