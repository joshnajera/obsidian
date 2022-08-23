
# Pointers
Simply a different way of declaring them
```go
// Syntax
	var var1 *Type
// Or to get it from the address of another variable
	var var2 = &someVariable
// Dereferencing
	*var1 = *var2 * 2
// Example Usage
	i:=42
	p:=&i
	*p = 11
	fmt.Prinln(*p)
```
