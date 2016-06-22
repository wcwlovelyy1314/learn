```javascript
var _ = require('lodash');
var arr = [{
	a: 1,
	b: 2
}, {
	a: 11,
	b: 22
}];
console.log(_.keyBy(arr, 'a'));
{ '1': { a: 1, b: 2 }, '11': { a: 11, b: 22 } }
```
