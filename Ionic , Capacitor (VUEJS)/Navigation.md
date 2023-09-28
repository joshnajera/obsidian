First see [[Router Explanation]] first to see how to set up a router

Then in your code you can create router-link's like this
```html
<ion-button router-link="/detail">Go to detail</ion-button>
```
where the path is the same as that defined in the router

Programmatic routing
```html
<ion-button @click="() => router.push('/detail')">Go to detail</ion-button>
```
```javascript
  import { useRouter } from 'vue-router';
```





## Ion Router
```html
<script setup>
	import { useIonRouter } from '@ionic/vue';
    const ionRouter = useIonRouter();
    ionRouter.push('/page2', customAnimation); // customAnimation is some custom code

    ionRouter.navigate('/page2', 'forward', 'replace', customAnimation);  // More advanced technique with navigate
	ionRouter.goBack() // Navigate backward
</script>

```