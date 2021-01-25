---
layout: post
title: "JavaScript Tutorial"
author: "Don Quixote"
tags: JavaScript
---

This blog mainly comes from Liao Xuefeng teacher’s website. About JavaScript Tuturial. It’s easy to understand, and here just for me to record some tip for myself. So guys, If you want to learn JavaScript, you’d better redirect to Liao’s site. 

这篇内容，主要是用来记录自己在学习廖雪峰老师的JavaScript课程时的一些记录。供个人学习，如果有兴趣，请访问廖雪峰老师官网。

## JavaScript简介

![JavaScript](https://miro.medium.com/max/800/1*bxEkHw1xewxOFjmGunb-Cw.png)

### JavaScript历史

要了解JavaScript，我们首先要回顾一下JavaScript的诞生。在上个世纪的1995年，当时的网景公司正凭借其Navigator浏览器成为Web时代开启时最著名的第一代互联网公司。由于网景公司希望能在静态HTML页面上添加一些动态效果，于是叫Brendan Eich这哥们在两周之内设计出了JavaScript语言。你没看错，这哥们只用了10天时间。为什么起名叫JavaScript？原因是当时Java语言非常红火，所以网景公司希望借Java的名气来推广，但事实上JavaScript除了语法上有点像Java，其他部分基本上没啥关系。

###  ECMAScript

因为网景开发了JavaScript，一年后微软又模仿JavaScript开发了JScript，为了让JavaScript成为全球标准，几个公司联合ECMA（European Computer Manufacturers Association）组织定制了JavaScript语言的标准，被称为ECMAScript标准。所以简单说来就是，ECMAScript是一种语言标准，而JavaScript是网景公司对ECMAScript标准的一种实现。那为什么不直接把JavaScript定为标准呢？因为JavaScript是网景的注册商标。不过大多数时候，我们还是用JavaScript这个词。如果你遇到ECMAScript这个词，简单把它替换为JavaScript就行了。

### JavaScript版本

JavaScript语言是在10天时间内设计出来的，虽然语言的设计者水平非常NB，但谁也架不住“时间紧，任务重”，所以，JavaScript有很多设计缺陷，我们后面会慢慢讲到。此外，由于JavaScript的标准——ECMAScript在不断发展，最新版ECMAScript 6标准（简称ES6）已经在2015年6月正式发布了，所以，讲到JavaScript的版本，实际上就是说它实现了ECMAScript标准的哪个版本。由于浏览器在发布时就确定了JavaScript的版本，加上很多用户还在使用IE6这种古老的浏览器，这就导致你在写JavaScript的时候，要照顾一下老用户，不能一上来就用最新的ES6标准写，否则，老用户的浏览器是无法运行新版本的JavaScript代码的。不过，JavaScript的核心语法并没有多大变化。我们的教程会先讲JavaScript最核心的用法，然后，针对ES6讲解新增特性。

## 快速入门

```javascript
// 以双斜杠开头直到行末的是注释，注释是给人看的，会被浏览器忽略
/* 在这中间的也是注释，将被浏览器忽略 */
// 第一个JavaScript代码:
alert('我要学JavaScript!');

var a = 1 + 2 * 3 / 4;
console.log(a);
2.5
```

### 基本语法

#### 语法

语句以`;`结束，语句块用`{...}`。但是，JavaScript并不强制要求每个语句结尾加`;`。

```javascript
var x = 1;
'Hello, world';
var x = 1; var y = 2; // 不建议一行写多个语句
```

语句块是一组语句的集合，例如，下面的代码先做了一个判断，如果判断成立，将执行`{...}`中的所有语句：

```javascript
if (2 > 1) {
    x = 1;
    y = 2;
    z = 3;
}
```

注意花括号`{...}`内的语句具有缩进，通常是4个空格。缩进不是JavaScript语法要求必须的，但缩进有助于我们理解代码的层次，所以编写代码时要遵守缩进规则。很多文本编辑器具有“自动缩进”的功能，可以帮助整理代码。

`{...}`还可以嵌套，形成层级结构：

```javascript
if(2 > 1){
    x = 1;
    y = 2;
    z = 3;
    if (x < y){
        z = 4;
    }
    if (x > y){
        z = 5;
    }
}
```

#### 注释

以`//`开头直到行末的字符被视为行注释，注释是给开发人员看到，JavaScript引擎会自动忽略：

```javascript
// 这是一行注释
alert('hello'); // 这也是注释
```

另一种块注释是用`/*...*/`把多行字符包裹起来，把一大“块”视为一个注释：

```javascript
/* 从这里开始是块注释
仍然是注释
仍然是注释
注释结束 */
```

#### 大小写

JavaScript严格区分大小写，如果弄错了大小写，程序将报错或者运行不正常。

### 数据类型和变量

#### 数据类型

计算机顾名思义就是可以做数学计算的机器，因此，计算机程序理所当然地可以处理各种数值。但是，计算机能处理的远不止数值，还可以处理文本、图形、音频、视频、网页等各种各样的数据，不同的数据，需要定义不同的数据类型。在JavaScript中定义了以下几种数据类型：

#### Number

JavaScript不区分整数和浮点数，统一用Number表示，以下都是合法的Number类型：

```javascript
123;  // 整数
0.456;  // 浮点数0.456
1.2345e3;  // 科学计数法表示1.2345*1000，等同于1234.5
-99;  // 负数
NaN;  // NaN表示Not a Number，当无法计算时用NaN表示
Infinity;  // Infinity表示无限大，当数值超过了JavaScript的Number所能表示的最大值时，就表示Infinity
```

计算机由于使用二进制，所以，有时候用十六进制表示整数比较方便，十六进制用0x前缀和0-9，a-f表示，例如：`0xff00`，`0xa5b4c3d2`，等等，它们和十进制表示的数值完全一样。

Number可以直接做四则运算，规则和数学一致：

```javascript
1+2;
3
(1+2)*5/2;
7.5
2/0;
Infinity
0/0;
NaN
10%3;
1
10.5%3;
1.5
```

注意`%`是求余运算。

#### 字符串

字符串是以单引号'或双引号"括起来的任意文本，比如`'abc'`，`"xyz"`等等。请注意，`''`或`""`本身只是一种表示方式，不是字符串的一部分，因此，字符串`'abc'`只有`a`，`b`，`c`这3个字符。

#### 布尔值

布尔值和布尔代数的表示完全一致，一个布尔值只有`true`、`false`两种值，要么是`true`，要么是`false`，可以直接用`true`、`false`表示布尔值，也可以通过布尔运算计算出来：

```javascript
true;
true
false;
false
2 > 1;
true
2 >= 3;
false
```

`&&`运算是与运算，只有所有都为`true`，`&&`运算结果才是`true`：

```javascript
true && true;
true
true && false;
false
false && true && false;
false
```

`!`运算是非运算，它是一个单目运算符，把`true`变成`false`，`false`变成`true`：

```javascript
! true; // 结果为false
! false; // 结果为true
! (2 > 5); // 结果为true
```

布尔值经常用在条件判断中，比如：

```javascript
var age = 15;
if (age >= 18) {
    alert('adult');
} else {
    alert('teenager');
}
```

#### 比较运算符

当我们对Number做比较时，可以通过比较运算符得到一个布尔值：

```javascript
2 > 5; // false
5 >= 2; // true
7 == 7; // true
```

实际上，JavaScript允许对任意数据类型做比较：

```javascript
false == 0; // true
false === 0; // false
```

要特别注意相等运算符`==`。JavaScript在设计时，有两种比较运算符：

第一种是`==`比较，它会**自动转换**数据类型再比较，很多时候，会得到非常诡异的结果；

第二种是`===`比较，它**不会自动转换**数据类型，如果数据类型不一致，返回`false`，如果一致，再比较。

由于JavaScript这个设计缺陷，***不要*使用`==`比较，始终坚持使用`===`比较。**

另一个例外是`NaN`这个特殊的Number与所有其他值都不相等，包括它自己：

```javascript
NaN === NaN; // false
```

唯一能判断`NaN`的方法是通过`isNaN()`函数：

```javascript
isNaN(NaN); // true
isNaN(5); // false
```

最后要注意浮点数的相等比较：

```javascript
1 / 3 === (1 - 2 / 3); // false
```

这不是JavaScript的设计缺陷。浮点数在运算过程中会产生误差，因为计算机无法精确表示无限循环小数。要比较两个浮点数是否相等，只能计算它们之差的绝对值，看是否小于某个阈值：

```javascript
Math.abs(1 / 3 - (1 - 2 / 3)) < 0.0000001; // true
```

#### null和undefined

`null`表示一个“空”的值，它和`0`以及空字符串`''`不同，`0`是一个数值，`''`表示长度为0的字符串，而`null`表示“空”。

在其他语言中，也有类似JavaScript的`null`的表示，例如Java也用`null`，Swift用`nil`，Python用`None`表示。但是，在JavaScript中，还有一个和`null`类似的`undefined`，它表示“未定义”。

JavaScript的设计者希望用`null`表示一个空的值，而`undefined`表示值未定义。事实证明，这并没有什么卵用，区分两者的意义不大。**大多数情况下，我们都应该用`null`。**`undefined`仅仅在判断函数参数是否传递的情况下有用。

#### 数组

数组是一组按顺序排列的集合，集合的每个值称为元素。JavaScript的数组可以包括任意数据类型。例如：

```javascript
[1, 2, 3.14, 'Hello', null, true];
```

上述数组包含6个元素。数组用`[]`表示，元素之间用`,`分隔。

另一种创建数组的方法是通过`Array()`函数实现：

```javascript
new Array(1, 2, 3); // 创建了数组[1, 2, 3]
```

然而，出于代码的可读性考虑，强烈建议直接使用`[]`。

数组的元素可以通过索引来访问。请注意，索引的起始值为`0`：

```javascript
var arr = [1, 2, 3.14, 'Hello', null, true];
arr[0]; // 返回索引为0的元素，即1
arr[5]; // 返回索引为5的元素，即true
arr[6]; // 索引超出了范围，返回undefined
```

#### 对象

JavaScript的对象是一组由键-值组成的无序集合，例如：

```javascript
var person = {
    name: 'Bob',
    age: 20,
    tags: ['js', 'web', 'mobile'],
    city: 'Beijing',
    hasCar: true,
    zipcode: null
};
```

JavaScript对象的键都是字符串类型，值可以是任意数据类型。上述`person`对象一共定义了6个键值对，其中每个键又称为对象的属性，例如，`person`的`name`属性为`'Bob'`，`zipcode`属性为`null`。

要获取一个对象的属性，我们用`对象变量.属性名`的方式：

```javascript
person.name; // 'Bob'
person.zipcode; // null
```

#### 变量

变量的概念基本上和初中代数的方程变量是一致的，只是在计算机程序中，变量不仅可以是数字，还可以是任意数据类型。

变量在JavaScript中就是用一个变量名表示，变量名是大小写英文、数字、`$`和`_`的组合，且不能用数字开头。变量名也不能是JavaScript的关键字，如`if`、`while`等。申明一个变量用`var`语句，比如：

```javascript
var a; // 申明了变量a，此时a的值为undefined
var $b = 1; // 申明了变量$b，同时给$b赋值，此时$b的值为1
var s_007 = '007'; // s_007是一个字符串
var Answer = true; // Answer是一个布尔值true
var t = null; // t的值是null
```

变量名也可以用中文，但是，请不要给自己找麻烦。

在JavaScript中，使用等号`=`对变量进行赋值。可以把任意数据类型赋值给变量，同一个变量可以反复赋值，而且可以是不同类型的变量，但是要注意只能用`var`申明一次，例如：

```javascript
var a = 123; // a的值是整数123
a = 'ABC'; // a变为字符串
```

这种变量本身类型不固定的语言称之为动态语言，与之对应的是静态语言。静态语言在定义变量时必须指定变量类型，如果赋值的时候类型不匹配，就会报错。例如Java是静态语言，赋值语句如下：

```java
int a = 123; // a是整数类型变量，类型用int申明
a = "ABC"; // 错误：不能把字符串赋给整型变量
```

和静态语言相比，动态语言更灵活，就是这个原因。

请不要把赋值语句的等号等同于数学的等号。比如下面的代码：

```javascript
var x = 10;
x = x + 2;
```

如果从数学上理解`x = x + 2`那无论如何是不成立的，在程序中，赋值语句先计算右侧的表达式`x + 2`，得到结果`12`，再赋给变量`x`。由于`x`之前的值是`10`，重新赋值后，`x`的值变成`12`。

要显示变量的内容，可以用`console.log(x)`，打开Chrome的控制台就可以看到结果。

使用`console.log()`代替`alert()`的好处是可以避免弹出烦人的对话框。

#### strict模式

JavaScript在设计之初，为了方便初学者学习，并不强制要求用`var`申明变量。这个设计错误带来了严重的后果：如果一个变量没有通过`var`申明就被使用，那么该变量就自动被申明为全局变量：

```javascript
i = 10; // i现在是全局变量
```

在同一个页面的不同的JavaScript文件中，如果都不用`var`申明，恰好都使用了变量`i`，将造成变量`i`互相影响，产生难以调试的错误结果。

使用`var`申明的变量则不是全局变量，它的范围被限制在该变量被申明的函数体内（函数的概念将稍后讲解），同名变量在不同的函数体内互不冲突。

为了修补JavaScript这一严重设计缺陷，ECMA在后续规范中推出了strict模式，在strict模式下运行的JavaScript代码，强制通过`var`申明变量，未使用`var`申明变量就使用的，将导致运行错误。

启用strict模式的方法是在JavaScript代码的第一行写上：

```javascript
'use strict';
```

这是一个字符串，不支持strict模式的浏览器会把它当做一个字符串语句执行，支持strict模式的浏览器将开启strict模式运行JavaScript。

不用`var`申明的变量会被视为全局变量，为了避免这一缺陷，所有的JavaScript代码都应该使用strict模式。我们在后面编写的JavaScript代码将全部采用strict模式。



### 字符串

JavaScript的字符串就是用`''`或`""`括起来的字符表示。

如果`'`本身也是一个字符，那就可以用`""`括起来，比如`"I'm OK"`包含的字符是`I`，`'`，`m`，空格，`O`，`K`这6个字符。

如果字符串内部既包含`'`又包含`"`怎么办？可以用转义字符`\`来标识，比如：

```javascript
'I\'m \"OK\"!';
```

表示的字符串内容是：`I'm "OK"!`

转义字符`\`可以转义很多字符，比如`\n`表示换行，`\t`表示制表符，字符`\`本身也要转义，所以`\\`表示的字符就是`\`。

ASCII字符可以以`\x##`形式的十六进制表示，例如：

```javascript
'\x41'; // 完全等同于 'A'
```

还可以用`\u####`表示一个Unicode字符：

```javascript
'\u4e2d\u6587'; // 完全等同于 '中文'
```

#### 多行字符串

由于多行字符串用`\n`写起来比较费事，所以最新的ES6标准新增了一种多行字符串的表示方法，用反引号 *`\* ... \*`* 表示：

```javascript
`这是一个
多行
字符串`;
```

```javascript
`这是一个
多行
字符串`
"这是一个↵多行↵字符串"
```

*注意*：反引号在键盘的ESC下方，数字键1的左边：

```ascii
┌─────┐ ┌─────┬─────┬─────┬─────┐
│ ESC │ │ F1  │ F2  │ F3  │ F4  │
│     │ │     │     │     │     │
└─────┘ └─────┴─────┴─────┴─────┘
┌─────┬─────┬─────┬─────┬─────┐
│  ~  │  !  │  @  │  #  │  $  │
│  `  │  1  │  2  │  3  │  4  │
├─────┴──┬──┴──┬──┴──┬──┴──┬──┘
│        │     │     │     │
│  tab   │  Q  │  W  │  E  │
├────────┴──┬──┴──┬──┴──┬──┘
│           │     │     │
│ caps lock │  A  │  S  │
└───────────┴─────┴─────┘
```

练习：测试你的浏览器是否支持ES6标准，如果不支持，请把多行字符串用`\n`重新表示出来：

```javascript
console.log(`多行
字符串
测试`)
多行
字符串
测试
```

#### 模板字符串

要把多个字符串连接起来，可以用`+`号连接：

```javascript
var name = '小明';
var age = 20;
var message = '你好, ' + name + ', 你今年' + age + '岁了!';
alert(message);
```

如果有很多变量需要连接，用`+`号就比较麻烦。ES6新增了一种模板字符串，表示方法和上面的多行字符串一样，但是它会自动替换字符串中的变量：

```javascript
var name = '小名';
var age = 20;
var message = `你好，${name}, 你今年${age}岁了!`;
alert(message);
```

#### 操作字符串

字符串常见的操作如下：

```
var s = 'Hello, world!';
s.length; // 13
```

要获取字符串某个指定位置的字符，使用类似Array的下标操作，索引号从0开始：

```javascript
var s = 'Hello, world!';

s[0]; // 'H'
s[6]; // ' '
s[7]; // 'w'
s[12]; // '!'
s[13]; // undefined 超出范围的索引不会报错，但一律返回undefined
```

*需要特别注意的是*，字符串是不可变的，如果对字符串的某个索引赋值，不会有任何错误，但是，也没有任何效果：

```javascript
var s = 'Test';
s[0] = 'X';
alert(s); // s仍然为'Test'
```

JavaScript为字符串提供了一些常用方法，注意，调用这些方法本身不会改变原有字符串的内容，而是返回一个新字符串：

#### toUpperCase

`toUpperCase()`把一个字符串全部变为大写：

```
var s = 'Hello';
s.toUpperCase(); // 返回'HELLO'
```











### 数组

### 对象

### 条件判断

### 循环

### Map和Set

### iterable

## 函数

### 函数定义和调用

### 变量作用域和结构赋值

### 方法

### 高阶函数

#### map/reduce

#### filter

#### sort

#### Array

### 闭包

### 箭头函数

### generator

## 标准对象

### Date

### RegExp

### JSON

## 面向对象编程

### 创建对象

### 原型继承

### class继承

## 浏览器

### 浏览器对象

### 操作DOM

#### 更新DOM

#### 插入DOM

#### 删除DOM

### 操作表单

### 操作文件

### AJAX

### Promise

### Canvas

## jQuery

### 选择器

#### 层级选择器

#### 查找和过滤

### 操作DOM

#### 修改DOM结构

### 事件

### 动画

### AJAX

### 扩展

## 错误处理

### 错误传播

### 异步错误处理

## underscore

### Collections

### Arrays

### Functions

### Objects

### Chaining

## Node.js

### 安装Node.js和npm

### 第一个Node程序

### 搭建Node开发环境

### 模块

### 基本模块

#### fs

#### stream

#### http

#### crypto

### Web开发

#### koa

##### koa入门

##### 处理URL

##### 使用Nunjucks

##### 使用MVC

#### mysql

##### 使用Sequelize

##### 建立Model

#### mocha

##### 编写测试

##### 异步测试

##### Http测试

#### WebSocket

##### 使用ws

##### 编写聊天室

#### REST

##### 编写REST API

##### 开发REST API

#### MVVM

##### 单向绑定

##### 双向绑定

##### 同步DOM结构

##### 集成API

##### 在线电子表格

#### 自动化工具

## 期末总结







<br>

_The end_