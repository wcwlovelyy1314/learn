```javascript
var bunyan = require('bunyan');
var log = bunyan.createLogger({
	name: 'play',
	level: 'trace'//级别最高，输出五种
});
log.trace('this one does not emit');
log.debug('hi on debug'); // console.log
log.info('hi on info'); // console.info
log.warn('hi on warn'); // console.warn
log.error('hi on error'); // console.error
日志级别：trace>debug>info>warn>error
```
