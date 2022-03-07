
**HTML** 全称为 HyperText Markup Language，译为**超文本标记语言**

![[Pasted image 20220305212446.png]]

-   问：网页的 head 标签里面，表示的是页面的配置，有什么配置？
-   答：字符集、关键词、页面描述、页面标题、IE 适配、视口、iPhone 小图标等等。
![[Pasted image 20220305220506.png]]

头标签内部的常见标签如下：

-   `<title>`：指定整个网页的标题，在浏览器最上方显示。
-   `<base>`：为页面上的所有链接规定默认地址或默认目标。
-   `<meta>`：提供有关页面的基本信息
-   `<body>`：用于定义 HTML 文档所要显示的内容，也称为主体标签。我们所写的代码必须放在此标签內。
-   `<link>` ：定义文档与外部资源的关系。

**meta 标签**：

meta 表示 “元”。“元” 配置，就是表示基本的配置项目。
（1）字符集 charset：即**网页的编码方式**。
（2）视口 viewport：视口大小
（3） “关键词”：name  ，提高搜索命中率
（4） “页面描述”：content   **SEO**（search engine optimization，搜索引擎优化）

**base 标签**：

```
<base href="/">
```

base 标签用于指定基础的路径。指定之后，所有的 a 链接都是以这个路径为基准。

`<body>` 标签的属性有：
-   `bgcolor`：设置整个网页的背景颜色。
-   `background`：设置整个网页的背景图片。
-   `text`：设置网页中的文本颜色。
-   `leftmargin`：网页的左边距。IE 浏览器默认是 8 个像素。
-   `topmargin`：网页的上边距。
-   `rightmargin`：网页的右边距。
-   `bottommargin` ：网页的下边距。
- `link` 属性表示默认显示的颜色、`alink` 属性表示鼠标点击但是还没有松开时的颜色、`vlink` 属性表示点击完成之后显示的颜色。

 ### 1、编写 XHTML 的规范：

（1）正确的嵌套，不能交叉嵌套。正确写法举例：`<h1><font></font></h1>`

（2）所有的标记都必须小写。

（3）所有的标签都必须闭合。

-   双标签：`<span></span>`
    
-   单标签：`<br>` 建议写成 `<br />` `<hr>` 建议转成 `<hr />`，还有 `<img src=“URL” />`    
    
（4）所有的属性值必须加引号。`<font color="red"></font>`

（5）所有的属性必须有值。`<hr noshade="noshade">`、`<input type="radio" checked="checked" />`

（6）XHTML 文档开头必须要有 DTD 文档类型定义。

tbc [07-HTML标签图文详解（二） | 千古前端图文教程 (qianguyihao.com)](https://web.qianguyihao.com/01-HTML/07-HTML%E6%A0%87%E7%AD%BE%E5%9B%BE%E6%96%87%E8%AF%A6%E8%A7%A3%EF%BC%88%E4%BA%8C%EF%BC%89.html#%E6%9C%AC%E6%96%87%E4%B8%BB%E8%A6%81%E5%86%85%E5%AE%B9)