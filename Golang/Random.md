```go
import "time" "math/rand"
seed := time.Now().Unix()
rand.Seed(seed)
randNum := rand.Intn(100) // 0 - 99 
```