
# Use
Different than the React library, this one allows for modification of DOM elements assuming you are on web. (As opposed to React Native stuff)


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