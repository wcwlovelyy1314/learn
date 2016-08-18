```javascript
ejs 的标签系统非常简单，它只有以下三种标签：

    <% code %>：JavaScript 代码。
    <%= code %>：显示替换过 HTML 特殊字符的内容。
    <%- code %>：显示原始 HTML 内容。

注意： <%= code %> 和 <%- code %> 的区别，当变量 code 为普通字符串时，两者没有区别。
当 code 比如为 <h1>hello</h1> 这种字符串时，<%= code %> 会原样输出 <h1>hello</h1>，而 <%- code %> 则会显示 H1 大的 hello 字符串。 
```
