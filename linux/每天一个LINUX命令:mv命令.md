```javascript
- mv:移动文件或者把文件重命名
```
第一个参数 | 第二个参数 | 结果 |
--- | --- |---
目录 | 目录（存在：重命名，不存在：创建） | 重命名 |
文件 |目录 |移动文件
文件 |文件 |重命名
```javascript
- mv test.txt test.log:把文件test.txt改为test.log
- mv -b:如果需要覆盖文件，则覆盖前先备份
  -b 不接受参数，mv会去读取环境变量VERSION_CONTROL来作为备份策略。
  --backup该选项指定如果目标文件存在时的动作，共有四种备份策略：
  1.CONTROL=none或off : 不备份。
  2.CONTROL=numbered或t：数字编号的备份
  3.CONTROL=existing或nil：如果存在以数字编号的备份，则继续编号备份m+1...n：
执行mv操作前已存在以数字编号的文件log2.txt.~1~，那么再次执行将产生log2.txt~2~，
以次类推。如果之前没有以数字编号的文件，则使用下面讲到的简单备份。
  4.CONTROL=simple或never：使用简单备份：在被覆盖前进行了简单备份，简单备份只能有一份，再次被覆盖时，简单备份也会被覆盖。
- mv -f:force,强制，如果目标文件已经存在，不会询问，直接覆盖
- mv -i:如果目标文件存在，就会询问是否覆盖
- mv -u:如果目标文件存在，并且source比较新，才会更新
- mv -t: --target-directory = DIRECTORY move all SOURCE arguments into <br>DIRECTORY,即指定mv的目标目录，
改选项适用于移动多个源文件到一个目录的情况，此时目标目录在前，源文件在后
```

