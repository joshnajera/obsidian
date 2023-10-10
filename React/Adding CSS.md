```js
import ".style.css"
```



# Module Imports 
- Allows scoped css
```jsx
import myCustomCss from './src/css/myCustomCss.module.css'

const MyComponent = () => {
return (
	<h1 className={myCustomCss.someClassName}>Test</h1>
);
}
```