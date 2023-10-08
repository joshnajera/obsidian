- We always use PascalCasing for naming components
- The component name and file name should match
- Export default helps for dynamic & lazy loading?
- The function name must match the component name

```jsx
import React from "react"

export default function ComponentName(){
	return (
		<h1 className="someClass" >learning react</h1>
	)
}

```


main.tsx / maint.jsx
```jsx

ReactDOM.render(
<div>
<ComponentName />
</div>,
document.getElementById("rootDestination")

//or

ReactDOM.render(<ComponentName/>, document.getElementById("rootDestination"))
)

```

NOTE: See how React renders using className = , not  class =,   this is bc class is a reserved word in javascript

