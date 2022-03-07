### html 的常见元素
1. head 区域的 html 元素（head 区域的 html 元素，不会在页面（网页）上留下直接的内容。）
Meta title style link script base  
[12-HTML基础回顾 | 千古前端图文教程 (qianguyihao.com)](https://web.qianguyihao.com/01-HTML/12-HTML%E5%9F%BA%E7%A1%80%E5%9B%9E%E9%A1%BE.html#_1%E3%80%81head-%E5%8C%BA%E5%9F%9F%E7%9A%84-html-%E5%85%83%E7%B4%A0)
2. Body 区域（body 区域的 html 元素，会直接出现在页面上。）
-   div、section、article、aside、header、footer
-   p
-   span、em、strong
-   表格元素：table、thead、tbody、tr、td
-   列表元素：ul、ol、dl、dt、dd
-   a  
-   表单元素：form、input、select、textarea、button

**常见标签的重要属性**：
-   a[href,target]
-   img[src,alt]
-   table td[colspan,rowspan]。设置当前单元格占据几行几列。在合并单元格时，会用到。
-   form[target,method,enctype]
-   input[type,value]
-   button[type]
-   selection>option[value]
-   label[for]


###   html 元素的分类
块级元素、行内元素、   inline-block：比如 `form` 表单元素。对外的表现是行内元素（不会独占一行），对内的表现是块级元素（可以设置宽高）。  
    
###   html 元素的嵌套关系
-   块级元素可以包含行内元素。
    
-   块级元素**不一定**能包含块级元素。比如 div 中可以包含 div，但 p 标签中不能包含 div。
    
-   行内元素**一般**不能包含块级元素。比如 span 中不能包含 div。但有个特例：在 HTML5 中， a 标签中可以包含 div。
    

**注意**：在 HTML5 中 `a > div` 是合法的， `div > a > div`是不合法的 。
    
###   html 元素的默认样式和 CSS Reset
Reset 方案
1. Normalize.css：   https://necolas.github.io/normalize.css/
2. Css tools：[https://meyerweb.com/eric/tools/css/reset/](https://meyerweb.com/eric/tools/css/reset/)
3.
*{
    margin: 0;
    padding: 0;
}
比较简洁，但可能会导致 css 选择器的性能问题。

  
  ### html 常见面试题
  **HTML5 有什么新的变化**
-   新的语义化元素  header footer nav
-   表单增强  email tel
-   新的 API：离线、音视频、图形、实时通信、本地存储、设备能力等。

 **自闭合元素 （包含单标签**）
 Input  img  br hr  meta link

 ** form 表单的作用**

-   直接提交表单
    
-   使用 submit / reset 按钮
    
-   便于浏览器保存表单
    
-   第三方库（比如 jQuery）可以整体获取值
    
-   第三方库可以进行表单验证
    

所以，如果我们是通过 Ajax 提交表单数据，也建议加上 form。