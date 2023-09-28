Ionic Framework has its router outlet, called `<ion-router-outlet>`
Because of this special handling, certain Vue Router components such as `<keep-alive>`, `<transition>`, and `<router-view>` should not be used in Ionic Vue applications..

router/index.ts
```typescript
import { createRouter, createWebHistory } from '@ionic/vue-router';
import { RouteRecordRaw } from 'vue-router';
import HomePage from '@/views/Home.vue';


const routes: Array<RouteRecordRaw> = [
  {
    path: '/',
    name: 'Home',
    component: HomePage,
  },
];

const router = createRouter({
  // Note how this differs from vue routers here
  history: createWebHistory(process.env.BASE_URL),
  routes,
});

export default router;
```