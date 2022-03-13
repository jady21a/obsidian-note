类名命名时写法
```
<h3 class="teshu  zhongyao">我是一个h3啊</h3>  //该标签有两个类名
```
伪类选择时写法
```
.nav ul li a:link , .nav ul li a:visited{
			text-decoration: none;
			background-color: purple;
			color:white;
		}
```

# 居中
### 行内元素水平居中
```
 text-align: center;
```
单行文本垂直居中。让**文字的行高** 等于 **盒子的高度**
```
    .father {
        height: 20px;
        line-height: 20px;
    }
```
## 块级元素水平垂直居中
如果它是一个行内元素，就对它的父容器应用 `text-align: center`；如果它是一个块级元素，就对它自身应用 `margin: auto` 或者 `margin: 0 auto`。
`margin: 0 auto` 相当于 `margin: 0 auto 0 auto`，四个值分别对应上右下左。其计算值取决于**剩余空间**。
```
<body>
    <div class="father">
        <div class="son"></div>
    </div>
    <script></script>
</body>
```

父元素和子元素都是定宽高的，在这种情况下，给子元素设置 `margin: auto`，子元素依然不能垂直居中。

### 1.绝对定位 + translate（无需指定子元素的宽高，推荐）
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        * {
            margin: 0;
            padding: 0;
        }
        .father{
            position: relative;
            min-height: 500px;
            background: pink;
        }
        .son {
            position: absolute;
            background: red;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
        }
    </style>
</head>
<body>
    <div class="father">
        <div class="son">子元素的内容</div>
    </div>
    <script></script>
</body>
</html>
```

### 2、flex 布局（待改进）
将父容器设置为 Flex 布局，再给父容器加个属性`justify-content: center`，这样的话，子元素就能水平居中了；再给父容器加个属性 `align-items: center`，这样的话，子元素就能垂直居中了。
不足之处在于：给父容器设置属性`justify-content: center`和`align-items: center`之后，导致父容器里的所有子元素们都垂直居中了（如果父容器里有多个子元素的话

### 3、flex 布局 + margin: auto（推荐）
先给父容器设置 `display: flex`，再给指定的子元素设置我们再熟悉不过的 `margin: auto`，即可让这个指定的子元素在**剩余空间**里，水平垂直居中。