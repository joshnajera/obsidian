## Shorthand
Use   { (conditional_statement) && JSX_element_to_render }
Example:
```js
import React from "react"

export default function Card(props) {
    return (
        {props.openSpots === 0 && <div className="card--badge">SOLD OUT</div>}
    )
}
```

