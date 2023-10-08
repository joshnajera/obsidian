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