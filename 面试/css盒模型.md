## 谈一谈你对 CSS 盒模型的认识
（1）基本概念：content、padding、margin。

（2）标准盒模型、IE 盒模型的区别。不要漏说了 IE 盒模型，通过这个问题，可以筛选一部分人。

（3）CSS 如何设置这两种模型（即：如何设置某个盒子为其中一个模型）？如果回答了上面的第二条，还会继续追问这一条。

（4）JS 如何设置、获取盒模型对应的宽和高？这一步，已经有很多人答不上来了。

（5）实例题：根据盒模型解释**边距重叠**。

前四个方面是逐渐递增，第五个方面，却鲜有人知。

（6）BFC（边距重叠解决方案）或 IFC。

## 标准盒模型和 IE 盒子模型
![[Pasted image 20220313012703.png]]

![[Pasted image 20220313012712.png]]

##   CSS 如何设置这两种模型
```
   /* 设置当前盒子为 标准盒模型（默认） */
    box-sizing: content-box;

    /* 设置当前盒子为 IE盒模型 */
    box-sizing: border-box;
```

## [#](https://web.qianguyihao.com/15-%E5%89%8D%E7%AB%AF%E9%9D%A2%E8%AF%95/02-CSS%E7%9B%92%E6%A8%A1%E5%9E%8B%E5%8F%8ABFC.html#js%E5%A6%82%E4%BD%95%E8%AE%BE%E7%BD%AE%E3%80%81%E8%8E%B7%E5%8F%96%E7%9B%92%E6%A8%A1%E5%9E%8B%E5%AF%B9%E5%BA%94%E7%9A%84%E5%AE%BD%E5%92%8C%E9%AB%98)JS 如何设置、获取盒模型对应的宽和高

### [#](https://web.qianguyihao.com/15-%E5%89%8D%E7%AB%AF%E9%9D%A2%E8%AF%95/02-CSS%E7%9B%92%E6%A8%A1%E5%9E%8B%E5%8F%8ABFC.html#%E6%96%B9%E5%BC%8F%E4%B8%80%EF%BC%9A%E9%80%9A%E8%BF%87dom%E8%8A%82%E7%82%B9%E7%9A%84-style-%E6%A0%B7%E5%BC%8F%E8%8E%B7%E5%8F%96) 方式一：通过 DOM 节点的 style 样式获取
```
	element.style.width/height;
```
只能获取**行内样式**，不能获取 `内嵌` 的样式和 `外链` 的样式。
###   方式二（通用型）
```
    window.getComputedStyle(element).width/height;
```
###   方式三（IE 独有的）

```
	element.currentStyle.width/height;
```
### 方式四

```
	element.getBoundingClientRect().width/height;
```

##   margin 塌陷 /margin 重叠
**标准文档流中，竖直方向的 margin 不叠加，只取较大的值作为 margin**(水平方向的 margin 是可以叠加的，即水平方向没有塌陷现象)。如果不在标准流，比如盒子都浮动了，那么两个盒子之间是没有 margin 重叠的现象的。

**margin 这个属性，本质上描述的是兄弟和兄弟之间的距离； 最好不要用这个 marign 表达父子之间的距离。**

所以，如果要表达父子之间的距离，我们一定要善于使用父亲的 padding，而不是儿子的 margin。

## BFC（边距重叠解决方案） skim

### [#](https://web.qianguyihao.com/15-%E5%89%8D%E7%AB%AF%E9%9D%A2%E8%AF%95/02-CSS%E7%9B%92%E6%A8%A1%E5%9E%8B%E5%8F%8ABFC.html#bfc%E7%9A%84%E6%A6%82%E5%BF%B5)BFC 的概念

BFC（Block Formatting Context）：块级格式化上下文。