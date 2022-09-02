# Web Framework Controllers
#middle-ware #web/development #development 
- Applies control logic to input and determine what page templates/variables to apply to get desired results
- Used to render / serve page content.

## Use
- [[Routers]] will direct traffic to these
-  Supplies [[Callback]] functions via exports
- Serve / Render Pages
- Often calling on something like a template system like EJS, etc.
## Example


Controller code 
```js
// controller.js
var Book = require('../models/book'); // This is where you would import your db?
exports.author_list = function(req, res) {
	res.send('NOT IMPLEMENTED: Author list');
	// implement templates here?
};
```

