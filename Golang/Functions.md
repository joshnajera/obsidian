``` go
// Syntax	
	func (receiver Type) funcName(arg1 argType) returnType{
		return
	}
	func funcName[T someType](s []T, x T) returnType {
	}
// Variable number of arguments
func funcName(varName ...someType) 

// Example Usage
func (c Circle) area (float){
	return (c.radius**2) * math.pi
}
func Index[T comparable](s []T, x T) int {
	return 0
}
```

Can be passed like values (first class functions?)
Optionally define receiver type, if you want class-like methods
Optionally define type parameter constraints prior to parameters in [] brackets such as 'comparable'