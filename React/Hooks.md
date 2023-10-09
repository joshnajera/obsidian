- Can only be called at the top level, not within javascript function loops etc
# Types
### Basic 
- useState
- useEffect
- useContext
### Additional
- useRef
- useReducer
- useCallback
- useMemo
- useImperitiveHandle
- useLayoutEffect
- useDebugValue

# useState()
- Allows for you to create reactive data
- Causes the component to rerender when modified.
- Returns two values, a getter and setter
```jsx
import {useState} from 'react';
let [valueExample, setValueExample] = useState('Default');
// Warning the following would infiinite loop
setValueExample('newValue');
// OR
setValueExample((previousState) => previousState + 1)
```

# useEffect()
- Watches for changes, then performs callback
- Happens on componentDidMount, componentDidUpdate, componentWillUnmount lifecycle hooks/events
- 
```jsx
let [valueExample, setValueExample] = useState('Default');
	useEffect(() => {
		// Infinite loop!  Update value -> update dom -> update value
		// setValueExample("SomeVal")
	})
```

Do NOT use this particular example with useEffect() or else you will get infinite loop.  

Fix: Add a second argument for 'dependencies'
```jsx
	useEffect(() => {
		// 
	}, [valueExample])
```

Add tear-down code
- Implemented by returning a function in our useEffect callback
```jsx
	useEffect(() => {
		// 
	return () => {
		// some tear-down code
	}
	}, [valueExample])
```
# useContext()
- Allows you to share or scope values through the entire component tree
- Values get updated everywhere automatically upon change
```jsx
// variable to be shared
const moods = {
	happy: "😀",
	sad: "🥲"
}
// Create a context, attach it to moods
const MoodContext = createContext(moods);

function App(props) {

	// Set up the context's provider, and bind the value 
	return(
		<MoodContext.Provider value={moods.happy}>
			<EmojiComponent />	
		</MoodContext.Provider>
	)
}
```

```jsx
export default function EmojiComponent(props){
const mood = useContext(MoodContext);
return(
	<h1>Mood: {mood}</h1>
)
}
```




# useRef()
- Creates a mutable object that will keep the same reference between renders.
- Doesn't trigger rerender when value changes
- Can be used to grab native HTML elements from JSX
- Notice how we simply create a ref, and assign it in JSX template, it automatically will get bound to that element
- Dereference using current
```jsx
const myBtn = useRef(null);
const clickMyBtn = () => myBtn.current.click();

return(
	<button ref={myBtn}>Clicky!</button>
);
```


# useReducer()
- Similar to set state, but using a 'redux' pattern
- Instead of affecting state  directly, you 'dispatch' an action, which go to a 'reducer function', which determines how to compute the next state
```jsx
function reducer(state, action) {
	switch(action.type) {
	case 'increment':
		return {count: state.count + 1};
	case 'decrement':
		return {count: state.count - 1};
	default:
		throw new Error();
	}
}

function App() {
	const defaultValue = {count: 0};
	const [state, dispatch] = useReducer(reducer, defaultValue);
return(
	<>
	Count: {state.count}
	<button onClick={()=> dispatch({type: 'decrement'})}> - </button>
	<button onClick={()=> dispatch({type: 'increment'})}> + </button>
	</>
);
}
```


# useMemo()
- Used for optimization
- Implements 'memoization' aka remembering the last result
- Recomputes on dependency change
- caches result
- Kind of similar to useEffect, but specifically designed for recalculating a value. Not performing a side-effect

```jsx
function App(props){

const [count, setCount] = useState(50);

// The
const expensiveCount = useMemo(() => {
	return count ** 2;
}, [count]);

}
```



# useCallback()
- Like memoization -- but for a function
- Re-renders & caches when dependency list is changed
- Used when many children depend on the same output of the function
	- Normally, the function will get re-rendered for each component it exists in
 - With memoization we prevent this rerender and it uses the same cached function

```jsx
function App(){

const showCount = useCallback(() => {
	alert(`Count: ${count}`);
}, [count]);

return(
	<SomeChild handler={showCount} />
	<SomeChild2 handler={showCount} />
);
}
```




# useImperitiveHandle()
- Used to define functionality which the parent component can call upon
- Can only be used within a `forwardRef`
- 
```jsx
// ParentComponent.js
import React, { useRef } from 'react';
import ChildComponent from './ChildComponent';

const ParentComponent = () => {
  const childRef = useRef(null); // Must get a reference to the child

  const handleIncrement = () => {
    // Call the increment function exposed by the child
    childRef.current.increment(); // Using the ref and exposed function, we can call it.
  };

  return (
    <div>
      <button onClick={handleIncrement}>Increment Child Count</button>
      <ChildComponent ref={childRef} />
    </div>
  );
};

export default ParentComponent;
```

```jsx
// ChildComponent.js
import React, { useRef, useImperativeHandle, useState } from 'react';

const ChildComponent = React.forwardRef((props, ref) => {
  const [count, setCount] = useState(0);

  const increment = () => {
    setCount(count + 1);
  };

  // Expose the increment function to the parent through the ref
  useImperativeHandle(ref, () => ({
    increment
  }));

  return (
    <div>
      <p>Count: {count}</p>
      <!--<button onClick={increment}>Increment</button>-->
    </div>
  );
});

export default ChildComponent;
```




# useLayoutEffect
- Used like useEffect
- Callback will be run after rendering the component, but before the changes have been made to the screen.
```jsx
function App(){
const myBtn = useRef(null);

useLayoutEffect(() => {
const rect = myBtn.current.getBoundingClientRect();
console.log(box.height);
})

return (
	<button ref={myBtn}></button>
)
}
```


# useDebugValue()
- Mostly helpful when creating your own hooks
- Allows you to create your own labels in React Dev Tools
```jsx

function useDisplayName(){
	const [displayName, setDisplayName ]  = useState("");

	useEffect(() => {
		const data = "abcd"; // Normally would be some api call or something
		setDisplayHName(data)
	}, []);

	useDebugValue(displayName ?? 'loading...'); // Will show in react dev tools
	
	return displayName;
}


function App(){
const displayName = useDisplayName();


return <button>{displayName}</button>
}
```