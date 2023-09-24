```html
<script setup> // 'setup' allows us to use composition API instead of the old options API
import customElement from 'customElement.vue';
import { ref, reactive, defineEmits, defineProps, watch } from 'vue';
import { useRoute, userRouter } from 'vue-router'; 
// userRoute Allows for use of fetching route info, including query parameters and url parameters
// useRouter Allows for modification of the current route, such as changing the route or appending query parameters

// Set localstorage info
localStorage.setItem("someVariableName", JSON.stringify(someVariable));
// Get localstorage info
var the_storage = localStorage.getItem("someVariableName");
if (the_storage){
	the_storage = JSON.parse(the_storage);
}
// Delete
localStorage.remove("someVariableName");
// Clear
localStorage.clear();

const route = useRoute();
console.log("url param: " + route.params); //  Will be an object with the variables inside 
console.log("url param: " + route.params.id); // when it comes to our particular example in [[Router]],   note: Comes in as strings
console.log( route.query ); // Get query params

const router  = useRouter();
// Push to query parameter
router.push({query:{ someParameter: 1337 }});
// Change the route
router.push("/somepath/");
// Navigate backward
router.back();

// Data binding
const hello_world = ref("Hi there"); // Can be any primitive, but not object?  Composition API
const some_bool = ref(false);
const some_int = ref(0);
const hello_world2 = reactive(); // Must be an object.  Composition API
const items = ref([]);
// Watch for changes
watch(items, (newValue, oldValue) =>{
	// Code to execute when items changes
},{
	// optional settings for watch
	deep: true, // watch for data within data?
});
// Automatically recompute values programmatically
const someAutoComputed = computed(() => {
	return items.reduce((a, b) => a + b, 0); // Whenever items changes, this value auto recalculates
});
const props_old_method = defineProps(["myFirstProp"]); // Old method -- Less control
const props = defineProps({ // New method -- Gives more control
	myFirstProp : {
		type: Object,
		required: true,
	},
});


// Sending data outward
const emit = defineEmits(["my-emit-function", "some-custom-emit"]);
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
<!-- Named Slot Implementation -->
<someSlottedThing>
	slotted content
	<template v-slot:mySlotName1>
		slot content
	</template>
	<!-- OR -->:
	<template #mySlotName1>
		slot content
	</template>
</someSlottedThing>

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
<someCustomElement @custom-emit-function="custom_emit_handler" />
<!-- Inline Emit -->
<button @click="$emit('some-custom-emit')">

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


<style scoped> /* scroped makes it scoped to this component */
/* Style */
</style>
```

