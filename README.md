# ES6
- 书籍：阮一峰es6标准入门第三版
- 立即执行函数
- 闭包
- 解决var存在的问题，出现了let和const定义

---
###### let
- 不存在变量提升
- 不能重复定义
- 存在暂时性死区
- 块级作用域
- let定义的不在window下

---
###### const
- 相当于声明一个只读常量，不可更改
- 不可更改的实质是内存地址不可改变
- RE：多从内存地址的角度考虑问题

---
###### 变量的解构赋值
从数组和对象中提取值，对变量进行赋值就是解构

有以下几种：
1. 数组解构
2. 对象解构
3. 字符串解构
4. 应用：函数参数的解构赋值、函数返回值、变量互换、json应用
- 数组根据索引来，而对象不是，不能用索引，只能通过对象名

---
###### 扩展运算符）和rest运算符（...）
1. 不确定参数
 (arg接收不确定新数组参数)
2. 作为数组的一部分
3. 数组复制
4. 合并数组
5. 合并对象
6. 解构
7. 解构赋值——只能实现半深克隆
8. rest（）；剩余的

---
###### 字符串扩展
- 模板字符串（反引号） ${}，支持标签、换行、数学运算
- indexOf()——检索字符串，有返回索引，没有返回-1
- includes（）——检索是否包含
- startsWith()
- endsWith()
- padStart(n,"XXXX")——把字符串加长，从头加，只能加长，不会减短
- padEnd()——从尾加
- repeat()

---
###### 数值扩展
逐步减少全局性方法，更加模块化
- 进制转换
- Number.isFinite()——是否为数字
- Number.isNaN（NaN）——判断是否是NaN
- Number.isInteger（5）——判断是否为整型
- Number.parseInt——把浮点型等转化成整型
- Number.parseFloat
- Number.isSafeInteger——安全范围内数字【js最大是2的53次幂】
- Math.trunc()——去掉一个数的小数部分，保留整数部分
-  Math.sign()——，判断正负数，正数返回1,0返回0，负数返回-1

---
###### 函数扩展
- 参数默认值，与解构赋值结合（类似于解构）
- 方法.length——返回没有指定默认值的参数个数
- 方法 .name——返回函数名
- rest参数
- 'use strict'——严格模式:


```
所谓严格模式即：
1. 变量必须先显式声明再使用，不能隐式声明
2. 禁止this关键字指向全局对象，构造函数必须new
3. 函数不能有重名的参数
4. 禁止使用with语句（with会改变当前this指向）
5. 不能用arguments.callee——相当于实现自身递归
6. .....还有好多好多
7. 函数内部 
8. ES6:规定只要函数参数使用了默认值、解构赋值、或者 扩展运算符，那么函数内部就不能显式设定为严格模式， 否则会报错。
```

- 箭头函数=>

```
1. 简化问题——箭头函数写法上是把function去掉，在参数括号后加箭头，最终可简化到只剩一个花括号
2. this指向问题，指向当前作用域，区别于普通的this指向，或者说：函数体内的this对象，就是定义时所指的this对象，而不是使用时所在的对象——看作用区
3. 不可以使用arguments对象，该对象在函数体内不存在，如果必须要用，就用rest代替
```

---
###### 构造函数

---
###### 数组扩展
- Array.from()			json数组格式、类数组 
- Array.of()			将一组值，转换为数组
- arr.copyWithin(target,	start	=	0,	end	=	this.length) 

```
- target（必需）：从该位置开始替换数据
- start（可选）：从该位置开始读取数据，默认为0。如 果为负值，表示倒数。
-end（可选）：到该位置前停止读取数据，默认等于数 组长度。如果为负值，表示倒数。 
```
- arr.find(function(val,	key,	arr){});用于找出第一个符合条 件的数组成员 arr.findIndex()
- arr.fill(’xx’,	1,	3);							
new	Array(3).fill(7)		
- arr.includes()数组是否包含给定的值，与字符串的 includes方法类似
- for	…of循环 
- entries()，keys()——用于遍历数组 
- 数组遍历： 

