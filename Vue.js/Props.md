
Allow for you to pass data into a child component
someTemplateWithProp.vue
```javascript
import {  defineProps } from 'vue';

// Old method -- Less control
const props_old_method = defineProps(["myFirstProp"]); 

// New method -- Gives more control
const props = defineProps({ 
	myFirstProp : { // Note: We define with camelCase, but use kebab in template
		type: Object,
		required: true,
	},
	mySecondProp : String,
	modelValue : String, // Note: v-model gets automatically bound to modelValue
});

```

then we can use the props in our template
```html
<!-- Note kebab case in following prop name--> 
<someTemplateWithProp my-first-prop="{someKey: 'someValue'}"> 
</someTemplateWithProp>
```

and access it in the sub-template
someTemplateWithProp.vue
```html
<template>
{{myFirstProp}}
</template>
```