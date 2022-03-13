JavaScript 基础分为三个部分：
- js 语法标准：包括变量、表达式、运算符、函数、if 语句、for 语句等。
- DOM：文档对象模型（Document object Model），操作 **网页上的元素**的 API。比如让盒子移动、变色、轮播图等。
-  **BOM**：浏览器对象模型（Browser Object Model），操作 **浏览器部分功能**的 API。比如让浏览器自动滚动。

## 常见的 BOM 对象有：
-   Window：代表整个浏览器的窗口，同时 window 也是网页中的全局对象。
    
-   Navigator：代表当前浏览器的信息，通过该对象可以识别不同的浏览器。
    
-   Location：代表当前浏览器的地址栏信息，通过 Location 可以获取地址栏信息，或者操作浏览器跳转页面。
    由于历史原因，Navigator 对象中的大部分属性都已经不能帮助我们识别浏览器了。**一般我们只会使用 `navigator.userAgent` 来获取浏览器的信息**。
属性：
```
console.log(location.href); // 获取当前页面的url 路径
location.href = 'www.baidu.com'; // 跳转到指定的页面链接。通俗理解就是：跳转到其他的页面
```
方法：
1、
```
    location.assign(str);//用来跳转到其他的页面，作用和直接修改 `location.href` 一样。
```
2、
```
 location.reload();//重新加载当前页面，作用和刷新按钮一样
```
3、
```
   location.replace();//使用一个新的页面替换当前页面，调用完毕也会跳转页面。但不会生成历史记录，不能使用「后退按钮」后退。
```

-   History：代表浏览器的历史记录，通过该对象可以操作浏览器的历史记录。由于隐私原因，该对象不能获取到具体的历史记录，只能操作浏览器向前或向后翻页，而且该操作只在当次访问时有效。
```
history.back();
history.forward();
```
-   Screen：代表用户的屏幕信息，通过该对象可以获取用户的显示器的相关信息。

## 定时器的常见方法
-   setInterval ()：循环调用。将一段代码，**每隔一段时间**执行一次。（循环执行）
每间隔一秒，将数字加 1：
1、
```
    let num = 1;
   setInterval(function () {
       num ++;
       console.log(num);
   }, 1000);
```
2、
```
    setInterval(fn,1000);

    function fn() {
       num ++;
       console.log(num);
    }
```


-   setTimeout ()：延时调用。将一段代码，等待一段时间之后**再执行**。（只执行一次）


###   清除定时器
定时器的返回值是作为这个定时器的**唯一标识**，可以用来清除定时器。具体方法是：假设定时器 setInterval () 的返回值是 `参数1`，那么 `clearInterval(参数1)` 就可以清除定时器。
1、
```
<script>
    let num = 1;

    const timer = setInterval(function () {
        console.log(num);  //每间隔一秒，打印一次num的值
        num ++;
        if(num === 5) {  //打印四次之后，就清除定时器
            clearInterval(timer);
        }

    }, 1000);
</script>
```
2、
```
    <script>
        window.onload = function () {
            //获取相关元素
            var imgArr = document.getElementsByTagName("img");
            //设置定时器：5秒后关闭两侧的广告栏
            setTimeout(fn,5000);
            function fn(){
                imgArr[0].style.display = "none";
                imgArr[1].style.display = "none";
            }
        }
    </script>
```
