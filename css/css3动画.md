## 过渡：transition
```
	transition: 让哪些属性进行过度 过渡的持续时间 运动曲线 延迟时间;

	transition: all 3s linear 0s;
```
-   `transition-property: all;` 如果希望所有的属性都发生过渡，就使用all。
    
-   `transition-duration: 1s;` 过渡的持续时间。
    
-   `transition-timing-function: linear;` 运动曲线。属性值可以是：
    
    -   `linear` 线性
    -   `ease` 减速
    -   `ease-in` 加速
    -   `ease-out` 减速
    -   `ease-in-out` 先加速后减速
-   `transition-delay: 1s;` 过渡延迟。多长时间后再执行这个过渡动画。

##   2D 转换
###   1、缩放：`scale`
```
	transform: scale(x, y);

	transform: scale(2, 0.5);
```
###   2、位移：translate
```
	transform: translate(水平位移, 垂直位移);

	transform: translate(-50%, -50%);
```
-   参数为百分比，相对于自身移动。
    
-   正值：向右和向下。负值：向左和向上。如果只写一个值，则表示水平移动。

#### N：居中
1、如果想让一个**标准流中的盒子在父亲里居中**（水平方向看），可以将其设置 `margin: 0 auto` 属性。

2、可如果盒子是绝对定位的，此时已经脱标了，如果还想让其居中（位于父亲的正中间），可以这样做：
```
	div {
		width: 600px;
		height: 60px;
		position: absolute;  绝对定位的盒子
		left: 50%;           首先，让左边线居中
		top: 0;
		margin-left: -300px;  然后，向左移动宽度（600px）的一半
	}
```
3、利用偏移 translate 来做，这也是比较推荐的写法：
```css
div {
	    width: 600px;
	    height: 60px;
	    background-color: red;
	    position: absolute;       绝对定位的盒子
	    left: 50%;               首先，让左边线居中
	    top: 0;
	    transform: translate(-50%);    然后，利用translate，往左走自己宽度的一半【推荐写法】
	}
```

###   3、旋转：rotate
```
	transform: rotate(角度);

	transform: rotate(45deg);
```

### 3D 转换
### 1、旋转：rotateX、rotateY、rotateZ

**3D 坐标系（左手坐标系）**
![[Pasted image 20220308193705.png]]

###   2、移动：translateX、translateY、translateZ
```
transform: translateX(100px);    //沿着 X 轴移动
```

### 3、透视：perspective
```
perspective: 500px;
```
### 4、3D 呈现（transform-style）
```
	transform-style: preserve-3d;     /* 让 子盒子 位于三维空间里 */

	transform-style: flat;   
```

## 动画
### 1、定义动画的步骤

（1）通过@keyframes定义动画；

（2）将这段动画通过百分比，分割成多个节点；然后各节点中分别定义各属性；

（3）在指定元素里，通过 `animation` 属性调用动画。

之前,我们在 js 中定义一个函数的时候，是先定义，再调用：
```
    js 定义函数：
        function fun(){ 函数体 }

     调用：
     	fun();
```
我们在 CSS3 中**定义动画**的时候，也是**先定义，再调用**：
```
    定义动画：
        @keyframes 动画名{
            from{ 初始状态 }
            to{ 结束状态 }
        }

     调用：
      animation: 动画名称 持续时间；
```
Animation 属性的格式如下
```
            animation: 定义的动画名称 持续时间  执行次数  是否反向  运动曲线 延迟执行。(infinite 表示无限次)

            animation: move1 1s  alternate linear 3;

            animation: move2 4s;
```
https://web.qianguyihao.com/02-CSS%E5%9F%BA%E7%A1%80/12-CSS3%E5%B1%9E%E6%80%A7%E8%AF%A6%E8%A7%A3%EF%BC%9A%E5%8A%A8%E7%94%BB%E8%AF%A6%E8%A7%A3.html#_1%E3%80%81%E5%AE%9A%E4%B9%89%E5%8A%A8%E7%94%BB%E7%9A%84%E6%AD%A5%E9%AA%A4

### 2、动画属性 skim
```
        animation: 定义的动画名称  持续时间  执行次数  是否反向  运动曲线 延迟执行。(infinite 表示无限次)

            animation: move1 1s  alternate linear 3;

            animation: move2 4s;
```

```
animation-name: move;
```

```
	animation-duration: 4s;
```

```
	animation-iteration-count: 1;
```

```
	animation-direction: alternate;
```

```
	animation-delay: 1s;
```

```
	animation-fill-mode: forwards;
```