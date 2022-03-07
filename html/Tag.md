### 排版 tag
-   `<h1>`   `<p>`  `<hr />`   `<br />`  `<div>`   `<span>`    

HTML 注释：

```
<!-- 我是 html 注释  -->
```
-   **文本级标签**：p、span、a、b、i、u、em。文本级标签里只能放**文字、图片、表单元素**。（a 标签里不能放 a 和 input）
    
-   **容器级标签**：div、h 系列、li、dt、dd。容器级标签里可以放置任何东西。


| tag     | comment                                                              | 属性                                                                     |
| ------- | -------------------------------------------------------------------- | ------------------------------------------------------------------------ |
| <h 1-6> | 1-6 （大-小）                                                        | align： left、center、right                                              |
| p       | paragraph                                                            | align： left、center、right                                              |
| hr /    | horizontal                                                           | align="属性值"     size="2"   width="500"     color="#0000FF"    noshade |
| br /    | 换行                                                                 |                                                                          |
| div     | division “分割，分配” ，把标签中的内容分割为独立的区块。必须单独占据一行。 | align="属性值"                                                           |
| span    | 范围、跨度，和 div 的作用一致，但不换行。                             |                                                                          |
|         |                                                                      |                                                                          |


#### div 和 span 的区别

`<span>` 和 `<div>` 唯一的区别在于：`<span>` 是不换行的，而 `<div>` 是换行的。

div 在浏览器中，默认是不会增加任何的效果的，但是语义变了，div 中的所有元素是一个小区域。 div 标签是一个**容器级**标签，里面什么都能放，甚至可以放 div 自己。

span 也是表达 “小区域、小跨度” 的标签，但只是一个**文本级**的标签。就是说，span 里面只能放置 a（链接）、文字、图片、表单元素。 span 里面不能放 p、h、ul、dl、ol、div。


- ### 字体 tag
字体标签：  `<b>` 加粗、 `<u>` 下划线、 `<sup>` 下标、`<sub>`  上标（eg：平方）、   `<i>` 或 `<em>` ：斜体标记

#### 超链接 `<a>`  anchor “锚”
###### 1、外部链接：a href（a 是文本级 标签）
```
<a href="http://www.baidu.com" target="_blank">点我点我</a>
```
<a href="02页面.html"> 点击进入另外一个文件</a>
```
```
###### 2、锚链接 
用 `name` 属性或者 `id` 属性给那个特定的位置起个名字，**在本页面或者其他页面的的不同位置进行跳转**  #

![[Pasted image 20220306002534.png]]
##### 3、邮件链接
```
<a href="mailto:xxx@163.com">点击进入我的邮箱</a>
```
###### 超链接的属性

-   `href`：目标 URL
-   `title`：悬停文本。
-   `name`：主要用于设置一个锚点的名称。
-   `target`：告诉浏览器用什么方式来打开目标页面。`target` 属性有以下几个值：
    -   `_self`：在同一个网页中显示（默认值）
    -   `_blank`：**在新的窗口中打开**。
    -   `_parent`：在父窗口中显示
    -   `_top` ：在顶级窗口中显示

	
转义字符
![[Pasted image 20220305230546.png]]

- ### 图片 tag
img：image
```
<img src="图片的URL" />
```
不能往网页中插入的图片格式是：psd、ai 
src： source

###### 相对路径
```
<!-- 当前目录中的图片 -->
<img src="2.jpg">
<img src="./2.jpg">

<!-- 上一级目录中的图片 -->
<img src="../2.jpg">
```
##### 绝对路径
```
<img src="C:\Users\qianguyihao\Desktop\html\images\1.jpg">  //工程用处不大，linux没有盘符
```
```
<img src="http://img.smyhvae.com/20200122_200901.png">
```
###### 属性
align ：bottom（默认）、center、top、left、right。

###  列表 tag
-   列表标签：
- `<ul>`    ul：unordered list， li：list item，// ul 的儿子，只能是 li，li 不能单独存在，须包裹在 ul 里面，但是 li 是一个容器级标签，**li 里面什么都能放，甚至可以再放一个 ul**。
Type="属性值"， `disc` (实心原点，默认)，`square` (实心方点)，`circle` (空心圆)
 -  `<ol>` `type="属性值"`。属性值可以是：1 (阿拉伯数字，默认)、a、A、i、I。结合 `start` 属性表示 `从几开始`
 ![[Pasted image 20220306015254.png]]
- `<dl>` 定义列表  definition list  ，dl 的子元素只能是 dt 和 dd ，没有属性
  `<dt>`：definition title 列表的标题，这个标签是必须的
  `<dd>` ：definition description 列表的列表项，如果不需要它，可以不加
 （1）是一个列表，列出了几个 dd 项目
 （2）每一个词儿都有自己的描述项。
-   表格标签：`<table>`
 `<tr>` ：table row  表行   td : table description
  属性：border width height bordercolor align（left right center）bgcolor   //tbc

单元格合并





  
![[Pasted image 20220306020728.png]]
-   框架标签及内嵌框架 `<iframe>`
-   表单标签：`<form>`
-   多媒体标签
-   滚动字幕标签：`<marquee>`      