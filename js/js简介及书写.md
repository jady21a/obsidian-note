Js 组成：
-   **ECMAScript**：JavaScript 的**语法标准**。包括变量、表达式、运算符、函数、if 语句、for 语句等。
    
-   **DOM**：Document Object Model（文档对象模型），JS 操作**页面上的元素**（标签）的 API（**a**pplication **p**rogramming **i**nterface **应用程序接口**）。比如让盒子移动、变色、改变大小、轮播图等等。
    
-   **BOM**：Browser Object Model（浏览器对象模型），JS 操作**浏览器部分功能**的 API。通过 BOM 可以操作浏览器窗口，比如弹框、控制浏览器跳转、获取浏览器分辨率等等。
通俗理解就是：ECMAScript 是 JS 的语法；DOM 和 BOM 是浏览器运行环境为 JS 提供的 API。

## JavaScript 的特点

### 1：解释型语言
程序执行之前，不需要事先被翻译为机器码；而是在运行时，边翻译边执行（翻译一行，执行一行）。
### 2：单线程

### 3：ECMAScript 标准
前身为欧洲计算机制造商协会, 英文名称是 European Computer Manufacturers Association

# 书写  helloworld
JS 代码的书写位置
1.  **行内式**：写在标签内部。(body 内)   //不推荐
```
<input type="button" value="点我点我" onclick="alert('千古壹号 Hello 方式1')" />

```
关于代码中的「引号」，在 HTML 标签中，我们推荐使用双引号，JS 中我们推荐使用单引号

2.  **内嵌式**（内联式）：写在 body 标签中。
    在 HTML 页面的 `<body>` 标签里放入`<script type=”text/javascript”></script>`标签对，并在`<script>`里书写 JavaScript 代码：
3.  **外链式**：引入外部 JS 文件。（body 内）//推荐
```
<script src="a.js"></script>
```
## JavaScript 一些简单的语法规则
JS 对换行、缩进、空格不敏感。每一条语句以分号结尾。每一条语句末尾要加上**分号**。

##   JavaScript 输出语句
#### 弹窗：alert () 语句
```
alert('千古壹号');
```
### 弹窗：confirm () 语句（含确认/取消）
```
var result = confirm('你听说过千古壹号吗？');
console.log(result);
```

### 弹出输入框：prompt()语句 
```
var a = prompt('请随便输入点什么东西吧');
console.log(a);
```
**alert()和 prompt()的区别：**

-   alert() 语句中可以输出数字和字符串，如果要输出字符串，则必须用引号括起来；prompt()语句中，用户不管输入什么内容，都是字符串。
-   prompt() 会返回用户输入的内容。我们可以用一个变量，来接收用户输入的内容。
- **总结**：alert () 主要用来显示消息给用户，console. Log () 用来给程序员做调试用。