```
1.forEach():没有返回值，只是针对每个元素调用func
2.map():返回一 个新的Array，每个元素为调用func的结果
3.filter():返回一个符合func条件的元素数组（过滤）
4.some():返回一个boolean，判断是否有元素是否符合func条件
5.every():返回一个boolean，判断每个元素是否符合func条件
```

---
###### 对象扩展
- 属性简洁表示法， 包括属性和方法 （自动解析键值对）
- 属性名表达式:[] 
- Object.is(‘foo’, ‘foo’); 比较两个值是否严格相等，
```
与严格比较运 算符（===）的行为基本一致 +0===-0 NaN===NaN
==判断值相等
===判断数据类型相等
NaN===NaN——false
Object.is(NaN, NaN)——true
```

（对象判断的是地址）

- Object.assign();对象合并,第一个参数是目标对象，后面的参数 都是源对象。浅拷贝

（与扩展运算符合并对象类似）

- ‘name’		in		  obj判断对象是否包含某个属性；

     0	in	arr判断数组位置是否有值


---
###### Symbol
- 新的原始数据类型Symbol，表示独一无二的值。可以保证不会与 其他属性名产生冲突。
```
letname	=	Symbol();
obj[name]	=	‘XX';

```
- 该属性不会出现在for...in、for...of循环中

---
###### Set
- Set类似于数组，但是成员的值都是唯一的，没有重复的值。函数接受数组或类数组作为参数。new	Set();
- add(value)：添加某个值，返回Set结构本身。
- delete(value)：删除某个值，返回一个布尔值，表示删除是否成 功。
- has(value)：返回一个布尔值，表示该值是否为Set的成员。
- clear()：清除所有成员，没有返回值 
- 遍历：

```
keys()
entires()	
forEach()	
for…of
```
- 长度：.size() 
- WeakSet:成员只能是对象，而不能是其他类型的值。add()增加值

---
###### Map
- 类似于对象，也是键值对的集合，但是“键”的范围不限于字符串，各种类型的值（包括对象）都可以当作键。new	Map() 
- .size属性返回Map	结构的成员总数 
- .set(key,	value) 
- .get(key) 
- .has(key) 
- .delete(key) 
- .clear() 
- 遍历 
- WeakMap：只接受对象作为键名object（null除外），不接受其他类型的值作为键名

---
###### promise(AJAX)
- Ajax:	Asynchronous	JavascriptAnd	XML（异步JavaScript和 XML） 
- Ajax原理（三步走） 

```
//第一步创建 XMLHttpRequest 对象

    var xmlhttp;
    if (window.XMLHttpRequest)
      {// code for IE7+, Firefox, Chrome, Opera, Safari
      xmlhttp=new XMLHttpRequest();
      }
    else
      {// code for IE6, IE5
      xmlhttp=new ActiveXObject("Microsoft.XMLHTTP");
      }

      //第二部 请求发送

      xmlhttp.open("GET","musicdata.json?t=" + Math.random(),true);
      xmlhttp.send();

      //第三步

      xmlhttp.onreadystatechange=function()
      {
      if (xmlhttp.readyState==4 && xmlhttp.status==200)
        {
          console.log()
          var thisdata = JSON.parse(xmlhttp.responseText)
          for(var i=0;i<thisdata.musicData.length;i++){
     console.log(thisdata.musicData[i].title);
          }
        }
      }

      /*

      存有 XMLHttpRequest 的状态。从 0 到 4 发生变化。

      0: 请求未初始化

      1: 服务器连接已建立

      2: 请求已接收

      3: 请求处理中

      4: 请求已完成，且响应已就绪

      */
```

- Jquery:	$.get().			$.post() 
- Promise	是异步编程的一种解决方案，比传统的解决方 案————更合理和更强大。回调函数和事件
- 异步编程的一种解决方案，比传统的解决方案——回调函数和事件——更合理 和更强大
- Promise对象有以下两个特点。 

