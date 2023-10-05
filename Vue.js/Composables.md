
## The Idea
Combine smaller bits of related logic to reuse elsewhere. Typically by breaking them down into small functions?


# Example
Make the following reusable

![[LocalStorage (javascript concept)#^8c9786]]

### Result
useLocalStorage.js
```javascript
import {ref, watch} from 'vue';

export default function (key = "someStorageVar", val = 0) {
	const val_ref = ref(val); // initialize with fallback
	const storageVal = window.localStorage.getItem(key);
	if (storageVal) {
		val_ref.val = JSON.parse(storageVal);
	}

	watch( val_ref, (newVal) => {
		window.localStorage.setItem(key, JSON.stringify(val));
	}, {deep:true});
}
```

### Usage

```javascript
import useLocalStorage from "../scripts/useLocalStorage.js";

const isOpen = useLocalStorage(true);
```
