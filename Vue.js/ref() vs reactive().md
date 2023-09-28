## ref()
- Uses .value to dereference the value
- Shallow reactivity
- Could be considered more 'lightweight'
```javascript
const user = ref({ name: 'John Doe', age: 30 });

console.log(user.value.name); // Access a property of the object
user.value.age++; // Modify a property of the object

// Changes to the object's properties are not deeply reactive
user.value.name = 'Jane Doe'; // Does not trigger reactivity
```
## reactive()
- Does not require the use of .value to dereference value
- Deeply reactive
```javascript
const user = reactive({
  name: 'John Doe',
  address: {
    city: 'New York',
    postalCode: '10001'
  }
});

user.name = 'Jane Doe'; // Triggers reactivity
user.address.city = 'San Francisco'; // Triggers reactivit
```