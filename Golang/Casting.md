
# Casting
## Floats and Integers
```go
// Syntax:
	var var1 Type = Type(valueToConvert)
	var2 := Type(valueToConvert)

// Example Usage:
	f := float64(123)
	i := int64(f)
```

Note, casting to string results in the ascii code representation

## Casting Strings
```go
import "strconv"
variable2, err = strconv.Atoi(variable1) // Ascii to int
variable2, err = strconv.Itoa(variable1) // Int to ascii
variable2, err = strconv.ParseFloat(variable1) // Ascii to float

import "fmt"
variable2, err = fmt.Sprintf("%f", variable1) // Float to ascii
```