```
（1）对象的状态不受外界影响。Promise对象代表一个异步操作，有三种状态：
 pending（进行中）、
fulfilled（已成功）
和rejected（已失败）。
只有异步操作的结果，可以决定当前是哪一种状态，任何其他操作都无法改变这个状态。
这也是 Promise这个名字的由来，它的英语意思就是“承诺”，表示其他手段无法改变。 
（2）一旦状态改变，就不会再变，任何时候都可以得到这个结果。
Promise对象 的状态改变，只有两种可能：
从pending变为fulfilled
和从pending变为rejected。 
只要这两种情况发生，状态就凝固了，不会再变了，会一直保持这个结果，这时 就称为resolved（已定型）。如果改变已经发生了，你再对Promise对象添加回 调函数，也会立即得到这个结果。
这与事件（Event）完全不同，事件的特点是， 如果你错过了它，再去监听，是得不到结果的。
```

---
###### Generator
- Generator	函数是ES6	提供的一种异步编程解决方案
- Generator最大特点就是可以交出函数的执行权（即暂停执行）。
- Generator 函数。它不同于普通函数，是可以暂停执行的，所以函数名之前要加星号，以示区别。
-  Generator 函数不同于普通函数的另一个地方，即执行它不会返回结果，返回的是指针对象。
-  Generator 函数可以暂停执行和恢复执行，这是它==能封装异步任务的根本原因==。
- 形式上，Generator	函数是一个普通函数，但是有两个特征。
一是， function关键字与函数名之间有一个星号；
二是，函数体内部使用 yield表达式，定义不同的内部状态（yield在英语里的意思就Generator最大特点就是可以交出函数的执行权（即暂停执行）。
整个 Generator 函数就是一个封装的异步任务，或者说是异步任务的容器。异步操作需要暂停的地方，都用 yield 语句注明。
 Generator 函数不同于普通函数的另一个地方，即执行它不会返回结果，返回的是指针对象。
Generator 函数可以暂停执行和恢复执行，这是它能封装异步任务的根本原因。是“产 出”） 
- 由于Generator	函数返回的遍历器对象，只有调用next方法才会遍 历下一个内部状态，所以其实提供了一种可以暂停执行的函数。 yield表达式就是暂停标志。
- yield表达式本身没有返回值，或者说总是返回undefined。next方法 可以带一个参数，该参数就会被当作上一个yield表达式的返回值。

---
###### class
- 类---对象 
- constructor() 
- 类和模块的内部，默认就是严格模式，所以不需要使用use	strict指 定运行模式。只要你的代码写在类或模块之中，就只有严格模式可 用。考虑到未来所有的代码，其实都是运行在模块之中，所以ES6	实际上把整个语言升级到了严格模式
- extends

---
###### call,apply,bind
==call、apply、bind的作用是改变函数运行时this的指向==
- call:后面可存多个参数

```
call() 方法在使用一个指定的 this 值和若干个指定的参数值的前提下调用某个函数或方法。
call 方法第一个参数是要绑定给this的值，后面传入的是一个参数列表。
当第一个参数为null、undefined的时候，默认指向window。
```

- apply:后面只能存两个参数，后者为参数数组

```
apply接受两个参数，第一个参数是要绑定给this的值，第二个参数是一个参数数组。
当第一个参数为null、undefined的时候，默认指向window。
```
==事实上apply 和 call 的用法几乎相同, 唯一的差别在于：当函数需要传递多个变量时, apply 可以接受一个数组作为参数输入, call 则是接受一系列的单独变量。==


```
对于什么时候该用什么方法，其实不用纠结。如果你的参数本来就存在一个数组中，那自然就用 apply，如果参数比较散乱相互之间没什么关联，就用 call。
```

- bind:依次传剩余参数

```
bind() 方法会创建一个新函数。当这个新函数被调用时，bind() 的第一个参数将作为它运行时的 this，之后的一序列参数将会在传递的实参前传入作为它的参数。
bind 函数的两个特点：
1.返回一个函数
2.可以传入参数
```
==和call很相似，第一个参数是this的指向，从第二个参数开始是接收的参数列表。区别在于bind方法返回值是函数以及bind接收的参数列表的使用。==
- call和apply是直接执行，bind是先绑定对象，再调用执行

---
###### 模块
-  export	:负责进行模块化，也是模块的输出。 
-  import	:	负责把模块引，也是模块的引入操作。 
-   as 
-   export	default
-   （命令行）babel-node	index.js
-   注意：ES6的模块化不能直接在浏览器中预览，必须要使用Babel进行 编译之后正常看到结果。

