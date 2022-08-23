```go
// General error ctach
if err != nil{
	log.Fatal(err)
}

// Specific error catch
import "error"
if errors.Is(err, os.ErrNotExist){

}
```
