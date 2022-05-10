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