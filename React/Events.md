## Basics
Event names are always camelCased
Can be added directly into jsx

```js
import React from "react"

export default function App() {
    function handleClick() {
        console.log("I was clicked!")
    }

    
    return (
        <div className="container">
            <img src="https://picsum.photos/640/360" />
            <button onClick={handleClick}>Click me</button>
        </div>
    )
}

```
Notice: when passing a function into the event handler (onClick in this case), don't pass the parenthesis, otherwise it will be called once immediately on load.


### All Events
https://reactjs.org/docs/events.html