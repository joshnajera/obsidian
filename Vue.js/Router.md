
How to use routes in nav:
<script>
	import { RouterLink, RouterView } from 'vue-router';
</script>
<template>
	<nav>
		<!-- Links to route us, these correlate to router index.js -->
		<RouterLink active-class='active' to='/'>Home</RouterLink> 
		<RouterLink active-class='active' to='/about'>About</RouterLink>
	</nav>

<RouterView/> <!--Tells us where to render the output -->
</template>
<style>
</style>





<script>
// router/index.js:
import { createRouter, createWebHistory } from 'vue-router';
import { HomeView } from "../views/HomeView.vue";
const router = createRouter({  
  history: createWebHistory(import.meta.env.BASE_URL),  
  routes: [  
    {  
      path: "/",  
      name: "home",  
      component: HomeView,  // This comes from views folder
    },  
    {  
      path: "/developer/:id",  // Dynamic paths -- params via useRoute
      name: "developer",  
      component: () => import("../views/devView.vue"),  
    },  
  ],  
});
export default router;
</script>




