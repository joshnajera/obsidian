
## Notes
- Stores data as a string, so it forgets types
- You should use json

```javascript
	// Submission
	window.localStorage.setItem(key, JSON.stringify(val))
	// Retrieveal 
	let storageVal = window.localStorage.getItem(key);
	storageVal = (storageVal) ? JSON.parse(storageVal) : false
```

^8c9786
