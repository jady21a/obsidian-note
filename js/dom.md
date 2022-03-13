### JavaScript的组成

JavaScript基础分为三个部分：

-   ECMAScript：JavaScript的语法标准。包括变量、表达式、运算符、函数、if语句、for语句等。
    
-   **DOM**：文档对象模型（Document object Model），操作**网页上的元素**的 API（ application programming interface）。比如让盒子移动、变色、轮播图等。
    
-   **BOM**：浏览器对象模型（Browser Object Model），操作**浏览器部分功能**的API。比如让浏览器自动滚动。
    

### 节点
构成 HTML 网页的最基本单元。网页中的每一个部分都可以称为是一个节点，比如：html标签、属性、文本、注释、整个文档等都是一个节点。
-   文档节点（文档）：整个 HTML 文档。整个 HTML 文档就是一个文档节点。
    
-   元素节点（标签）：HTML标签。
    
-   属性节点（属性）：元素的属性。
    
-   文本节点（文本）：HTML标签中的文本内容（包括标签之间的空格、换行）。
    
节点的类型不同，属性和方法也都不尽相同。所有的节点都是 Object。

![[Pasted image 20220311121310.png]]

### DOM 可以做什么
-   找对象（元素节点）、设置元素的属性值、设置元素的样式、动态创建和删除元素、事件的触发响应：事件源、事件、事件的驱动程序

##   元素节点的获取
```
var div1 = document.getElementById("box1"); //方式一：通过 id 获取 一个 元素节点（为什么是一个呢？因为 id 是唯一的）

var arr1 = document.getElementsByTagName("div"); //方式二：通过 标签名 获取 元素节点数组，所以有s

var arr2 = document.getElementsByClassName("hehe"); //方式三：通过 类名 获取 元素节点数组，所以有s


document.getElementsByTagName("div1")[0];    //取数组中的第一个元素

document.getElementsByClassName("hehe")[0];  //取数组中的第一个元素
```

###   获取父节点
```
节点.parentNode
```

###  获取兄弟节点
nextSibling：下一个节点（包括标签、空文档和换行节点）
nextElementSibling：下一个元素节点（标签）
previousSibling 、previousElementSibling
获得任意一个兄弟节点：
```
节点自己.parentNode.children[index];  //随意得到兄弟节点
```
### 子节点
firstChild、lastChild
firstElementChild、lastElementChild
### 获取所有的子节点
**childNodes**：标准属性。返回的是指定元素的**子节点**的集合（包括元素节点、所有属性、文本节点）
```
子节点数组 = 父节点.childNodes;   //获取所有节点。
```
**children**：非标准属性。返回的是指定元素的**子元素节点**的集合。【重要】

-   它只返回 HTML 节点，甚至不返回文本节点。
```
	子节点数组 = 父节点.children;   //获取所有节点。用的最多。
```
## DOM 节点的操作（重要）
节点的**访问关系**都是**属性**，节点的**操作**都是**函数**（方法）
### 创建节点
```
var a1 = document.createElement("li");   //创建一个li标签
var a2 = document.createElement("adbc");   //创建一个不存在的标签
```

###  插入节点
```
	父节点.appendChild(新的子节点);
```
父节点的最后插入一个新的子节点。
```
	父节点.insertBefore(新的子节点,作为参考的子节点)
```
-   在参考节点前插入一个新的节点。
-   如果参考节点为 null，那么他将在父节点里面的最后插入一个子节点。

###   删除节点
```
父节点.removeChild(子节点);
```
**用父节点删除子节点**

```
node1.parentNode.removeChild(node1);
```
删除自己这个节点

### 复制节点（克隆节点）
```
	要复制的节点.cloneNode();       //括号里不带参数和带参数false，效果是一样的。

	要复制的节点.cloneNode(true);
```
-   不带参数/带参数false：只复制节点本身，不复制子节点。
    
-   带参数 true：既复制节点本身，也复制其所有的子节点。

##   设置节点的属性
```
<img src="images/1.jpg" class="image-box" title="美女图片" alt="地铁一瞥" id="a1">
```
### 获取节点的属性值
1、
```
	元素节点.属性名;
	元素节点[属性名];
```

```
    console.log(myNode["src"]);
    console.log(myNode["className"]); //注意，是className，不是class
    console.log(myNode["title"]);
```
2、
```
	元素节点.getAttribute("属性名称");
```

```
    console.log(myNode.getAttribute("src"));
    console.log(myNode.getAttribute("class"));   //注意是class，不是className
    console.log(myNode.getAttribute("title"));
```
前者是直接操作标签，后者是把标签作为 DOM 节点。推荐方式 2。

### 设置节点的属性值
1、
```
    myNode.src = "images/2.jpg"   //修改src的属性值
    myNode.className = "image2-box";  //修改class的name
```
2、
```
	元素节点.setAttribute("属性名", "新的属性值");
eg：
    myNode.setAttribute("src","images/3.jpg");
    myNode.setAttribute("class","image3-box");
    myNode.setAttribute("id","你好");
```

### 删除节点的属性
```
元素节点.removeAttribute(属性名);
```

### innerHTML和innerText的区别

-   value：标签的value属性。
    
-   **innerHTML**：双闭合标签里面的内容（包含标签）。
    
-   **innerText**：双闭合标签里面的内容（不包含标签）。
![[Pasted image 20220311125151.png]]


### nodeType、nodeName、nodeValue


skim35-38
