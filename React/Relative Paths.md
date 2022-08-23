When dealing with relative paths it may be necessary to import the path and use it as a variable so the bundler will know how to manage/rename/reorganize

```js
import logo from ".assets/someLogo.png"

function App(){
return(
<div className="App">
<img src={logo} />
</div>
)
}
```