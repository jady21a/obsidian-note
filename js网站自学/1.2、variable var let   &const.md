### let
```
let  = 'Hello!'; // 定义变量，并且赋值 
 alert (message); // Hello!
```

``` 
let user = 'John', age = 25, message = 'Hello';
```

`var` 与 `let/const` 有两个主要的区别：

1.  `var` 声明的变量没有块级作用域，它们仅在当前函数内可见，或者全局可见（如果变量是在函数外声明的）。
2.  `var` 变量声明在函数开头就会被处理（脚本启动对应全局变量）。声明提前（**声明会被提升，但是赋值不会。**）
3. var 重复声明的话以第一次声明为准，后声明无效。let 重复声明则会报错

变量命名：
1.  变量名称必须仅包含字母，数字，符号 `$` 和 `_`。
2.  首字符必须非数字。
3. 保留字不能用：https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Lexical_grammar#keywords

### const 常量
不变的 let

hard-coded（硬编码）：通常用大写字母表示“硬编码（hard-coded）”的常量，
当值在执行之前或在被写入代码的时候，我们就知道值是什么了