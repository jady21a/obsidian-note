CSS：Cascading Style Sheet，层叠样式表
Css 注释：CSS 只有 `/* */` 这种注释，没有 `//` 这种注释。而且注释要写在 `<style>` 标签里面才算生效。
属性：

| color            | 字体颜色 | color：red；            |
| ---------------- | -------- | ----------------------- |
| font-size        | 字号大小 | font-size：40px;        |
| background-color | 颜色     | background-color: blue; |
| font-weight      | 加粗     | bold、normal            |
| font-style       | 斜体     | italic、normal          |
| text-decoration  | 下划线   | underline、none         |

##### CSS 和 HTML 的结合方式有 3 种：
-   **行内样式**：在某个特定的标签里采用 style**属性**。范围只针对此标签，适合局部修改。
```
<p style="color:white;background-color:red">我不会就这样轻易的狗带</p>
```
-   **内嵌样式表**：在页面的 head 里采用`<style>`**标签**。范围针对此页面。
-   **引入外部样式表 css 文件**的方式。这种引入方式又分为两种：
 1、采用 `<link>` 标签。例如：`<link rel = "stylesheet" type = "text/css" href = "a.css"></link>` 
 2、采用 import，必须写在 `<style>` 标签中，并且必须是第一句。例如：`@import url(a.css) ;`

 ## 选择器
 指定 CSS 要作用的标签，那个标签的名称就是选择器。意为：选择哪个容器。分为两大类：基本选择题和扩展选择器。
#### 基本选择器
- a、  标签选择器：针对**一类**标签
所有的标签，都可以是选择器。比如 ul、li、label、dt、dl、input。

-  b、 ID 选择器：id 前加#，针对某**一个**特定的标签，只能使用一次
```
#mytitle{ border:3px dashed green; }
```
Id 命名：
   （1）只能有字母、数字、下划线。
   （2）必须以字母开头。
   （3）不能和标签同名。比如 id 不能叫做 body、img、a。

- c、类选择器：类名前加.  、针对相同类名的标签使用

```
<h3 class="teshu  zhongyao">我是一个h3啊</h3>  //该标签有两个类名
```
**类上样式，id 上行为**。
### class和id的区别

class用于css的，id用于js的。

1）class 页面上可以重复。id 页面上唯一，不能重复。 2）一个标签可以有多个 class，用空格隔开。但是 id 只能有 id

- d、通用选择器（通配符*）：针对所有的标签都适用。IE 有些版本不支持，大网站增加客户端负担。效率不高，如果页面上的标签越多，效率越低（不建议使用）

#### 扩展（高级）选择器
- a   后代选择器：用空格隔开
```
<style type="text/css">
    .div1 p {
        color: red;
    }
</style>
```
- b  交集选择器：选择器之间紧密相连
https://web.qianguyihao.com/02-CSS%E5%9F%BA%E7%A1%80/03-CSS%E6%A0%B7%E5%BC%8F%E8%A1%A8%E5%92%8C%E9%80%89%E6%8B%A9%E5%99%A8.html#_2%E3%80%81%E4%BA%A4%E9%9B%86%E9%80%89%E6%8B%A9%E5%99%A8%EF%BC%9A%E5%AE%9A%E4%B9%89%E7%9A%84%E6%97%B6%E5%80%99%E7%B4%A7%E5%AF%86%E7%9B%B8%E8%BF%9E
- c  并集选择器（分组选择器）：用逗号隔开
- d 子代选择器
```
div > p {
    color: red;
}
```
- e 序选择器
ul li: first-child 、ul li: last-child 
- f 下一个兄弟选择器
```
<style type="text/css">
    h3 + p {
        color: red;
    }
</style>
```
选择的是 h3 元素后面紧挨着的第一个兄弟。
- d  伪类选择器
1. 静态伪类：只能用于超链接的样式
   `:link` 超链接点击之前
   `:visited` 链接被访问过之后
2. 动态伪类：适用所有标签的样式
   `:hover` “悬停”：鼠标放到标签上的时候
   `:active` “激活”： 鼠标点击标签，但是不松手时。
   `:focus` 是某个标签获得焦点时的样式（比如某个输入框获得焦点）
  
   **a 的伪类：link visited hover active**

   兼容性
   Ie6：
```
p
#box
.spec
div p
div.spec
div,p
*
```
Ie7
```
div>p
h3+p
```
Ie8（win7）：
```
ul li:first-child
ul li:last-child
```