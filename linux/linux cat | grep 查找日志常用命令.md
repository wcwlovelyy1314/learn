```javascript
1. 通常查找出错误日志 cat error.log | grep 'nick' , 这时候我们还有个需求就是输出当前这个日志的前后几行：

cat error.log | grep -C 5 'nick' 显示file文件里匹配foo字串那行以及上下5行
cat error.log | grep -B 5 'nick' 显示foo及前5行
cat error.log | grep -A 5 'nick' 显示foo及后5行
```
