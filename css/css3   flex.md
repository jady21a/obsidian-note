### Flex 布局的优势
1、**flex 布局的子元素不会脱离文档流**，很好地遵从了“流的特性”。
2、**flex 是一种现代的布局方式，是 W3C 第一次提供真正用于布局的 CSS 规范**。 Flex 非常提供了丰富的属性，非常灵活，让布局的实现更佳多样化，且方便易用。

## 概念
-   **弹性盒子**：指的是使用 `display:flex` 或 `display:inline-flex` 声明的**父容器**。
    
-   **子元素/弹性元素**：指的是父容器里面的子元素们（父容器被声明为 flex 盒子的情况下）。

-   主轴：flex容器的主轴，默认是水平方向，从左向右。
    
-   侧轴：与主轴垂直的轴称作侧轴，默认是垂直方向，从上往下。

###   flex-direction 属性
`flex-direction` ：用于设置盒子中**子元素**的排列方向。属性值可以是：
Row：从左到右水平排列子元素（默认值）
Column：从上到下垂直排列子元素
Row-reverse：从右向左排列子元素
Column-reverse：从下到上垂直排列子元素

### flex-wrap 属性
`flex-wrap` ：控制子元素溢出时的换行处理。

### justify-content 属性
`justify-content` ：控制子元素在主轴上的排列方式。

## 弹性元素

###  justify-content 属性

### `flex` 属性：设置子盒子的权重