```javascript
use admin
db.runCommand({
   copydb: 1,
   fromdb: "test",
   todb: "records"
})
```
