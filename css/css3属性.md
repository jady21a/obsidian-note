main：文本、盒模型中的 box-sizing 属性、处理兼容性问题：私有前缀、边框、背景属性、渐变
## 文本
### Text-shadow：设置文本的阴影
```
	text-shadow: 20px 27px 22px pink;
```
参数解释：水平位移、垂直位移、模糊程度、阴影颜色。
## 盒模型中的 box-sizing 属性
CSS3 对盒模型做出了新的定义，即允许开发人员**指定盒子宽度和高度的计算方式**。
```
box-sizing: content-box;
```
此时设置的 width 和 height 是**内容区域**的宽高。`盒子的实际宽度 = 设置的 width + padding + border`。此时改变 padding 和 border 的大小，也不会改变内容的宽高，而是盒子的总宽高发生变化。

```
box-sizing: border-box;
```
此时设置的 width 和 height 是**盒子**的总宽高。`盒子的实际宽度 = 设置的 width`。此时改变 padding 和 border 的大小，会改变内容的宽高，盒子的总宽高不变

## 边框
###   边框圆角：`border-radius` 属性
```
	border-radius: 60px/120px;             //参数：水平半径/垂直半径

	border-radius: 20px 60px 100px 140px;  //从左上开始，顺时针赋值。如果当前角没有值，取对角的值

	border-radius: 20px 60px;
```
![[Pasted image 20220308191612.png]]

### 边框阴影：`box-shadow` 属性
```
	box-shadow: 水平偏移 垂直偏移 模糊程度（不能为负值） 阴影大小 阴影颜色

	box-shadow: 15px 21px 48px -2px #666;
```
![[Pasted image 20220308192036.png]]