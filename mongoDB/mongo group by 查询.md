```javascript
db.V_SZB_MZXX.aggregate(
  [
  {
      $group : {
        _id : "$jzid", 
        num_tutorial : {$sum : 1}
               }
    },
  {   $match : { 
       num_tutorial : { $gt : 1} } }  
  ]);
  等价与
  select count(*),jzid from V_SZB_MZXX group by jzid having count(*)>1;
  ```
