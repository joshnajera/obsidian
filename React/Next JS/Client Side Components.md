
# How to make a client-side component
- Make the entire component client-side
- Simply add `'use client';` at the top of your jsx/tsx file.
```jsx
'use client'; // Without this line we would fail to bind to the onClick event
import React from 'react';

export default function MyComponent() {

return (
	<button onClick={()=>{console.log("ASDF")}}>Add to card</button>
);
}
```

