Css 选择器
```
    div 标签选择器

     .box 类名选择器

     #box　id选择器

     div p 后代选择器

     div.box 交集选择器

     div,p,span 并集选择器

     div>p 子代选择器

     * : 通配符

     div+p: 选中div后面相邻的第一个p

     div~p: 选中的div后面所有的p
```

## Css3 选择器
###  属性选择器   skim
属性选择器的标志性符号是 `[]`
```
^：开头  $：结尾  *：包含
```
-   `E[title]` 选中页面的E元素，并且E存在 title 属性即可。
    
-   `E[title="abc"]`选中页面的E元素，并且E需要带有title属性，且属性值**完全等于**abc。
    
-   `E[attr~=val]` 选择具有 att 属性且属性值为：用空格分隔的字词列表，其中一个等于 val 的E元素。
    
-   `E[attr|=val]` 表示要么是一个单独的属性值，要么这个属性值是以“-”分隔的。
    
-   `E[title^="abc"]` 选中页面的E元素，并且E需要带有 title 属性,属性值以 abc 开头。
    
-   `E[title$="abc"]` 选中页面的E元素，并且E需要带有 title 属性,属性值以 abc 结尾。
    
-   `E[title*="abc"]` 选中页面的 E 元素，并且 E 需要带有 title 属性, 属性值任意位置包含 abc。


### 结构伪类选择器 skim
伪类选择器的标志性符号是 `:`。
-   `E:first-child` 匹配父元素的第一个子元素E。
    
-   `E:last-child` 匹配父元素的最后一个子元素E。
    
-   `E:nth-child(n)` 匹配父元素的第n个子元素E。**注意**，盒子的编号是从`1`开始算起，不是从`0`开始算起。
    
-   `E:nth-child(odd)` 匹配奇数
    
-   `E:nth-child(even)` 匹配偶数
    
-   `E:nth-last-child(n)` 匹配父元素的倒数第 n 个子元素 E。
https://web.qianguyihao.com/02-CSS%E5%9F%BA%E7%A1%80/10-CSS3%E9%80%89%E6%8B%A9%E5%99%A8%E8%AF%A6%E8%A7%A3.html#%E7%BB%93%E6%9E%84%E4%BC%AA%E7%B1%BB%E9%80%89%E6%8B%A9%E5%99%A8

###   伪元素选择器  skim
伪元素选择器的标志性符号是 `::`。
-   `E::before` 设置在 元素E 前面（依据对象树的逻辑结构）的内容，配合content属性一起使用。
    
-   `E::after` 设置在 元素E 后面（依据对象树的逻辑结构）的内容，配合content属性一起使用。
    

`E:after`、`E:before`在旧版本里是伪类，在 CSS3 这个新版本里是伪元素。新版本里，`E:after`、`E:before`会被自动识别为`E::after`、`E::before`，按伪元素来对待，这样做的目的是用来做兼容处理。