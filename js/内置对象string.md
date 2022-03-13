**JavaScript 的内置对象**：

| 内置对象  | 声明         |
| --------- | ------------ |
| arguments | 函数参数集合 |
| arry      | 数组         |
| boolean   | 布尔对象     |
| math      | 数学对象     |
| date      | 日期时间     |
| error     | 异常         |
| function  | 函数构造器   |
| number    | 数值         |
| object    | 基础对象     |
| string    | 字符串对象   |
| RegExp    | 正则表达对象 |

## 查找字符串
### 1、indexOf ()/lastIndexOf ()：获取字符串中指定内容的索引
```
索引值 = str.indexOf(想要查询的字符串);
```
可以检索一个字符串中是否含有指定内容。如果字符串中含有该内容，则会返回其**第一次出现**的索引；如果没有找到指定的内容，则返回 -1。


     Skim  js15-19
 

## 大小写转换
```
var str = 'abcdEFG';

//转换成小写
console.log(str.toLowerCase());

//转换成大写
console.log(str.toUpperCase());
```