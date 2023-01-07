# If Statement
```go
// If condition
if expression {
	// Code
} else {
	// Code
}
// If w short statement
if var var1:= val; expression {
	// Code
}

```
# Switch Statement
```go
switch expression {
	case val:
		// Code
	default:
		// Code
} 
// Can be used without condition to acheive same as long if/else chain
switch {
	case expression:
		// Code
	case expression:
		// Code ...
	default:
		// Code
}
```
- Evaluated top->bottom
- Note how no break statement is needed at the end, unlike other languages