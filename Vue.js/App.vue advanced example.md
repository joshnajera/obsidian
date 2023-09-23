<script setup> // 'setup' allows us to use composition API instead of the old options API
import customElement from 'customElement.vue';
import { ref, reactive, defineEmits, defineProps } from 'vue';
import { useRoute, userRouter } from 'vue-router'; 
// userRoute Allows for use of fetching route info, including query parameters and url parameters
// useRouter Allows for modification of the current route, such as changing the route or appending query parameters

const route = useRoute();
console.log("url param: " + route.params); //  Will be an object with the variables inside 
console.log("url param: " + route.params.id); // when it comes to our particular example in [[Router]],   note: Comes in as strings
console.log( route.query ); // Get query params

const router  = useRouter();
// Push to query parameter
router.push({query:{ someParameter: 1337 }});
// Change the route
router.push("/somepath/");

// Data binding
const hello_world = ref("Hi there"); // Can be any primitive, but not object?  Composition API
const some_bool = ref(false);
const some_int = ref(0);
const hello_world2 = reactive(); // Must be an object.  Composition API
const items = ref([]);
const props_old_method = defineProps(["myFirstProp"]); // Old method -- Less control
const props = defineProps({ // New method -- Gives more control
	myFirstProp : {
		type: Object,
		required: true,
	},
});


// Sending data outward
const emit = defineEmits(["my-emit-function"]);
emit('my-emit-function', extraData);  // Emit an event, sends the extra variables as 'params'
// To see how to catch emitted events look in the <template> of this file

function someFunc(){
	//code
	some_int.value += 1; //Note how we have to take the value of the variable
	
	var extraData = {};
}


</script>

<template>
<!-- HTML -->
<slot>
	This is some default / fall-back content in the slot
	<!-- Allows you to insert data from non-self-closed custom tags -->
</slot>
<slot name="someSecondarySlot">
	<!-- Similar, but allows you to name additional ones -->
</slot>

<h1>{{ hello_world }}</h1> <!-- Moustache syntax -->
<button v-on:click="someFunc()">Click me full syntax</button>
<button @click="someFunc()">Click me shorthand</button>
<div v-if="some_bool">
<!-- This will conditionally render if some_bool evaluates to true -->
</div>
<div v-else-if="some_other_bool">
</di>
<div v-else>
</div>
<div v-show="some_bool">
<!-- This will conditionally display if some_bool evaluates to true -- works via display -->
</div>
<textarea v-model="hello_world"></textarea> <!-- 2 way binding onto a value -->
<ul>

<!-- Catch Emitted Event -->
<someCustomElement @custom-emit-function="custom_emit_handler()" />

<!-- For loop -->
<customElement v-for="item in items">
<customElement v-for="(item, index) in items">
<!-- Another way to do for loop -->
<div>
	<div v-for="item in items">
		<h1>{{item.title}}</h1>
		<p>{{item.text}}</p>
	</div>
</div>
</ul>
</template>

<style scoped>
/* Style */
</style>


