
## Static 1-Way binding 
- Will not be updated 'automatically' when staticValueExample is changed
```JSX
function Message() {
	let staticValueExample = 'Josh';
	return <h1>{staticValueExample}</h1>;
}
```

You can bind directly to props
```jsx
function Message(){
	let someVal = "ASDF";
	return <example propName={someVal}/>;
}
```

## Dynamic 1-Way binding   
- Uses `useState` [[Hooks|Hook]]
```JSX
import {useState} from 'react';
function Message() {
	let [staticValueExample, setStaticValueExample] = useState('Josh');
	return <h1>{staticValueExample}</h1>;
}
```

