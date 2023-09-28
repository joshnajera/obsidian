You have a basic web file, index.html for example, which has an element which we are hooking into and initializing our 'app'.  This app is defined a .vue file or series of files.  The vue files is a self contained set of code, template, and style.   Example


index.html
```html
<div id="app">
<!--Mounting point-->
</div>
```
main.js
```javascript
import './assets/main.css'
import { createApp } from 'vue'
// Base file to create app from
import App from './App.vue'
// Predefines the routes of the site, used by useRoute, useRouter
import router from './router'

const app = createApp(App) // Create app using App.vue [[Basic Concept]]

app.use(router) 
app.mount('#app') // Attach to HTML element
```

router/index.js
[[Router]]
