# nodejs

1 CommonJS
- 模块引用
```js
var math = require('math')
```
- 模块定义
模块中存在一个 module 对象, exports 是 module 的属性
```js
exports.add = function(){
...
}
```
- 模块标识
小驼峰命名的字符串，相对路径或者绝对路径，可以没有js后缀
