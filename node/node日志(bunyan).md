```javascript
var bunyan = require('bunyan');
var log = bunyan.createLogger({
	name: 'play',
	level: 'trace'
});
log.trace('this one does not emit');
log.debug('hi on debug'); // console.log
log.info('hi on info'); // console.info
log.warn('hi on warn'); // console.warn
log.error('hi on error'); // console.error
```
