# Web Routers
#middle-ware #web/development #development
## Use
- Redirect web traffict to [[controllers]]
- Given:  a specific url path (e.g.  /api/public/ , etc)  
 	+ HTTP verb (e.g. `GET`, `POST`, `PUT`, `DELETE`, etc.)  
   -> Then call upon the appropriate controller function


## Example

Router Code
```js
// my_router.js
var express = require('express');
var router = express.Router();
// Require controller modules.
var my_controller = require('../controllers/myController');
router.get('/', my_controller.index);
router.post('/my/path/create', my_controller.create_post);
module.exports = router;
```

Implementation in express app.js
```js
// my_app.js
 var indexRouter = require('./routes/index');
 var my_router = require('./routes/my_router');
 app.use('/', indexRouter);
 app.use('/my', my_router);

```
