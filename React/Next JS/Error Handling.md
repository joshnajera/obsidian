Create new `error.jsx / tsx` which will automatically run when the error happens.

```jsx
const Error({error, reset }) => {
useEffect(() => {
console.log(error);
}, [error]);

return (
<div>
<h1>Something went wrong</h1>
<button onClick={()=> reset()}>Retry</button>
</div>
)
}
export default Error;
```