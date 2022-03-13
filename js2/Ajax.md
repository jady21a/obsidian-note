Ajax：Asynchronous Javascript And XML（异步 JavaScript 和 XML）
在浏览器中，我们可以在不刷新页面的情况下，通过 Ajax 的方式去获取一些新的内容。
发送 Ajax 请求的五个步骤：

（1）创建异步对象，即 XMLHttpRequest 对象。

（2）使用 open 方法设置请求参数。`open(method, url, async)`。参数解释：请求的方法、请求的 url、是否异步。第三个参数如果不写，则默认为 true。

（3）发送请求：`send()`。

（4）注册事件：注册 onreadystatechange 事件，状态改变时就会调用。

如果要在数据完整请求回来的时候才调用，我们需要手动写一些判断的逻辑。

（5）服务端响应，获取返回的数据。

发送请求的方法：
1、
```
open(method, url, async);
```
-   method：请求的类型；GET 或 POST
    
-   url：文件在服务器上的位置
    
-   async：true（异步）或 false（同步）
2、
```
send(string);//（仅用于 POST 请求）
```

get 请求：
```
//【发送ajax请求需要五步】
//（1）创建XMLHttpRequest对象
var xmlhttp = new XMLHttpRequest();

//（2）设置请求的参数。包括：请求的方法、请求的url。
xmlhttp.open('get', '02-ajax.php');

//（3）发送请求
xmlhttp.send();

//（4）注册事件。 onreadystatechange事件，状态改变时就会调用。
//如果要在数据完整请求回来的时候才调用，我们需要手动写一些判断的逻辑。
xmlhttp.onreadystatechange = function () {
    // 为了保证 数据 完整返回，我们一般会判断 两个值
    if (xmlhttp.readyState == 4 && xmlhttp.status == 200) {
        //（5）服务端相应：如果能够进入这个判断，说明数据请求成功了
        console.log('数据返回成功：' + JSON.stringify(xmlhttp.responseText));

        // 伪代码：按业务需要，将接口返回的内容显示在页面上
        // document.querySelector('h1').innerHTML = xmlhttp.responseText;
    }
};
```

post 请求：
```
//（1）异步对象
var xmlhttp = new XMLHttpRequest();

//（2）设置请求参数。包括：请求的方法、请求的url。
xmlhttp.open('post', '02.post.php');

// 如果想要使用post提交数据,必须添加此行
xmlhttp.setRequestHeader('Content-type', 'application/x-www-form-urlencoded');

//（3）发送请求
xmlhttp.send('name=fox&age=18');

//（4）注册事件
xmlhttp.onreadystatechange = function () {
    //（5）服务端相应
    if (xmlhttp.readyState == 4 && xmlhttp.status == 200) {
        alert(xmlhttp.responseText);
    }
};
```

###   JSON 的语法
语法规则：

-   数据在键值对中
    
-   数据由逗号分隔
    
-   花括号保存对象
    
-   方括号保存数组
    

数据类型：

-   数字（整数或浮点数）
    
-   字符串（在双引号中）
    
-   逻辑值（true 或 false）
    
-   数组（在方括号中）
    
-   对象（在花括号中）
    
-   null

```
// 对象
{
  "name":"fox",
  "age":"18",
  "sex":"true",
  "car":null
}

// 数组
[
  {
      "name":"小小胡",
      "age":"1"
  },
  {
      "name":"小二胡",
      "age":"2"
  }
]
```

JSON. parse ()：将 JSON 字符串转化为 js 对象
```
var jsObj = JSON.parse(ajax.responseText);
```

### ajax 请求解析 json（举例）
（1）Person. json:
```
{
    "name": "小强",
    "skill": "砍树",
    "friend": "老板"
}
```
（2）myJson. php：
```
<?php

	// 读取json文件 并返回即可
	echo  file_get_contents('info/Person.json');

 ?>
```
（3）getJson. html：
[03-Ajax传输json和XML | 千古前端图文教程 (qianguyihao.com)](https://web.qianguyihao.com/06-JavaScript%E5%9F%BA%E7%A1%80%EF%BC%9A%E5%BC%82%E6%AD%A5%E7%BC%96%E7%A8%8B/03-Ajax%E4%BC%A0%E8%BE%93json%E5%92%8CXML.html#ajax-%E8%AF%B7%E6%B1%82%E8%A7%A3%E6%9E%90-json%EF%BC%88%E4%B8%BE%E4%BE%8B%EF%BC%89)

### XML（Extensible Markup Language）：可扩展标记语言
```
<?xml version="1.0" encoding="UTF-8"?>//声明
```
自定义标签
```
<fox></fox>
<name></name>
```
**根节点**
```
<root1>
  <name></name>
</root1>
```

### ajax 请求解析 xml（举例）
（1）get_xml. php：（里面包含了 xml 文件）
```
<?php
	// 设置 返回的为 xml
	header('content-type:text/xml; charset= utf-8');

	// 读取xml文件 并返回
	echo file_get_contents('info/star.xml');

 ?>
```
（2）get_xml. html：（Ajax 请求，获取并解析 xml）
```
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8" />
        <title>Document</title>
    </head>
    <body>
        <input type="button" value="获取XMl数据" id="getXML" />
    </body>
</html>
<script type="text/javascript">
    document.querySelector('#getXML').onclick = function () {
        var ajax = new XMLHttpRequest();

        ajax.open('get', 'get_XMl.php');

        ajax.send();

        ajax.onreadystatechange = function () {
            if (ajax.readyState == 4 && ajax.status == 200) {
                // 如果 返回的是 xml文件
                console.log(ajax.responseText);

                // 异步 对象中 有另外一个属性 用来专门获取 xml
                // xml对象 在浏览器段 就是一个 document对象
                // 解析时 可以直接使用 querySelector 或者 getElementById等等 document对象 有的语法
                console.log(ajax.responseXML);
                console.log(ajax.responseXML.querySelector('kuzi').innerHTML);
                // 下面这个 页面文档对象 如果要获取某个标签
                console.log(window.document);
            }
        };
    };
</script>
```