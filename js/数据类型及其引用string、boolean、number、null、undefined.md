-   **基本数据类型（值类型）**：String 字符串、Number 数值、Boolean 布尔值、Null 空值、Undefined 未定义、（BigInt 大型数值、Symbole /s6)。
-   **引用数据类型（引用类型）**：Object 对象。
 注意：内置对象 Function、Array、Date、RegExp、Error 等都是属于 Object 类型。也就是说，除了那七种基本数据类型之外，其他的，都称之为 Object 类型。
 
 **数据类型之间最大的区别**：

-   基本数据类型：参数赋值的时候，传数值。
    
-   引用数据类型：参数赋值的时候，传地址。

## 栈内存和堆内存
所有的**变量**都是保存在**栈内存**中的。

**基本数据类型**：

基本数据类型的值，直接保存在栈内存中。值与值之间是独立存在，修改一个变量不会影响其他的变量。   
```
var a = 23;
var b = a;

a++;

console.log(a); // 打印结果：24
console.log(b); // 打印结果：23
```

**引用数据类型**：

对象是保存到**堆内存**中的。每创建一个新的对象，就会在堆内存中开辟出一个新的空间；而**变量保存了对象的内存地址**（对象的引用），保存在栈内存当中。如果两个变量保存了同一个对象的引用，当一个通过一个变量修改属性时，另一个也会受到影响。
```
var obj1 = new Object();
obj1.name = 'smyh';

// 让 obj2 等于 obj1
var obj2 = obj1;

// 修改 obj1 的 name 属性
obj1.name = 'vae';

console.log(obj1.name); // 打印结果：vae
console.log(obj2.name); // 打印结果：vae
```

## 字符串 String
字符串型可以是引号中的任意文本，其语法为：双引号 `""` 或者单引号 `''`
### 转义字符
-   `\"` 表示 `"` 双引号
    
-   `\'` 表示 `'` 单引号
    
-   `\\` 表示`\`
    
-   `\r` 表示回车
    
-   `\n` 表示换行。n 的意思是 newline。
    
-   `\t` 表示缩进。t 的意思是 tab。
    
-   `\b` 表示空格。b 的意思是 blank。

### 获取字符串的长度
```
var str1 = '千古壹号';
var str2 = '千古壹号，永不止步！';

var str3 = 'qianguyihao';
var str4 = 'qianguyihao, keep moving!';

console.log(str1.length); // 4
console.log(str2.length); // 10
console.log(str3.length); // 11
console.log(str4.length); // 25
```
-   一个中文算一个字符，一个英文算一个字符
    
-   一个标点符号（包括中文标点、英文标点）算一个字符
    
-   一个空格算一个字符
    
### 字符串拼接
多个字符串之间可以使用加号 `+` 进行拼接。
```
字符串 + 任意数据类型 = 拼接之后的新字符串;
```
## 模板字符串（模板字面量）
### 在模板字符串中插入变量
```
var name = 'qianguyihao';
var age = '26';

console.log('我是' + name + ',age:' + age); //传统写法
console.log(`我是${name},age:${age}`); //ES6 写法。注意语法格式
```
**注意**，上方代码中，倒数第二行用的符号是单引号，最后一行用的符号是反引号（在 tab 键的上方）。

### 在模板字符串中插入表达式
```
const a = 5;
const b = 10;

// 下面这行代码，故意做了换行。
console.log(`this is ${a + b} and
not ${2 * a + b}.`);
```
### 模板字符串中可以换行
###  模板字符串中可以调用函数
```
function getName() {
    return 'qianguyihao';
}

console.log(`www.${getName()}.com`); // 打印结果：www.qianguyihao.com
```
### 模板字符串支持嵌套使用
```
const nameList = ['千古壹号', '许嵩', '解忧少帅'];

function myTemplate() {
    // join('') 的意思是，把数组里的内容合并成一个字符串
    return `<ul>
	${nameList.map((item) => `<li>${item}</li>`).join('')}
	</ul>`;
}
document.body.innerHTML = myTemplate();
```

## 布尔值：Boolean
布尔值直接使用就可以了，千万不要加引号。
```
var a = true;
console.log(typeof a);
```

## 数值型：Number
### 数值范围
由于内存的限制，ECMAScript 并不能保存世界上所有的数值。

-   最大值：`Number.MAX_VALUE`，这个值为： 1.7976931348623157e+308
    
-   最小值：`Number.MIN_VALUE`，这个值为： 5e-324
    

如果使用 Number 表示的变量超过了最大值，则会返回 Infinity。

-   无穷大（正无穷）：Infinity
    
-   无穷小（负无穷）：-Infinity
    

注意：`typeof Infinity`的返回结果是 number。

### NaN
表示 Not a Number，非数值
1.  `typeof NaN`的返回结果是 number。
    
2.  **Undefined 和任何数值计算的结果为 NaN。NaN 与任何值都不相等，包括 NaN 本身。**
    
3.  关于 isNaN () 函数，可以看后续的文章《typeof 和数据类型转换》。

### 连字符和加号的区别

键盘上的 `+` 可能是连字符，也可能是数字的加号。
```
console.log("我" + "爱" + "你");	//连字符，把三个独立的汉字，连接在一起了
console.log("我+爱+你");			//原样输出
console.log(1+2+3);				//输出6
```
在变量中加入字符串进行拼接，可以被同化为字符串。

### 隐式转换
`"2"+1`得到的结果其实是字符串，但是`"2"-1`得到的结果却是数值 1，这是因为计算机自动帮我们进行了“**隐式转换**”。

也就是说，`-`、`*`、`/`、`%`这几个符号会自动进行隐式转换。

## 变量值的传递（赋值）
```
a = b;
```
把 b 的值赋给 a，b 不变。

##   Null：空对象
如果你想定义一个变量用来保存引用类型，但是还没想好放什么内容，这个时候，可以在初始化时将其设置为 null。你可以把 null 理解为：**null 虽然是一个单独的数据类型，但 null 相当于是一个 object，只不过地址为空（空指针）而已**。
```
let myObj = null;
cosole.log(typeof myObj); // 打印结果：object
```
-   Null 类型的值只有一个，就是 null。比如 `let a = null`。
    
-   使用 typeof 检查一个 null 值时，会返回 object。

##   undefined：未定义类型
-   Undefined 类型的值只有一个，就是 undefind。
-   使用 typeof 检查一个 undefined 值时，会返回 undefined。
### case1：变量已声明，未赋值时
**声明**了一个变量，但没有**赋值**，此时它的值就是 `undefined`
```
let name;
console.log(name); // 打印结果：undefined
console.log(typeof name); // 打印结果：undefined
```
### Case2：变量未声明（未定义）时
### Case3：函数无返回值时（没有 return）
### Case4：调用函数时，未传参
## Null 和 NaN 的区别
`null == undefined` 的结果为 `true`
`null === undefined` 的结果是 false。
-   10 + null 结果为 10。
-   10 + undefined 结果为 NaN。

-    任何值和 null 运算，null 可看做 0 运算。
-   任何数据类型和 undefined 运算都是 NaN。