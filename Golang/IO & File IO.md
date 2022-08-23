
# Input
Method 1
```go
import "fmt"
fmt.Scanln(&destinationVariable)
```

Method 2
```go
import "bufio" "os"
reader := bufio.NewReader(os.Stdin)
input, err := reader.ReadString('\n') // Read until newline/enter
```

```go
import "fmt"
fmt.Println("output")
```


# File I/O
## Create and write to file
```go
import "os"
// Create file and open
f, err := os.Create("filename.txt")
if err != nil{
	log.Fatal(err)
}
defer f.Close()
// Write to file
_,err := f.WriteString(someString)
if err != nil{
	log.Fatal(err)
}

```

## Check if file exists
```go
_, err = os.Stat("filename.txt")
if errors.Is(err, os.ErrNotExist){ // Catching a specific error

}

```

## Open and read a file
```go
import "os"
f, err := os.Open("filename.txt")
// OR
linux_permissions := 644
options := os.O_APPEND | os.O_RDWR
f, err := os.OpenFile("filename.txt", options, linux_permissions) // Options below
if err != nil{
	log.Fatal(err)
}

defer f.Close()
scan := buio.NewScanner(f)
for scan.Scan(){
	fmt.Println(scan.Text()) // Prints one line at a time
}

```

### Options
	**Exactly one of O_RDONLY, O_WRONLY, or O_RDWR must be specified**
	O_RDONLY : open the file read-only
	O_WRONLY : open the file write-only
	O_RDWR   : open the file read-write

	**These can be or'ed**
	O_APPEND : append data to the file when writing
	O_CREATE : create a new file if none exists
	O_EXCL   : used with O_CREATE, file must not exist
	O_SYNC   : open for synchronous I/O
	O_TRUNC  : truncate regular writable file when opened

```go
impor "os"
f, err := os.OpenFile("filename.txt", os.O_APPEND | os.O_RDWR, 644)

```