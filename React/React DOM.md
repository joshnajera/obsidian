# Methods
### .render()
ReactDOM.render(<HTML_TO_RENDER>, DESTINATION)
```js
ReactDOM.render(<h1>Hello, everyone!</h1>, document.getElementById("root"));
```
Note, you can only insert one root node, cannot insert sibling root nodes

## .createRoot()
```js
ReactDOM.createRoot(document.getElementById("root").render(<html></html>));
```