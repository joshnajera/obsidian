When declaring a variable either use the shorthand of ```:=```
Otherwise it is necessary to declare the type:
```go
// Syntax:
	var myVariable[, ...] variableType [ =value ]
	const myVariable[, ...] variableType [ =value ]

// Example Usage:
	var i int // 0  -- Gets set to zero value since undefined on declaration
	var var1, var2 string = 'value1', 'value2'
	var3 := 3
	var4,var5 := true, "nein!!!"
```


Base Data Types
```go
int
int32
float64
bool
string
rune

// Getting type
import "reflect"
reflect.TypeOf()
```

Default Values
```go
0
0.0
false
""
```

Note:
- If a vriable starts with a capital letter, it is considered exported and will be available from outside the package