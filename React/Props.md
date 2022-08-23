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