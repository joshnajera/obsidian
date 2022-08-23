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