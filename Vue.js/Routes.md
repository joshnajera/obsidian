
How to use routes in nav:
<script>
	import { RouterLink, RouterView } from 'vue-router';
</script>
<template>
	<nav>
		<!-- Links to route us, these correlate to router index.js -->
		<RouterLink to='/'>Home</RouterLink> 
		<RouterLink to='/about'>About</RouterLink>
	</nav>

<RouterView/> <!--Tells us where to render the output -->
</template>
<style>
</style>





<script>
// router/index.js:
const router = createRouter({  
  history: createWebHistory(import.meta.env.BASE_URL),  
  routes: [  
    {  
      path: "/",  
      name: "home",  
      component: HomeView,  
    },  
    {  
      path: "/developer/:profileNumber",  
      name: "developer",  
      component: () => import("../views/devView.vue"),  
    },  
  ],  
});
</script>




