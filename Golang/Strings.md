
# Strings
## Functions
```go
// Replacing parts of a string
import "strings"
v1 := "A word"
replacer := strings.NewReplacer("A", "Another")
v2 := replacer.Replace(v1)
// OR
strings.Replace(variable1, searchStr, replacementStr, -1) // last number is number of matches to replace, -1 for all.

// Length
len(someVariable)

// Index of 
strings.Index(searchString, subString)

// Checks if string contains another string
strings.Contains(v2, "Another")

// Time white space
someString := "\nSome string!\n"
someString = strings.TrimSpace(someString)

// Splitting on delimeter
someString = strings.Split("A B C D", " ")

// to lower to upper
strings.ToUpper()
strings.ToLower()

// If starts with / ends with a string
strings.HasPrefix("Mr. Anderson", "Mr")
strings.HasSuffix("Mr. Anderson", "Anderson")



// ----- FORMATTED PRINT -----

// Go has its own version of C's printf

// %d : Integer

// %c : Character

// %f : Float

// %t : Boolean

// %s : String

// %o : Base 8

// %x : Base 16

// %v : Guesses based on data type

// %T : Type of supplied value

fmt.Printf("%s %d %c %f %t %o %x\n", "Stuff", 1, 'A', 3.14, true, 1, 1)
```

## Casting
[[Strings#Casting]]