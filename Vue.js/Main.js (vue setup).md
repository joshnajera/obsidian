
``` html
<script>

import { createApp } from 'vue'
import App from './App.vue'
import router from './router'  // [[Router]]  router/index.js

const app = createApp(App) // Initialize

app.use(router) // Add 'middleware' router, which is created in Router file

app.mount('#app') // Bind to our element with id of #app

</script>
```