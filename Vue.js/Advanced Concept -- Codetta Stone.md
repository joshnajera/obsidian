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
// Delete storage variable
localStorage.remove("someVariableName");
// Clear storage variable
localStorage.clear();

const route = useRoute();
console.log("url param: " + route.params); 
//  Will be an object with the variables inside 
console.log("url param: " + route.params.id); 
// when it comes to our particular example in [[Router]],   note: Comes in as strings. you will need to cast it
console.log( route.query ); // Get query params

const router  = useRouter();
// Push to query parameter
router.push({query:{ someParameter: 1337 }});
// Change the route
router.push("/somepath/");
// Navigate backward
router.back();

// Data binding
const hello_world = ref("Hi there");  // ref() can be primitive or nonprimitive
const some_bool = ref(false);
const some_int = ref(0);
const hello_world2 = reactive({}); // Must be an object
const items = ref([]);
// Watch for changes -- typically for ref() with objects/arrays?:
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
	myFirstProp : { // Note: We define with camelCase, but use kebab in template
		type: Object,
		required: true,
	},
	mySecondProp : String,
	modelValue : String, // Note: v-model gets automatically bound to modelValue
});



// Sending data outward
const emit = defineEmits(["my-emit-function", "some-custom-emit"]);

function someFunc(){
	some_int.value += 1; //Note how we have to take the value of the variable
	var extraData = {};
	// Emit an event, 
	emit('my-emit-function', extraData);  // sends the extra variables as 'params'
	// To see how to catch emitted events look in the <template> of this file
}
</script>


<template>
	<!-- HTML -->
	{{moustacheSyntaxVariable}}
	{{$attrs}} <!-- Anything not defined as a prop or event will be available -->
	<!-- Note kebab case in following prop name--> 
	<someTemplateWithProp :my-first-prop="{someKey: 'someValue'}"> 
		<!-- Note we can dynamically bind with ':' -->
		<!-- This allows us to pass data, like objects -->
		<!-- slot data for someTemplateWithProp -->
	</someTemplateWithProp>
	<slot>
		This is some default / fall-back content in the slot
		<!-- Allows you to insert data from non-self-closed custom tags -->
	</slot>
	<!-- Named Slot template definition -->
	<slot name="someSecondarySlot">
		<!-- Similar, but allows you to name additional ones -->
	</slot>
	<!-- Named Slot implementation -->
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
	<keep-alive> <!-- cache the data, if we navigate away we save it -->
		<div v-if="some_bool">
			<!-- This will conditionally render if some_bool evaluates to true -->
		</div>
	</keep-alive>
	<div v-else-if="some_other_bool">
	</di>
	<div v-else>
	</div>
	<div v-show="some_bool">
		<!-- This will conditionally display if some_bool evaluates to true -->
	</div>

	<!-- 2 way binding onto a value -->
	<textarea v-model="hello_world"> </textarea> 
	<!-- v-model's can be named -->
	<input type='text' v-model:somePropName = "some Value" />

	
	<!-- Catch Emitted Event -->
	<someCustomElement @custom-emit-function="custom_emit_handler" />
	<!-- Inline Emit:  Notice the $ on emit & event, these are nice shorthands -->
	<button @click="$emit('some-custom-emit', $event.target.value)">
	<!-- 2-way Binding to parent variable -->
	<input :value="modelValue" @input="$emit('update:modelValue', $event.target.value)" />
	
	<!-- For loop -->
	<div>
		<customElement v-for="item in items">
		<customElement v-for="(item, index) in items">
	</div>
	<!-- Another way to do for loop -->
	<div>
		<div v-for="item in items">
			<h1>{{item.title}}</h1>
			<p>{{item.text}}</p>
		</div>
	</div>
</template>


<style scoped> /* scroped makes it scoped to this component */
/* Style */
</style>
```

