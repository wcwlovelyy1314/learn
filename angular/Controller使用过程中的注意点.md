- 不要试图去复用controller，一个控制器一般只负责一小块视图
- 不要在controller中操作dom，这不是控制器的职责
- 不要在controller里面做数据的格式化，ng有很好用的表单控件
- 不要在controller里面做数据过滤的操作，ng有$filter服务
- 一般来说,controller是不会互相调用，控制器之间的交互会通过事件交互
