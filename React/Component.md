```js
import React from "react"

export default function ComponentName(){
return(
<h1 className="someClass" >learning react</h1>
)
}

ReactDOM.render(
<div>
<ComponentName />
</div>,
document.getElementById("rootDestination")

//or

ReactDOM.render(<ComponentName/>, document.getElementById("rootDestination"))
)

```

the function name must match the component name
NOTE: see how React renders using className = , not  class =,   this is a JSX thing?

