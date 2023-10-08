## Default prop 'children' AKA default slot in vue
```jsx
Type MyProps = {
children: ReactNode;
}
export default function ContactCard(props: MyProps) {
	return (
		<h1>{props.children}</h1>
	)
}
```


When in JSX markup, you can insert javascript with {} braces, which will be evaluated

Props get passed in as first argument, name is arbitrary

```js
export default function ConcactCard(props){
	return(
		<h1>{props.name}</h1>
		<!--You can nest components -->
		<Age age={props.age} {...item_spread}/> 
		
	)
}
```



Passing info into a prop
```js
<ContactCard name="Joe" age={5} dead={false} />
```

### Destructuring
- We can destructure to fetch exact values and assign them to variables
```jsx
export default function ContactCard({prop1, prop2}) {
return (
	<h1>{prop1}</h1>
	<h2>{prop2}</h2>
)
}
```


## Adding a Interface/Type to get better syntax support
- We can define an interface for our props to be able to enable typescript features
```jsx
interface myProps {
	items: string[];
	heading: string;
}

export default function ContactCard(props: myProps){
	//...
}
```

```jsx
type MyProps = {
    name: string;
}
export default function Test(props: MyProps){
    return(
        <h1>{props.name}</h1>
    )
}
```


## Passing Functions
- You can also pass functions to children via props
- This function will retain the scope of the variables defined in the parent variable.
```jsx
type MyProps = {
    someFunc: (item:string) => void;
}
export default function Test(props){
	return (
		<button onClick={props.someFunc}>Click Me</button>
	)
}

```