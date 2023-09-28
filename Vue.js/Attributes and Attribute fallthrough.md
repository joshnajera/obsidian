## Attributes

Example: Given this element with attribute `thisIsAnAttribute`
```html
<someElement thisIsAnAtribute="value">
```
Then in it's template
```html
<template>
	{{$attrs}}
</template>
```
will output: `{"thisIsAnAttribute":"value"}`

We also get access in the `<script>`
```javascript
import { useAttrs } from 'vue';
const attrs = useAttrs();
```

One thing to note is if an attribute is 'caught' using [[Vue.js/Props|Props]] then it gets removed from $attrs


## Fallthrough
When attributes are places on a custom component, they automatically get applied to their child root element.
__Example__:
myButton.vue definition
```html
<template>
	<button>
</template>
```
implementation
```html
<myButton class="test">
```
output
```html
<button class="test">
```



## Merging
When `class` or `style` get defined on a parent and a child root node, their values get merged.
Other elements however, use the value of the parent component will take precedence over the child root node.