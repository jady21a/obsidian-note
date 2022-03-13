绑定：
1、onclick
```
   element.onclick = function () {

    }
```
2、 addEventListener
```
    element.addEventListener('click', function () {

    }, false);
```
-   参数 1：事件名的字符串 (注意，没有 on)
    
-   参数 2：回调函数：当事件触发时，该函数会被执行
    
-   参数 3：**true 表示捕获阶段触发，false 表示冒泡阶段触发（默认）**。如果不写，则默认为 false。【重要】

3、 attachEvent
```
    element.attachEvent('onclick', function () {

    });
```
-   attachEvent () 中的 this，是 window
-   addEventListener () 中的 this，是绑定事件的对象。

### 事件对象 event
当事件的响应函数被触发时，会产生一个事件对象 `event`。浏览器每次都会将这个事件 `event` 作为实参传进之前的响应函数。
![[Pasted image 20220312135822.png]]

##### 举例 1：使 div 跟随鼠标移动
##### 举例 2：获取鼠标距离所在盒子的距离
##### 举例 3：商品放大镜

## DOM 事件流

事件传播的三个阶段是：事件捕获、事件冒泡和目标。

-   事件捕获阶段：事件从祖先元素往子元素查找（DOM 树结构），直到捕获到事件目标 target。在这个过程中，默认情况下，事件相应的监听函数是不会被触发的。
```
    box1.addEventListener("click", function () {
        alert("捕获 box3");
    }, true);//参数为 true，代表事件在捕获阶段执行。
```
    
-   事件目标：当到达目标元素之后，执行目标元素该事件相应的处理函数。如果没有绑定监听函数，那就不执行。
    
-   事件冒泡阶段：事件从事件目标 target 开始，从子元素往冒泡祖先元素冒泡，直到页面的最上一级标签。 （**子元素的事件被触发时，父元素的同样的事件也会被触发**。）
以下事件不冒泡：blur、focus、load、unload、onmouseenter、onmouseleave
```
event.bubbles  //检查一个元素是否会冒泡，
```

![[Pasted image 20220312140340.png]]

## 阻止冒泡
```
  event.stopPropagation();   //w3c
```

```
event.cancelBubble = true  //ie10 以下
```

## 事件委托
事件委托，通俗地来讲，就是把一个元素响应事件（click、keydown......）的函数委托到另一个元素。
绑定函数过多会消耗内存和性能。**我们希望，只绑定一次事件，即可应用到多个元素上**，即使元素是后来添加的。因此，比较好的方法就是把这个点击事件绑定到他的父层上，如为父节点注册 click 事件，当子节点被点击的时候，click 事件会从子节点开始**向父节点冒泡**。
事件委托是利用了冒泡机制，减少了事件绑定的次数，减少内存消耗，提高性能。

# 键盘事件
## 鼠标的拖拽事件

拖拽的流程：

（1）`onmousedown`：当鼠标在被拖拽元素上按下时，开始拖拽；

（2）`onmousemove`：当鼠标移动时被拖拽元素跟随鼠标移动；

（3）`onmouseup` ：当鼠标松开时，被拖拽元素固定在当前位置。
## 鼠标的滚轮事件

`onmousewheel`：鼠标滚轮滚动的事件，会在滚轮滚动时触发。但是火狐不支持该属性。

`DOMMouseScroll` ：在火狐中需要使用 DOMMouseScroll 来绑定滚动事件。注意该事件需要通过 addEventListener () 函数来绑定。

### 键盘事件

`onkeydown`：按键被按下。

`onkeyup`：按键被松开。