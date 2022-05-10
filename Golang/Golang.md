# Features
- Strongly typed
- Favors composition , doesn't use classes
- No semi colons

# Syntax
```go
package main
import "fmt"
var demonstration []string = []string{'testing', 'abc'}
func main(){
	// Code
}
```
# Data
## [[Golang Arrays|Arrays]]
- Fixed size indexable storage
## [[Golang Slices|Slices]]
- Dynamic indexable storage
## [[Golang Functions]]
## [[Golang Maps|Maps]]
- Maps key-value pairs
## [[Golang Types|Types]]
## [[Golang Variables |Variables]]
- When declaring a variable, if not defined, defaults to the zero value of that type
## [[Golang Operators|Operators]]
- Fairly standard operators.
- 2 golang specific operators
## [[Golang Pointers|Pointers]]



# Flow Control
## [[Golang Loops|Loops]]
- For Loops
- While Loops
## [[Golang Conditionals|Conditionals]]
- If Statements 
- Switch Statements
## [[Golang Defer|Defer]]
- Waits till the function is returning before calling this function.






# Composition & Objects
## [[Golang Structs|Structs]]
Define a 'thing', as a set of properties/variables.
## [[Golang Interfaces|Interfaces]]
Define a 'thing', as a set of functions. 
Anything that implements this set of functions can then be used in place of the interface in any function calls / expressions



# Channels
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
for i:= range ch:
	// Code here
```

## Select statements 
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

#  [[Golang Concurrency|Concurrency]]
Running in parallel is easy with just a keyword ```go```
## Thread management
Use wait groups to manage/synchronize worker groups
```go
var wg sync.WaitGroup
wg.Add(1)
go func(){ defer wg.Done()}()
wg.Wait()
```

## Thread safety
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

# Errors
## Error handling
```go
	if err != nil {
	    return
	}
```



# Modules & Imports
```go
import (
	"fmt"
)
```

## Useful Libraries
| Library   | Use                  | Useful functions            |
| --------- | -------------------- | --------------------------- |
| fmt       | Printing to console  | fmt.Println(), fmt.Printf() |
| time      | Time functions       | time.Now()                  |
| math/rand | Randomness           | rand.Intn()                 |
| math      | Math                 | math.Sqrt(), math.pi,       |
| sync      | Handling concurrency | sync.WaitGroup , sync.Mutex |
| io        | input/output         | io.Reader                   |
| image     | images               | image.NewRGBA               |
