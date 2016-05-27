```
var ep = new eventproxy();
ep.all('data1_event', 'data2_event', 'data3_event', function (data1, data2, data3) {
  var html = fuck(data1, data2, data3);
  render(html);
});

$.get('http://data1_source', function (data) {
  ep.emit('data1_event', data);
  });

$.get('http://data2_source', function (data) {
  ep.emit('data2_event', data);
  });

$.get('http://data3_source', function (data) {
  ep.emit('data3_event', data);
  });
```
好看多了是吧，也就是个高等计数器嘛。<br>
ep.all('data1_event', 'data2_event', 'data3_event', function (data1, data2, data3) {});<br>
这一句，监听了三个事件，分别是 data1_event, data2_event, data3_event，每次当一个源的数据抓取完成时，就通过 ep.emit() 来告诉 ep 自己，某某事件已经完成了。<br>
当三个事件未同时完成时，ep.emit() 调用之后不会做任何事；当三个事件都完成的时候，就会调用末尾的那个回调函数，来对它们进行统一处理。
