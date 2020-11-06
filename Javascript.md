![](imgs\cake.png)

JavaScript 是一种脚本，一门编程语言，它可以在网页上实现复杂的功能，网页展现给你的不再是简单的静态信息，而是实时的内容更新，交互式的地图，2D/3D 动画，滚动播放的视频等等。



---

# 初识

------



## 应用场景

------



- 处理网页功能（数据交互）及部分特效
- 基于NodeJS开发服务端



## 环境准备

------

在普通的html页面中，加入一个不同寻常的script标签则是js最妙的开始。

提示：

1. 正常来说script标签可以增加html页面的任意位置上，不过script自己更愿意待在body标签后面

```html
<html>
	<head>
        <title>JavaScript初识</title>
        <style>
        	// CSS
        </style>
    </head>
    <body></body>
    <!-- 我才是压轴戏 -->
    <script>
        // JS代码
    	console.log('学海无涯苦作舟。');
    </script>
</html>
```



## 无话不说的人

------

我们可以通过`console.log(),alert()`等js的代码，在浏览器的控制和弹出框中输出一些**的文字（手动滑稽）

```javascript
// 控制台输出
console.log('输出内容');

// 警告框
alert('确定离开页面？');

// 模态对话框
confirm('你知不知那件事情？');

// 提示用户输入文字
prompt('请输入你的语文考试分数');

// 将指定的内容输出在页面中（什么?只能输出文字?你整点html标签搞搞）
document.write();
```



## 内嵌还是外链？

------

- **内嵌**
  我们可以将`script` 直接写在html页面中，方便于调试，减少http请求的次数

  ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <title>Title</title>
  </head>
  <body>
  
  </body>
  <script>
  	console.log('窗前明月光，疑是地上霜。');
  </script>
  </html>
  ```

- **外链**
亦可以将js代码抽取成一个独立的`.js`文件，然后再使用`script`便签加载进来，保证页面整洁性
  
  **html代码：**
  
  ```html
  <!DOCTYPE html>
  <html lang="en">
  <head>
      <meta charset="UTF-8">
      <title>Title</title>
  </head>
  <body>
  
  </body>
  <script src="js/index.js" type="text/javascript"></script>
  </html>
  ```
  
  **js代码：**
  
  ```js
  console.log('这就是js代码，能干点什么呢？');
  ```
  
  



## 箱子（变量）

------

在程序运行的过程中，不同的业务场景拥有不同的程序里，如：计算，存储，修改等等处理，都离不开`变量`的支持。`变量`的作用则是充当程序在运行中存储数据的**临时容器**，没错，**临时!!!**

<img src="imgs\boxes.png" style="zoom:50%;" />



### 小知识

------

- 通过ID获取指定输入框的值

  ```html
  <script type="text/javascript">
      /*
          不懂？看这里：
          id_val:	填入指定标签id则可
          val:	输入框中的内容
      */
      let val = document.getElementById('id_val').value;
      console.log('输入框中的内容：',val);
  </script>
  ```
  
- 获取提示框的文本内容

  ```html
  <script type="text/javascript">
  	let inputVal = prompt('请输入你的语文考试分数');
   	console.log('你刚刚输入的内容：',inputVal);
  </script>
  
  ```

  

### 定义

------

在script实现一个`"箱子"`，用来装数据。

语法：` let 变量名称 = 变量的值; 或者 var 变量名称 = 变量的值; `

只定义变量： `let date; / var time;`

定义变量并且赋值：`let date = '2020-10-10';`

定义多个变量且赋值：`let date = '2020-10-10, time = '10:00:00;'`

```html
<script type="text/javascript">
    /*
        定义变量
        
		1.你没看错，定义变量可以使用let及var来定义，至于区别以后告诉你；
    */

	var date;
	let time;
    
    console.log('变量能吃? date:',date,',time:',time);
</script>


```



### 赋值

------

“空箱子”就是浪费，来给它装点东西。

```html
<script type="text/javascript">
    /*
        定义变量

        你没看错，定义变量可以使用let及var来定义，至于区别以后告诉你
    */

	var date;
	let time;

	// 装东西到箱子中（赋值）
    date = '2019';
    time= '12:00:00';
</script>

```

### 更新

------

`箱子`里的东西，用过了，需要装新的东西。

```html
<script type="text/javascript">
    /*
        定义变量

        你没看错，定义变量可以使用let及var来定义，至于区别以后告诉你
    */

	var date;
	let time;

	// 装东西到箱子中
    date = '2019';
    time= '12:00:00';
	console.log('日期：',date,' 时间：',time);
    
    // 把箱子的旧东西丢掉，装进新的东西（重新赋值）
    date = '2020';
	time = '13:00:00';
    
    console.log('新的日期：',date,' 新的时间：',time);
</script>

```



### 连续定义

------

一个一个的定义变量实属有些繁琐。我们可以一次性定义多个变量和赋值，搞搞它。

```html
<script type="text/javascript">
    // 把上面的代码改为下列写法
    
    // 只定义，不赋值。   -_-||
    // let date,time;
    
    // 定义并赋值  :)
    let date = '2020-10-10',time = '00:00:00';
    console.log('日期：',date,' 时间：',time);
</script>
```



**好言相劝：**

1. 不要定义重名变量，js可能会给你报错。
2. 变量不要提前访问，不然会出现奇奇怪怪的问题。



### 数据类型

------

数据类型是装在箱子里面的物品类型（装在变量里的数据类型），箱子装的东西也是有要求的。



#### 数字

------

数字分为整形及浮点型两种，说白了就是整数或者小数，无论正负。

```html
<script type="text/javascript">
    var age = 18; //整数
    var weight = 65.5; //小数
    var height = '170'; // 字符串数字
    var money = -10;
    
    console.log('我今年',age,'岁，吃饱饭之后',weight,'公斤，','身高',height,'cm，现有资产',money,'元');
    
    
    
    // 数字可以用于运算，那我们来试试吧。
    let n1 = 10, n2 = 3;
    
    //  扩展知识点1:以下操作都不会影响n1和n2两个变量的值
    
    // 加法操作：result为n1和n2相加的和
    let result = n1 + n2;
    console.log('n1与n2的和:',result);
    
    // 减法操作：result为n1和n2相减的差
    result = n1 - n2;
    console.log('n1与n2的差:',result);
    
    // 乘法操作：result为n1和n2相乘的积
    result = n1 * n2;
    console.log('n1与n2的积:',result);
    
    // 除法操作：result为n1和n2相除的商
    result = n1 / n2;
    console.log('n1与n2的商:',result);
    
    // 取余操作：result为n1和n2相除的余数
    result = n1 % n2;
    console.log('n1与n2的余数:',result);
    
    // 幂运算：result为n1的n2次方
    result = n1 ** n2;
    console.log('n1的n2次方:',result);
    
    // 正数变负数
    result = n1* -1;
    console.log('我是负数:',result);
    result = -n1;
    console.log('我是负数还是正数：',result);    
    
    
    // 扩展知识点2: parseInt() 将字符串数字转换为整数，parseFloat() 将字符串数字转换为小数。
    let n3 = '10.98';
    
    // result等于n3的整数部分    
    result = parseInt(n3);
    console.log('整数:',result);
    
    // result等于n3的数字部分    
    result = parseFloat(n3);
    console.log('小数:',result);
    
</script>
```

#### 字符串

使用`'',"",`` `等引号包裹起来的字符就是字符串，不管里面是什么，包住就是字符串。

```html
<script type="text/javascript">
    // 字符串
    var text = '床前明月光';
    var text2 = "疑是地上霜";
    var text3 = `举头望明月`;
	console.log(text,',',text2,',',text3);
    
    
    // 知识点1：任何东西和字符串相加都会变成字符串哦
    text = text + 666;
    
    // 你猜猜这会输出什么？
    console.log('内容：'text);
</script>
```

#### 布尔值

道家老子曾经说：有无相生，难易相成。在js编程中还存在一种特殊值，即布尔值：不是真`(true)`那就是假`(false)`

```html
<script type="text/javascript">
    // bool
    var result = false;
    var result2 = true;
    // 提示：布尔值常常出没于数据对比的场景
    var result3 = 1 > 3;
    
    console.log('1 是不是大于 3：',result3);
</script>
```



#### 对象  `简简单单`

----

一个复杂的结构。普通变量像一杯水，清澈透明。对象更像一锅汤，由不同的料组成。在js中对象的定义比较广：`函数，对象，数据...`

```html
<script type="text/javascript">
    let obj = {name:'张三',sex:'男'}
    
    console.log('对象中的数据：',obj);
</script>
```



#### 特殊的值

---

在程序运行过程中，在用户不正常操作，编写程序预见性不够时则会出现以下的值。

```html
<script type="text/javascript">
    // 箱子是空的，没装过东西。全新的。（没有初始化）
    var d;
    console.log(d); // 输出: undefined

    // 箱子是空的，装过东西，但是现在没有东西在里面。（空是意外导致的）
    var d=null;
    console.log(d); // 输出: null
</script>
```





### 关于变量命名的规则

------

- 变量名不要以下划线开头—— 以下划线开头的被某些JavaScript设计为特殊的含义，因此可能让人迷惑。  _abc ×  a_b √
- 变量名不要以数字开头。这种行为是不被允许的，并且将引发一个错误。 let 1a=10; ×    let a1=100; √
- 一个可靠的命名约定叫做 ["小写驼峰命名法"](https://en.wikipedia.org/wiki/CamelCase#Variations_and_synonyms)，用来将多个单词组在一起，小写整个命名的第一个字母然后大写剩下单词的首字符。  create time  ---> createTime
- 让变量名直观，它们描述了所包含的数据。不要只使用单一的字母/数字，或者长句。  py  friend  
- 变量名大小写敏感——因此`myage`与`myAge`是2个不同的变量。   let i=10; let I=10;
- 最后也是最重要的一点—— 你应当避免使用JavaScript的保留字给变量命名。保留字，即是组成JavaScript的实际语法的单词！因此诸如 `var`, `function`, `let和` `for`等，都不能被作为变量名使用。浏览器将把它们识别为不同的代码项，因此你将得到错误。





## 运算符号

------



### 算术运算符

------

| 运算符 | 名称                 | 作用                                                         | 示例                                                |
| :----- | :------------------- | :----------------------------------------------------------- | :-------------------------------------------------- |
| `+`    | 加法                 | 两个数相加。                                                 | `6 + 9`                                             |
| `-`    | 减法                 | 从左边减去右边的数。                                         | `20 - 15`                                           |
| `*`    | 乘法                 | 两个数相乘。                                                 | `3 * 7`                                             |
| `/`    | 除法                 | 用右边的数除左边的数                                         | `10 / 5`                                            |
| `%`    | 求余(有时候也叫取模) | 在你将左边的数分成同右边数字相同的若干整数部分后，返回剩下的余数 | `8 % 3` (返回 2，8除以3的倍数，余下2 。)            |
| `**`   | 幂                   | 取底数的指数次方，即指数所指定的底数相乘。它在EcmaScript 2016 中首次引入。 | `5 ** 5` (返回 3125，相当于 `5 * 5 * 5 * 5 * 5` 。) |

### 赋值运算符

---

| 运算符 | 名称     | 作用                                           | 示例             | 等价于              |
| :----- | :------- | :--------------------------------------------- | :--------------- | :------------------ |
| `+=`   | 加法赋值 | 右边的数值加上左边的变量，然后再返回新的变量。 | `x = 3;x += 4;`  | `x = 3;x = x + 4;`  |
| `-=`   | 减法赋值 | 左边的变量减去右边的数值，然后再返回新的变量。 | `x = 6;x -= 3;`  | `x = 6;x = x - 3;`  |
| `*=`   | 乘法赋值 | 左边的变量乘以右边的数值，然后再返回新的变量。 | `x = 2;x *= 3;`  | `x = 2;x = x * 3;`  |
| `/=`   | 除法赋值 | 左边的变量除以右边的数值，然后再返回新的变量。 | `x = 10;x /= 5;` | `x = 10;x = x / 5;` |

```html
<script type="text/javascript">
    // 直接赋值
    var name = '张三';
    var age = 100;

    // 复合赋值
    name+= '丰'; 	// 等于: name = name + '丰';
    age-=10;		// 等于: age = age-10;
    
    console.log('用户名:',name,age); // name的值等于:张三丰    age的值等于90
</script>
```



### 比较运算符

| 运算符 | 名称       | 作用                                                   | 示例          |
| :----- | :--------- | :----------------------------------------------------- | :------------ |
| `===`  | 严格等于   | 测试左右值(数据类型与数值同时)是否相同(数据类型与数值) | `5 === 2 + 4` |
| `!==`  | 严格不等于 | 测试左右值(数据类型与数值同时)是否不相同               | `5 !== 2 + 3` |
| `<`    | 小于       | 判断左边是否小于右边                                   | `10 < 6`      |
| `>`    | 大于       | 判断左边是否大于右边                                   | `10 > 20`     |
| `<=`   | 小于或等于 | 判断左边是否小于等于右边                               | `3 <= 2`      |
| `>=`   | 大于或等于 | 判断左边是否大于等于右边                               | `5 >= 4`      |
| `==`   | 等于       | 判断左边与右边的变量（数值）是否相等                   | `5==5`        |
| `!=`   | 不等于     | 判断左边与右边的变量（数值）是否不相等                 | `5!=4`        |

**示例代码**

```html
<script type="text/javascript">
    // 定义基础变量
    var num4 = 10;
    var num5 = 12;
    var num6 = '12';

    // 大于
    console.log(num4 > num5);
    // 小于
    console.log(num4 < num5);
    // 不等于
    console.log(num4 != num5);
    // 等于
    console.log(num4 == num5);
    // 全等于
    console.log(num4 === num5);
    console.log(num5 === num6);

    // 全不等
    console.log(num4 !== num5);
    console.log(num5 !== num6);
</script>
```



## 流程控制语句

流程控制语句作为业务分支的支持，使用流程控制语句可以编写复杂的应用场景，例如：购买商品时金额是否足够？购买商品时，利用积分抵扣一部分的金额再打折等等。

<img src="imgs\cookie-choice-small.png" style="zoom: 50%;" />



### if语句

---

if语句在流程控制一直都占据着重要的地位。因为if语句器本身的特性，可以实现多条件、等值、范围等场景的条件判断。



#### if()

---

独立的`if`语句，可以用于判断指定的条件。当条件满足时，可以执行指定的代码块。



**示例代码** *以下代码：在模态框中输入年龄，即可输出是否成年*

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title>js - if语句初识</title>
	</head>
	<body>
	</body>
	<script type="text/javascript">
		// 弹出提示框
		let age = prompt("姑娘，今年贵庚：")
		// 转换数字
		age = parseInt(age);
		// 判断一个年龄是否满足成年
		if(age > 17){
			alert('成年');
		}
	</script>
</html>

```

**效果图**

![效果图：](work\if1.gif)





#### if ... else 语句

---

在只有`if`语句的情况下，当条件不满足时，就不会有代码执行了。`else`语句则可以弥补，`if`语句条件不成立时的特殊情况。如：*年龄 <18 则为未成年，年龄 >17 则为成年*。

**语法**

```js
if (条件判断) {
  // 条件成立则执行 
} else {
  // 条件不成立则执行
}
```

**示例**

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title>js - if语句初识</title>
	</head>
	<body>
	</body>
	<script type="text/javascript">
		// 弹出提示框
		let age = prompt("姑娘，今年贵庚：")
		// 转换数字
		age = parseInt(age);
		// 判断一个年龄是否满足成年
		if(age > 17){
			alert('成年');
		}else{
			alert('未成年');
		}
	</script>
</html>

```

**效果**

![](work\if2.gif)



#### if ...elseif... else 语句

---

`if...else`语句适用于 *如果...否则...* 的情况。当出现 *如果...或者...否则* 的情况时，`if...else if()...else` 则更适合。如：*购买一件商品需要花费100或者扣除积分2000否则不能购买*

```js
if (条件判断A) {
  // 条件A成立则执行 
} else if(条件判断B) {
  // 条件B成立则执行
} else {
  // 所有条件不成立则执行
}
```



**示例代码**

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title>js - 购买商品</title>
	</head>
	<body>
	</body>
	<script type="text/javascript">
		let money = prompt('请输入您的金额');
		
		let score = prompt('请输入您的积分');
		
		if(money >= 100){
			alert('余额购买');
		}else if(score >= 2000){
			alert('积分购买');
		}else{
			alert('条件不符合，不能购买。');
		}
	</script>
</html>

```

**效果**

![](work\if3.gif)



**好言香串**：

	1. 当需要更多的 `或者` 时，则增加相应的`else if`即可
 	2. 代码从上往下自行，当`if`条件不成立时，才会执行`else if`的判断
 	3. 在多个`else if`条件判断中，按照位置进行顺序匹配，当其中一个`else if`条件成立时，在其之后`else if及else`都不会执行（有点像电路短路机制）
 	4. 独立`if`语句可以正常运行，`else`与`else if`不能离开`if`语句独立运行
 	5. 当`if`语句、`else if`语句、`else`语句对应代码块中只存在一行代码，可以不写`{}`



**if语句小知识**

```js
// 当if语句、else if语句、else语句对应代码块中只存在一行代码，可以不写`{}`
// 为了代码的阅读性，请不要省略`{}``
// 下面三句代码意思相等
// 1
if(score >=60) console.log('等分及格');
else console.log('得分不及格');
// 2
if(score >=60) 
    console.log('等分及格');
else 
    console.log('得分不及格');
// 3
if(score >=60){
    console.log('等分及格');
}else{
    console.log('得分不及格');
} 
```



#### 逻辑运算符

- `&&` — 逻辑与; 使得并列两个或者更多的表达式成为可能，只有当这些表达式每一个都返回`true`时，整个表达式才会返回`true.`
- `||` — 逻辑或; 当两个或者更多表达式当中的任何一个返回 `true` 则整个表达式将会返回 `true`.
- ! — 逻辑非; 对一个布尔值取反, 非true返回false,非false返回true.



















### 三目运算符

一个if简洁版版的条件判断语句

**语法**

```js
condition ? exprIfTrue : exprIfFalse
```

### switch语句

用于匹配等值判断的条件语句

**语法**

```js
switch (表达式) {
  case choice1:
    // 当表达式结果等于 choice1时，执行此代码块
    break;

  case choice2:
     // 当表达式结果等于 choice2时，执行此代码块
    break;
    
  default:
    // 当表达式结果与所有 case的值都不匹配时，则执行
}
```

#### 小知识

case对应语句需要增加执行的break，否则将会出现不在预期的错误。

### 嵌套控制

```js
// if嵌套
if(条件a){
	if(条件b){
		// 当条件a+条件b同时满足是则运行
	}
}
// 三目嵌套
条件1?条件2?表达式2-1:表达式2-2:表达式1-2
```





## 循环

重复执行某组动作或者重复完成某个任务

<img src="imgs\loop_js-02-farm-cn.png" style="zoom: 67%;" />



### while循环

```js
while (循环条件) {
  // 循环体
}
```

### do...while循环

```js
do {
  // 循环体
} while (循环条件)
```

### for循环

```js
for (初始语句; 循环条件; 迭代语句) {
  // 循环体
}
```

### 嵌套循环

```js
for (初始语句; 循环条件; 迭代语句) {
	for (初始语句2; 循环条件2; 迭代语句2) {
		// 循环体
	}
}
```





# 中场

## 数据类型判断

简介

**`typeof`** 操作符返回一个字符串，表示未经计算的操作数的类型。

### 语法

```js
typeof operand
typeof(operand)
```

**`operand`**

需要判断数据类型的`表达式`或者`对象`

### 常见类型及返回值

| 类型                                                         | 结果                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [Undefined](https://developer.mozilla.org/zh-CN/docs/Glossary/undefined) | `"undefined"`                                                |
| [Null](https://developer.mozilla.org/zh-CN/docs/Glossary/Null) | `"object"` (见[下文](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Operators/typeof#null)) |
| [Boolean](https://developer.mozilla.org/zh-CN/docs/Glossary/Boolean) | `"boolean"`                                                  |
| [Number](https://developer.mozilla.org/zh-CN/docs/Glossary/Number) | `"number"`                                                   |
| [BigInt](https://developer.mozilla.org/zh-CN/docs/Glossary/BigInt) | `"bigint"`                                                   |
| [String](https://developer.mozilla.org/zh-CN/docs/Glossary/字符串) | `"string"`                                                   |
| [Symbol](https://developer.mozilla.org/zh-CN/docs/Glossary/Symbol) (ECMAScript 2015 新增) | `"symbol"`                                                   |
| 宿主对象（由 JS 环境提供）                                   | *取决于具体实现*                                             |
| [Function](https://developer.mozilla.org/zh-CN/docs/Glossary/Function) 对象 (按照 ECMA-262 规范实现 [[Call]]) | `"function"`                                                 |
| 其他任何对象                                                 | `"object"`                                                   |



## 常量

一旦赋值就不能改变的变量

### **语法**

```js
const valName = val;
```



## 数组

用于多数据存储的特殊结构，数组需要通过索引（下标）进行数据的访问。

### **语法**

```js
[element0, element1, ..., elementN]
new Array(element0, element1[, ...[, elementN]])
new Array(arrayLength)
```

### 常用属性

| 属性名称                                                     | 属性含义               |
| ------------------------------------------------------------ | ---------------------- |
| [`length`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/length) | 返回当前数组的元素个数 |

### 常用函数

| 函数名称                                                     | 函数描述                                                     |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [`pop()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/pop) | 删除数组的最后一个元素，并返回这个元素。                     |
| [`push()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/push) | 在数组的末尾增加一个或多个元素，并返回数组的新长度。         |
| [`shift()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/shift) | 删除数组的第一个元素，并返回这个元素。                       |
| [`sort()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/sort) | 对数组元素进行排序，并返回当前数组。                         |
| [`unshift()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/unshift) | 在数组的开头增加一个或多个元素，并返回数组的新长度。         |
| [`slice()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/slice) | 抽取当前数组中的一段元素组合成一个新数组。                   |
| [`indexOf()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/indexOf) | 返回数组中第一个与指定值相等的元素的索引，如果找不到这样的元素，则返回 -1。 |
| [`lastIndexOf()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/lastIndexOf) | 返回数组中最后一个（从右边数第一个）与指定值相等的元素的索引，如果找不到这样的元素，则返回 -1。 |
| [`join()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/join) | 连接所有数组元素组成一个字符串。                             |
| [`splice()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/splice) | 在任意的位置给数组添加或删除任意个元素。                     |

### 迭代/遍历数组

```js
// for循环遍历
for(let i=0;i<arr.length;i++){
    console.log(arr[i]);
}
// for...in循环遍历
for(let i=0;i<arr.length;i++){
    console.log(arr[i]);
}
// 自带函数遍历
fruits.forEach(function (item, index, array) {
    console.log(item, index);
});
```



## 函数

### **简介**

**function**，**函数**，是一个可以被其他代码或其自身调用的代码片段，或者是一个指向该函数的[变量](https://developer.mozilla.org/en-US/docs/Glossary/variable) 。



一个**函数定义**（也称为**函数声明**，或**函数语句**）由一系列的[`function`](https://developer.mozilla.org/zh-CN/docs/JavaScript/Reference/Statements/function)关键字组成，依次为：

- 函数的名称。
- 函数参数列表，包围在括号中并由逗号分隔。
- 定义函数的 JavaScript 语句，用大括号`{}`括起来。



### **语法**

```js
function name([param,[, param,[..., param]]]) {
   [statements]
}
```

- `name`

  函数名

- `param`

  要传递给函数的参数的名称。不同引擎中的最大参数数量不同。

- `statements`

  包含函数体的语句。

### 创建

#### 具名函数

*自身拥有名字的函数*

```js
// 无参具名函数
function foo() {
    // 函数体
}
```

#### 匿名函数

自身没有名称的函数，需要通过引用调用或者执行运行

```js
function () {};
// 引用调用
var getDate = function (){
    // 方法体    
}

// 通过立即调用函数表达式可直接运行
(function(){
    // 方法体
})();
```

### 参数

```js
// 无参函数
function getDate(){
    // 方法体
}

// 带参函数
function getDiff(num){
   // 方法体 
}

// 带参函数，参数设置默认值
function getDiff(num=0){
    // 方法体
}
```

### 返回值

```js
// 无参无返回值函数
function getTime(){
    console.log('2019-12-01 00:00:00');
}

// 带参、返回值函数
function add(num1,num2){
	return num1+num2;
}

// 函数停止符
function scroeLevel(score){
    if(score <0){
        return 0;
    }
}
```



```js

```





# 收场

## JSON

描述： [JSON](https://developer.mozilla.org/zh-CN/docs/Glossary/JSON) (JavaScript Object Notation, JS 对象简谱)  是一种按照JavaScript对象语法的数据格式  虽然它是基于 JavaScript 语法，但它独立于JavaScript。 JSON可以作为一个对象或者字符串存在，前者用于解读 JSON 中的数据，后者用于通过网络传输 JSON 数据。 

#### 语法

```js
// JSON字符串   xml数据

// 简单JSON
let jsonStr ='{"now" : "2020-02-20"}';

// 包含数组JSON
jsonStr ='{"now" : "2020-20-20" , "month":[1,2,3,4,5,6,7,8,9,10,11,12]}';

// json嵌套
jsonStr = '{"today":{"year":2020,"month":02,"day":02},"yesterday":{"year":2020,"month":02,"day":01}}';
```

#### 注意事项

- JSON 是一种纯数据格式，它只包含属性，没有方法。
- JSON 要求有两头的 { } 来使其合法。最安全的写法是有两边的括号，而不是一边。
- 甚至一个错位的逗号或分号就可以导致  JSON 文件出错。
- JSON 可以将任何标准合法的 JSON 数据格式化保存，不只是数组和对象。比如，一个单一的字符串或者数字可以是合法的 JSON 对象。虽然不是特别有用处……
- 不像 JavaScript 标识符可以用作属性，在 JSON 中，只有字符串才能用作属性。





## 对象(结构)    不是oop的对象

对象是一个包含相关数据和方法的集合（通常由一些变量和函数组成，我们称之为对象里面的属性和方法）

![](imgs\person-diagram.png)

#### 语法

```js
// 简单变量
let name = '张三';
let age = 18;
let addresses = ['广州白云','广州番禺'];

// 简单对象
let Account = {
    name : '永带妹',
    age: 24,
    addresses: ['后山小屋','木叶村一角'],
    sayHi: function(){
        alert('我的名字是'+this.name+",很高兴认识你。");
    },
    sayHi: function(n){
        alert('很高兴认识你，'+n);
    }
};

// 复杂对象
let zyt = {
    name: '祝英台',
    sex: '女',
    age: 17
}

let lsb = {
    name: '梁山伯',
    sex: '男',
    age:18,
    girlFirend = zyt;
}
```

#### 对象使用

```js
// 访问对象的属性
Account.name;
Account.addresses[0];
Account['name'];

// 访问对象的方法
Account.sayHi();


// 修改对象中的属性值
Account.name = '一打七';
```

#### 增加/删除属性

```js
let Person ={
    name: null,
    sex: null
}

// 删除属性
delete Person.name;

// 动态增加属性
Person.age = 18;

```







提示：

1. 在一个对象定义同名属性或函数时，后者将会覆盖前者







## 作用域

**作用域**就是变量与函数的可访问范围,即**作用域**控制着变量与函数的可见性和生命周期。 

### 全局作用域

任何地方都能访问到的对象拥有全局作用域。比如window对象

```js
window.console.log('早睡早起，身体棒棒~');

```



### 局部作用域

只在固定的代码片段内可访问到。比如函数，for循环。

```js
// 代码块作用域（for，if等块状代码类似）
{
    let age = 19;
    {
        let age=26;
        console.log('内 年龄：',age);
    }
    console.log('外 年龄：'age);
}

// 函数作用域
function showTime(){
    let now = new Date();
	console.log('内 - 当前时间：',now);   
}
console.log('外 - 当前时间：',now); // 代码错误
```





#### var 和let的区别

### this关键字

在绝大多数情况下，函数的调用方式决定了`this`的值。`this`不能在执行期间被赋值，并且在每次函数被调用时`this`的值也可能会不同。

-  在对象方法中， this 指向调用它所在方法的对象。
-  单独使用 this，它指向全局(window)对象。   
-  函数使用中，this 指向函数的所属者。
-  严格模式下函数是没有绑定到 this 上，这时候 this 是 undefined。
-  在 HTML 事件句柄中，this 指向了接收事件的 HTML 元素。
-  apply 和 call 允许切换函数执行的上下文环境（context），即 this 绑定的对象，可以将 this 引用到任何对象。



#### 全局环境

在全局执行环境中（在任何函数体外部）`this` 都指向全局对象。

```js
// 在浏览器中, window 对象同时也是全局对象：
console.log(this === window); // true

a = 37;
console.log(window.a); // 37

this.b = "MDN";
console.log(window.b)  // "MDN"
console.log(b)         // "MDN"
```



## DOM

DOM（Document Object Model——文档对象模型）是用来呈现以及与任意 HTML 或 XML文档交互的API。DOM 是载入到浏览器中的文档模型，以节点树的形式来表现文档，每个节点代表文档的构成部分



### 获取标签

| 函数名称                                                     | 描述                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [`getElementById(String id)`](https://developer.mozilla.org/zh-CN/docs/Web/API/Document/getElementById) | 返回一个匹配特定 [ID](https://developer.mozilla.org/en-US/docs/DOM/element.id)的标签.由于标签的 ID 在大部分情况下要求是独一无二的，这个方法自然而然地成为了一个高效查找特定元素的方法。 |
| [`querySelector()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Document/querySelector) | 返回文档中与指定选择器或选择器组匹配的第一个 html标签[`Element`](https://developer.mozilla.org/zh-CN/docs/Web/API/Element)。 如果找不到匹配项，则返回`null`。 |
| [`querySelectorAll()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Document/querySelectorAll) | 返回与指定的选择器组匹配的文档中的元素列表 (使用深度优先的先序遍历文档的节点)。返回的对象是 [`NodeList`](https://developer.mozilla.org/zh-CN/docs/Web/API/NodeList) 。<br />**注意：** 如果`selectors`参数中包含 [CSS伪元素](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)，则返回的列表始终为空。 |
| [`getElementsByTagName()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Document/getElementsByTagName) | 返回一个包括所有给定标签名称的元素的HTML集合[`HTMLCollection`](https://developer.mozilla.org/zh-CN/docs/Web/API/HTMLCollection)。 |
| [`getElementsByClassName()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Document/getElementsByClassName) | 返回一个包含了所有指定类名的子元素的类数组对象。             |

### 属性操作

| 函数名称                                                     | 描述                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [`getAttribute()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Element/getAttribute) | 返回元素上一个指定的属性值。如果指定的属性不存在，则返回  `null` 或 `""` （空字符串）； |
| [`getAttributeNames()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Element/getAttributeNames) | 返回一个[`Array`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Array)，该数组包含指定元素（Element）的所有属性名称，如果该元素不包含任何属性，则返回一个空数组。 |
| [`hasAttribute()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Element/hasAttribute) | 返回一个布尔值，指示该元素是否包含有指定的属性（attribute）  |
| [`removeAttribute()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Element/removeAttribute) | 从指定的标签中删除一个属性。                                 |
| [`setAttribute()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Element/setAttribute) | 设置指定元素上的某个属性值。如果属性已经存在，则更新该值；否则，使用指定的名称和值添加一个新的属性。 |

### 标签小知识

- 获取输入框内的值

  ```js
  input.value;
  ```

- 获取下拉框中的所有项

  ```js
  HTMLSelectElement.options;
  ```

- 获取下拉框选择项的下标

  ```js
  HTMLSelectElement.selectedIndex;
  ```

- 获取/修改标签内容

  ```js
  element.innerText;
  ```

- 获取/修改标签的子标签 

  ```
  elemetn.innerHTML;
  ```

- 

### 操作CSS及class

```js
// 在单个语句中设置多个样式
elt.style.cssText = "color: blue; border: 1px solid black"; 
// 或者
elt.setAttribute("style", "color:red; border: 1px solid blue;");

// 设置特定样式，同时保持其他内联样式值不变
elt.style.color = "blue"; 
elt.style.marginLeft = "10px";

// 设置class
div.className = 'red bk'

// 注意: 以下方法，IE浏览器不支持
// 增加一个或多个class
div.classList.add("anotherclass");
div.classList.add("foo", "bar", "baz");
// 移除一个或多个class
div.classList.remove("foo");
div.classList.remove("foo", "bar", "baz");
// 判断class是否存在
div.classList.contains("foo");

```

### 事件

#### 浏览器事件

##### 加载事件

当网页的标签加载完成时触发

**语法**

```js
window.onload = funcRef;
```

##### 滚动条事件

元素的 `scroll `事件处理函数。

**语法**

```js
element.onscroll = functionReference
```

#### 常见事件

| 事件名称                                                     | 描述                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [`onclick`](https://developer.mozilla.org/zh-CN/docs/Web/API/GlobalEventHandlers/onclick) | 点击事件                                                     |
| [`ondblclick`](https://developer.mozilla.org/zh-CN/docs/Web/API/GlobalEventHandlers/ondblclick) | 双击事件                                                     |
| [`onfocus`](https://developer.mozilla.org/zh-CN/docs/Web/API/GlobalEventHandlers/onfocus) | 得到焦点事件                                                 |
| [`onblur`](https://developer.mozilla.org/zh-CN/docs/Web/API/GlobalEventHandlers/onblur) | 失去焦点事件                                                 |
| [`onkeydown`](https://developer.mozilla.org/zh-CN/docs/Web/API/GlobalEventHandlers/onkeydown) | 键盘按下事件                                                 |
| [`onkeypress`](https://developer.mozilla.org/zh-CN/docs/Web/API/GlobalEventHandlers/onkeypress) | 按键按住事件（连续触发。）除 Shift、Fn、CapsLock 外的任意键以外 |
| [`onkeyup`](https://developer.mozilla.org/zh-CN/docs/Web/API/GlobalEventHandlers/onkeyup) | 按键释放事件                                                 |
| [`onmouseenter`](https://developer.mozilla.org/zh-CN/docs/Web/API/GlobalEventHandlers/onmouseenter) | 鼠标进入事件                                                 |
| [`onmouseleave`](https://developer.mozilla.org/zh-CN/docs/Web/API/GlobalEventHandlers/onmouseleave) | 鼠标离开事件                                                 |
| [`onchange`](https://developer.mozilla.org/zh-CN/docs/Web/API/GlobalEventHandlers/onchange) | 改变事件                                                     |

### 创建

通过下列语句可以创建一个html标签

```js
var element = document.createElement(tagName[, options]);
```

### 新增

```js
/*
	
    insertedNode 已经经过插入newNode的新的节点
    parentNode 新插入节点的父节点
    newNode 用于插入的节点
    referenceNode newNode 将要插在这个节点之前

如果 referenceNode 为 null 则 newNode 将被插入到子节点的末尾。
*/
// 在共同父节点内的指定节点前插入行的节点
var insertedNode = parentNode.insertBefore(newNode, referenceNode);

/*
    parentNode 新插入节点的父节点
    newNode 用于插入的节点
*/
// 将一个节点附加到指定父节点的子节点列表的末尾处。
parentNode.appendChild(newNode)
```

### 删除

```js
/*
	
    child 是要移除的那个子节点.
    node 是child的父节点.
    oldChild保存对删除的子节点的引用. oldChild === child.

*/
let oldChild = node.removeChild(child);

//OR

element.removeChild(child);
```

更多事件名称请移步MDN网址：https://developer.mozilla.org/zh-CN/docs/Web/Events



## 定时器

描述：用于定时任务上，比如轮播图，倒计时，动画...

### setTimeOut

设置一个计时器，一旦计时器到期，该计时器将执行功能或指定的代码段。

```js
// 开启定时器器
var timeoutID = window.setTimeout(function[, delay, arg1, arg2, ...]);
var timeoutID = window.setTimeout(function[, delay]);
var timeoutID = window.setTimeout(code[, delay]);

// 清除/取消定时器
window.clearTimeout(timeoutID);
```

### setInterval

重复调用一个函数或执行一个代码段，在每次调用之间具有固定的时间延迟。

```js
// 开启重复任务
var intervalID = window.setInterval(func, delay, [arg1, arg2, ...]);
var intervalID = window.setInterval(code, delay);

// 清除重复调用
window.clearInterval(intervalID);
```





## 异常处理

### Error对象

描述： 当运行时错误产生时，Error的实例对象会被抛出，error对象出现后，js代码将会停止运行。Error对象也可用于用户自定义的异常的基础对象。 

#### 常见Error类型

| **[`SyntaxError`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/SyntaxError)** | 创建一个error实例，表示错误的原因：[`eval()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/eval)在解析代码的过程中发生的语法错误。 |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| **[`TypeError`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/TypeError)** | 创建一个error实例，表示错误的原因：变量或参数不属于有效类型。 |
| **[`ReferenceError`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/ReferenceError)** | 创建一个error实例，表示错误的原因：无效引用。                |
| **[`RangeError`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/RangeError)** | 创建一个error实例，表示错误的原因：数值变量或参数超出其有效范围。 |
| **[`URIError`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/URIError)** | 创建一个error实例，表示错误的原因：给 [`encodeURI()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/encodeURI)或 [`decodeURl()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/decodeURI)传递的参数无效。 |
| **[`EvalError`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/EvalError)** | 创建一个error实例，表示错误的原因：与 [`eval()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/eval) 有关。 |

#### 构建一个异常

```js
/*
	message	异常信息
	fileName 异常产生的文件名*   【属性未形成标准】
	lineNumber 异常产生的行号*	  【属性未形成标准】
*/
new Error([message[, fileName[,lineNumber]]])
```



#### 扔出一个异常

```js
/*
	位于异常扔出后的代码，不可被执行
*/
throw new Error('错误信息');
```



#### 判断一个异常的类型

```js
/*

	instanceof用于判断一个变量是否为某一种类型，注意不能使用instanceof去判断一个字面量变量
*/
try{
    // 代码
}catch(e){
    if(e instanceof RangeError){
        
    }
}
```



#### 构建自定义异常

```js
// 构建一个异常函数
function MyError(message) {
  this.name = 'MyError';
  this.message = message || 'Default Message';
  this.stack = (new Error()).stack;
}
// 将MyError与Js的Error基础对象关联（类似于继承）
MyError.prototype = Object.create(Error.prototype);
// 将MyError函数设置为MyError对象的构造函数
MyError.prototype.constructor = MyError;
```





### try...catch语句

描述：包含一段可能会出现异常的代码块，并在出现异常时执行相应捕获操作

语法变换：

1. `try...catch`
2. `try...finally`
3. `try...catch...finally`

```js

/*
try_statements	需要被执行的语句。
catch_statements_1	如果在try块里有异常被抛出时执行的语句。
exception_var_1	用于保存关联catch子句的异常对象的标识符。
finally_statements	在try语句块之后执行的语句块。无论是否有异常抛出或捕获这些语句都将执行。
*/

try {
   try_statements
}
[catch (exception_var_1) {
   catch_statements_1
}]
[finally {
   finally_statements
}]
```





## Ajax

 **AJAX**即“**Asynchronous JavaScript and XML**”（异步的[JavaScript](https://zh.wikipedia.org/wiki/JavaScript)与[XML](https://zh.wikipedia.org/wiki/XML)技术），指的是一套综合了多项技术的[浏览器](https://zh.wikipedia.org/wiki/瀏覽器)端[网页](https://zh.wikipedia.org/wiki/網頁)开发技术。 



### tcp小知识

#### 好基友，握握手

![](imgs\Image2001.gif)

[^https://wiki.mikrotik.com/wiki/Manual:Connection_oriented_communication_(TCP/IP)]: 图片摘自mikrotik



#### HTTP信息

---



##### 请求 / 请求头

---



<img src="C:/Users/mo/Desktop/md/jquery/imgs/request_header.png"  />

![](C:/Users/mo/Desktop/md/jquery/imgs/request_header2.png)



##### 响应 / 响应头

---

![](C:/Users/mo/Desktop/md/jquery/imgs/response_header.png)



#### 基友的状态

 TTP 响应状态代码指示特定 [HTTP](https://developer.mozilla.org/zh-cn/HTTP) 请求是否已成功完成。响应分为五类：信息响应(`100`–`199`)，成功响应(`200`–`299`)，重定向(`300`–`399`)，客户端错误(`400`–`499`)和服务器错误 (`500`–`599`)。 

##### 信息响应

| 状态码 | 状态描述                                                     |
| ------ | ------------------------------------------------------------ |
| 100    | 这个临时响应表明，迄今为止的所有内容都是可行的，客户端应该继续请求，如果已经完成，则忽略它。 |
| 101    | 该代码是响应客户端的 [`Upgrade`](https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Headers/Upgrade) 标头发送的，并且指示服务器也正在切换的协议。 |
| 102    | 此代码表示服务器已收到并正在处理该请求，但没有响应可用。     |
| 103    | 此状态代码主要用于与[`Link`](https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Headers/Link) 链接头一起使用，以允许用户代理在服务器仍在准备响应时开始预加载资源。 |

##### 成功响应

| 状态码                   | 描述                                                         |
| ------------------------ | ------------------------------------------------------------ |
| 200                      | 请求成功。                                                   |
| 201                      | 该请求已成功，并因此创建了一个新的资源。这通常是在POST请求，或是某些PUT请求之后返回的响应。 |
| 202                      | 请求已经接收到，但还未响应，没有结果。意味着不会有一个异步的响应去表明当前请求的结果，预期另外的进程和服务去处理请求，或者批处理。 |
| 203                      | 服务器已成功处理了请求，但返回的实体头部元信息不是在原始服务器上有效的确定集合，而是来自本地或者第三方的拷贝。当前的信息可能是原始版本的子集或者超集。例如，包含资源的元数据可能导致原始服务器知道元信息的超集。使用此状态码不是必须的，而且只有在响应不使用此状态码便会返回200 OK的情况下才是合适的。 |
| 204                      | 服务器成功处理了请求，但不需要返回任何实体内容，并且希望返回更新了的元信息。响应可能通过实体头部的形式，返回新的或更新后的元信息。如果存在这些头部信息，则应当与所请求的变量相呼应。如果客户端是浏览器的话，那么用户浏览器应保留发送了该请求的页面，而不产生任何文档视图上的变化，即使按照规范新的或更新后的元信息应当被应用到用户浏览器活动视图中的文档。由于204响应被禁止包含任何消息体，因此它始终以消息头后的第一个空行结尾。 |
| 205                      | 服务器成功处理了请求，且没有返回任何内容。但是与204响应不同，返回此状态码的响应要求请求者重置文档视图。该响应主要是被用于接受用户输入后，立即重置表单，以便用户能够轻松地开始另一次输入。与204响应一样，该响应也被禁止包含任何消息体，且以消息头后的第一个空行结束。 |
| 206                      | 服务器已经成功处理了部分 GET 请求。类似于 FlashGet 或者迅雷这类的 HTTP 下载工具都是使用此类响应实现断点续传或者将一个大文档分解为多个下载段同时下载。该请求必须包含 Range 头信息来指示客户端希望得到的内容范围，并且可能包含 If-Range 来作为请求条件。 |
| 207(WebDAV)              | 由WebDAV(RFC 2518)扩展的状态码，代表之后的消息体将是一个XML消息，并且可能依照之前子请求数量的不同，包含一系列独立的响应代码。 |
| 208(WebDAV)              | 在 DAV 里面使用: propstat 响应元素以避免重复枚举多个绑定的内部成员到同一个集合。 |
| 226(HTTP Delta encoding) | 服务器已经完成了对资源的 GET 请求，并且响应是对当前实例应用的一个或多个实例操作结果的表示。 |

##### 重定向

| 状态码 | 描述                                                         |
| ------ | ------------------------------------------------------------ |
| 300    | 被请求的资源有一系列可供选择的回馈信息，每个都有自己特定的地址和浏览器驱动的商议信息。用户或浏览器能够自行选择一个首选的地址进行重定向。 |
| 301    | 被请求的资源已永久移动到新位置，并且将来任何对此资源的引用都应该使用本响应返回的若干个 URI 之一。如果可能，拥有链接编辑功能的客户端应当自动把请求的地址修改为从服务器反馈回来的地址。除非额外指定，否则这个响应也是可缓存的。 |
| 302    | 请求的资源现在临时从不同的 URI 响应请求。由于这样的重定向是临时的，客户端应当继续向原有地址发送以后的请求。只有在Cache-Control或Expires中进行了指定的情况下，这个响应才是可缓存的。 |
| 303    | 对应当前请求的响应可以在另一个 URI 上被找到，而且客户端应当采用 GET 的方式访问那个资源。这个方法的存在主要是为了允许由脚本激活的POST请求输出重定向到一个新的资源。 |
| 304    | 如果客户端发送了一个带条件的 GET 请求且该请求已被允许，而文档的内容（自上次访问以来或者根据请求的条件）并没有改变，则服务器应当返回这个状态码。304 响应禁止包含消息体，因此始终以消息头后的第一个空行结尾。 |
| 307    | 请求的资源现在临时从不同的URI 响应请求。由于这样的重定向是临时的，客户端应当继续向原有地址发送以后的请求。只有在Cache-Control或Expires中进行了指定的情况下，这个响应才是可缓存的。 |
| 308    | 这意味着资源现在永久位于由 `Location:` HTTP Response 标头指定的另一个 URI。 这与 `301 Moved Permanently HTTP` 响应代码具有相同的语义，但用户代理不能更改所使用的 HTTP 方法：如果在第一个请求中使用 `POST`，则必须在第二个请求中使用 `POST`。 |

##### 客户端响应

| 状态        | 描述                                                         |
| ----------- | ------------------------------------------------------------ |
| 400         | 1、语义有误，当前请求无法被服务器理解。除非进行修改，否则客户端不应该重复提交这个请求。2、请求参数有误。 |
| 401         | 当前请求需要用户验证。该响应必须包含一个适用于被请求资源的 WWW-Authenticate 信息头用以询问用户信息。客户端可以重复提交一个包含恰当的 Authorization 头信息的请求。如果当前请求已经包含了 Authorization 证书，那么401响应代表着服务器验证已经拒绝了那些证书。如果401响应包含了与前一个响应相同的身份验证询问，且浏览器已经至少尝试了一次验证，那么浏览器应当向用户展示响应中包含的实体信息，因为这个实体信息中可能包含了相关诊断信息。 |
| 403         | 服务器已经理解请求，但是拒绝执行它。与 401 响应不同的是，身份验证并不能提供任何帮助，而且这个请求也不应该被重复提交。如果这不是一个 HEAD 请求，而且服务器希望能够讲清楚为何请求不能被执行，那么就应该在实体内描述拒绝的原因。当然服务器也可以返回一个 404 响应，假如它不希望让客户端获得任何信息。 |
| 404         | 请求失败，请求所希望得到的资源未被在服务器上发现。没有信息能够告诉用户这个状况到底是暂时的还是永久的。假如服务器知道情况的话，应当使用410状态码来告知旧资源因为某些内部的配置机制问题，已经永久的不可用，而且没有任何可以跳转的地址。404这个状态码被广泛应用于当服务器不想揭示到底为何请求被拒绝或者没有其他适合的响应可用的情况下。 |
| 405         | 请求行中指定的请求方法不能被用于请求相应的资源。该响应必须返回一个Allow 头信息用以表示出当前资源能够接受的请求方法的列表。 鉴于 PUT，DELETE 方法会对服务器上的资源进行写操作，因而绝大部分的网页服务器都不支持或者在默认配置下不允许上述请求方法，对于此类请求均会返回405错误。 |
| 406         | 请求的资源的内容特性无法满足请求头中的条件，因而无法生成响应实体。 |
| 407         | 与401响应类似，只不过客户端必须在代理服务器上进行身份验证。代理服务器必须返回一个 Proxy-Authenticate 用以进行身份询问。客户端可以返回一个 Proxy-Authorization 信息头用以验证。 |
| 408         | 请求超时。客户端没有在服务器预备等待的时间内完成一个请求的发送。客户端可以随时再次提交这一请求而无需进行任何更改。 |
| 409         | 由于和被请求的资源的当前状态之间存在冲突，请求无法完成。这个代码只允许用在这样的情况下才能被使用：用户被认为能够解决冲突，并且会重新提交新的请求。该响应应当包含足够的信息以便用户发现冲突的源头。 |
| 410         | 被请求的资源在服务器上已经不再可用，而且没有任何已知的转发地址。这样的状况应当被认为是永久性的。如果可能，拥有链接编辑功能的客户端应当在获得用户许可后删除所有指向这个地址的引用。如果服务器不知道或者无法确定这个状况是否是永久的，那么就应该使用 404 状态码。除非额外说明，否则这个响应是可缓存的。 |
| 411         | 服务器拒绝在没有定义 `Content-Length` 头的情况下接受请求。在添加了表明请求消息体长度的有效 `Content-Length` 头之后，客户端可以再次提交该请求。 |
| 412         | 服务器在验证在请求的头字段中给出先决条件时，没能满足其中的一个或多个。这个状态码允许客户端在获取资源时在请求的元信息（请求头字段数据）中设置先决条件，以此避免该请求方法被应用到其希望的内容以外的资源上。 |
| 413         | 服务器拒绝处理当前请求，因为该请求提交的实体数据大小超过了服务器愿意或者能够处理的范围。此种情况下，服务器可以关闭连接以免客户端继续发送此请求。如果这个状况是临时的，服务器应当返回一个 `Retry-After` 的响应头，以告知客户端可以在多少时间以后重新尝试。 |
| 414         | 请求的URI 长度超过了服务器能够解释的长度，因此服务器拒绝对该请求提供服务。这比较少见，通常的情况包括：本应使用POST方法的表单提交变成了GET方法，导致查询字符串（Query String）过长。 |
| 415         | 对于当前请求的方法和所请求的资源，请求中提交的实体并不是服务器中所支持的格式，因此请求被拒绝。 |
| 416         | 如果请求中包含了 Range 请求头，并且 Range 中指定的任何数据范围都与当前资源的可用范围不重合，同时请求中又没有定义 If-Range 请求头，那么服务器就应当返回416状态码。 |
| 417         | 此响应代码意味着服务器无法满足 [`Expect`](https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Headers/Expect) 请求标头字段指示的期望值。 |
| 418         | 服务器拒绝尝试用 `“茶壶冲泡咖啡”`。                          |
| 421         | 该请求针对的是无法产生响应的服务器。 这可以由服务器发送，该服务器未配置为针对包含在请求 URI 中的方案和权限的组合产生响应。 |
| 422(WebDAV) | 请求格式良好，但由于语义错误而无法遵循。                     |
| 423(WebDAV) | 正在访问的资源被锁定。                                       |
| 424(WebDAV) | 由于先前的请求失败，所以此次请求失败。                       |
| 425 | 服务器不愿意冒着风险去处理可能重播的请求。                   |
| 426 | 服务器拒绝使用当前协议执行请求，但可能在客户机升级到其他协议后愿意这样做。 服务器在 426 响应中发送 [`Upgrade`](https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Headers/Upgrade) 头以指示所需的协议。 |
| 428 | 原始服务器要求该请求是有条件的。 旨在防止“丢失更新”问题，即客户端获取资源状态，修改该状态并将其返回服务器，同时第三方修改服务器上的状态，从而导致冲突。 |
| 429         | 用户在给定的时间内发送了太多请求（“限制请求速率”）           |
| 431 |服务器不愿意处理请求，因为它的 请求头字段太大（ Request Header Fields Too Large）。 请求可以在减小请求头字段的大小后重新提交|
|451|用户请求非法资源，例如：由政府审查的网页。|

##### 服务端响应

| 状态码      | 描述                                                         |
| ----------- | ------------------------------------------------------------ |
| 500         | 服务器遇到了不知道如何处理的情况。                           |
| 501         | 此请求方法不被服务器支持且无法被处理。只有`GET`和`HEAD`是要求服务器支持的，它们必定不会返回此错误代码。 |
| 502         | 此错误响应表明服务器作为网关需要得到一个处理这个请求的响应，但是得到一个错误的响应。 |
| 503         | 服务器没有准备好处理请求。 常见原因是服务器因维护或重载而停机。 请注意，与此响应一起，应发送解释问题的用户友好页面。 这个响应应该用于临时条件和 `Retry-After`：如果可能的话，HTTP头应该包含恢复服务之前的估计时间。 网站管理员还必须注意与此响应一起发送的与缓存相关的标头，因为这些临时条件响应通常不应被缓存。 |
| 504         | 当服务器作为网关，不能及时得到响应时返回此错误代码。         |
| 505         | 服务器不支持请求中所使用的HTTP协议版本。                     |
| 506         | 服务器有一个内部配置错误：对请求的透明内容协商导致循环引用。 |
| 507         | 服务器有内部配置错误：所选的变体资源被配置为参与透明内容协商本身，因此不是协商过程中的适当端点。 |
| 508(WebDAV) | 服务器在处理请求时检测到无限循环。                           |
| 510         | 客户端需要对请求进一步扩展，服务器才能实现它。服务器会回复客户端发出扩展请求所需的所有信息。 |
| 511         | 511 状态码指示客户端需要进行身份验证才能获得网络访问权限。   |



#### 请求方式  method

| 方式    | 描述                                                         |
| ------- | ------------------------------------------------------------ |
| GET     | GET方法请求一个指定资源的表示形式. 使用GET的请求应该只被用于获取数据.(搜索，明文) |
| HEAD    | HEAD方法请求一个与GET请求的响应相同的响应，但没有响应体.     |
| POST    | POST方法用于将实体提交到指定的资源，通常导致在服务器上的状态变化或副作用.（登录，密文） |
| PUT     | PUT方法用请求有效载荷替换目标资源的所有当前表示。            |
| DELETE  | DELETE方法删除指定的资源。                                   |
| CONNECT | CONNECT方法建立一个到由目标资源标识的服务器的隧道。          |
| OPTIONS | OPTIONS方法用于描述目标资源的通信选项。                      |
| TRACE   | TRACE方法沿着到目标资源的路径执行一个消息环回测试。          |
| PATCH   | PATCH方法用于对资源应用部分修改。                            |





### XMLHttpRequest对象

`XMLHttpRequest`（XHR）对象用于与服务器交互。通过 XMLHttpRequest 可以在不刷新页面的情况下请求特定 URL，获取数据。这允许网页在不影响用户操作的情况下，更新页面的局部内容。 



#### 构建及发送

```js
// 创建xhr对象(支持绝大部分浏览器)
let ajax = new XMLHttpRequest();  

//针对性创建
// IE6
ajax = new ActiveXObject("Msxml2.XMLHTTP");
// IE5及以下
ajax = new ActiveXObject('Microsoft.XMLHTTP');



// 构建请求
/*
	method 	为http请求方式
	url		为http请求地址
	async	为该请求是否为异步请求（默认为true）
*/
ajax.open(method, url);
ajax.open(method, url, async);

/*
当ajax使用get方法请求url时，应该将参数拼接在url中所以send(null)
~~~~~~~~~post~~~~~~~~~~~~，可以设置ajax的请求内容类型来使用send(数据)来发送数据

// 键值对
ajax.setRequestHeader('Content-Type','application/x-www-form-urlencoded');
ajax.send('cityId=653100');

// json
ajax.setRequestHeader('Content-Type','application/json');
ajax.send('{"cityId":653100}');

未设置请求头的Content-Type，send()参数，后台可能无法正确解析

设置 HTTP 请求头的值。必须在 open() 之后、send() 之前调用 setRequestHeader() 方法。

*/
ajax.send(param);

```

#### 监听及获取数据

```js
// onreadystatechange ： 当 readyState 属性发生变化时，事件被触发(IE5+)

ajax.onreadystatechange = function(){
    if(ajax.readyState == ajax.DONE){
        if(ajax.status == 200){
            console.log('拉取的数据为：',ajax.responseText);
            let resObj = JSON.parse(ajax.responseText);
            console.log('后台拉回的数据:',resObj);
        }
    }
}

// onload 在readState = 4时被触发（IE9+）
ajax.onload=function(){
    console.log('状态变化:',ajax.readyState);
    if(ajax.status == 200){
        console.log('拉取的数据为：',ajax.response);
        console.log('拉取的数据为：',ajax.responseText);
        let resObj = JSON.parse(ajax.responseText);
        console.log('后台拉回的数据:',resObj);
    }
    
}
```



#### 异常、超时处理

```js
// 设置超时时间（单位、毫秒）
ajax.timeout = 20; // ie8+
		
// 超时回调
ajax.ontimeout =function(){  // ie10+
    console.log('请求超时了');
}

//取消ajax请求
setTimeout(function(){
    ajax.abort()
},1);
```





#### 小知识

##### readState状态

| 值   | 状态               | 描述                                                |
| ---- | ------------------ | --------------------------------------------------- |
| `0`  | `UNSENT`           | 代理被创建，但尚未调用 open() 方法。                |
| `1`  | `OPENED`           | `open()` 方法已经被调用。                           |
| `2`  | `HEADERS_RECEIVED` | `send()` 方法已经被调用，并且头部和状态已经可获得。 |
| `3`  | `LOADING`          | 下载中； `responseText` 属性已经包含部分数据。      |
| `4`  | `DONE`             | 下载操作已完成。                                    |



### FormData对象 IE10+

 **`FormData`** 接口提供了一种表示表单数据的键值对 `key/value` 的构造方式，并且可以轻松的将数据通过[`XMLHttpRequest.send()`](https://developer.mozilla.org/zh-CN/docs/Web/API/XMLHttpRequest/send) 方法发送出去。 如果送出时的编码类型被设为 `"multipart/form-data"`，它会使用和表单一样的格式。 

#### 常用属性或函数

| 属性或名称              | 描述                                                         |
| ----------------------- | ------------------------------------------------------------ |
| new Form([formElement]) | 构造一个新的表单数据对象                                     |
| delete(k)`ie不支持`     | 删除一个键值对。                                             |
| entries()`ie不支持`     | 包含所有键值对的[`iterator`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Iteration_protocols)对象 |
| get(k)`ie不支持`        | 返回在 `FormData` 对象中与给定键关联的第一个值。             |
| getAll(k)`ie不支持`     | 返回一个包含 `FormData` 对象中与给定键关联的所有值的数组。   |
| has()`ie不支持`         | 否包含某些键。                                               |
| keys()                  | 所有键的[`iterator`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Iteration_protocols)对象。 |
| set(k,v)`ie不支持`      | 给 `FormData` 设置属性值，如果`FormData` 对应的属性值存在则覆盖原值，否则新增一项属性值。 |
| values()`ie不支持`      | 返回一个包含所有值的[`iterator`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Iteration_protocols)对象。 |
| append(k,v)`ie10+`      | 向 `FormData` 中添加新的属性值，`FormData` 对应的属性值存在也不会覆盖原值，而是新增一个值，如果属性不存在则新增一项属性值。 |

#### 遍历数据[es6]

```js
// for   of循环将会一对对抽取formData中的数据
for(let kv of formData){
    console.log('key:',kv[0],', value:',kv[1]);
}
```



### 二进制文件







## 本地存储

js提供 `localStorage`  及 `sessionStorage`  两个对象给用户对浏览器写入和读取自定义数据（键值对的形式）。 本地存储为每一个给定的源（given origin）维持一个独立的存储区域 。



### localStorage

`localStorage`提供永久性数据存储， 比使用 cookie 更加直观 。

### sessionStorage

`sessionStorage`提供数据存储，但是存储在 `sessionStorage` 里面的数据在页面会话结束时会被清除（关闭页面的时候）。 



**Stroage对象函数及属性**

| 属性或函数         | 描述                                                       |
| ------------------ | ---------------------------------------------------------- |
| length             | 返回一个整数，表示存储在 `Storage` 对象中的数据项数量。    |
| getItem(key)       | 返回键名对应的值                                           |
| setItem(key,value) | 将会把键值对添加到存储中，如果键名存在，则更新其对应的值。 |
| removeItem(key)    | 把该键名从存储中删除。                                     |
| clear()            | 该方法会清空存储中的所有键名。                             |

提示：

1. sessionStorage与localStorage的数据不相通
2. 浏览器清除数据会把本地存储的数据清除
3. 不同域名的存储是不同区域的
4. key在storage是唯一的



# 常用对象及其函数

描述：JS对开发人员提供更方便的对象操作（字符串截取，获取标签...）

[^https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects]: 对象链接



## 标准内置对象

### String

#### 字符串模板（ES6）

```js
`string text`

`string text line 1
 string text line 2`

`string text ${expression} string text`

tag `string text ${expression} string text`


let name ='张三丰';
let age = 100;
// 变量获取例子
let temp1 = `我的名字是：${name}，今年${age}岁。`
// 变量及表达式例子
let temp2 = `我的名字是：${name}，今年${age}岁，再过三年我就${age+3}岁了。`

```

#### 字符串拼接

```js
// 通过 + 号连接
let desc = "JavaScript ( JS ) 是一种具有函数优先的轻量级，解释型或即时编译型的编程语言。 " +
                 " JavaScript 的标准是 ECMAScript 。" +
                 "不要将 JavaScript 与 Java编程语言 混淆。";
// 
let desc = "JavaScript ( JS ) 是一种具有函数优先的轻量级，解释型或即时编译型的编程语言。 \
JavaScript 的标准是 ECMAScript 。\
不要将 JavaScript 与 Java编程语言 混淆。";
```



#### 构建方式

```js
/*
	1.使用字面量的构建方式与对象构建方式在使用上无差别，两者的数据类不相同所以不要用===来判断
*/

let str = "JavaScript真好玩，我要学习。";  // 字面量构建方式
let str2 = String('JavaScript真好用，我要学习。');
let str3 = new String('JavaScript真简单，我要学习。');  // 对象构建方式
```

#### 常用函数

| 函数或属性                                                   | 描述                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [`length`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/length) | 返回了字符串的长度。                                         |
| [`endsWith()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/endsWith) | 判断一个字符串的是否以给定字符串结尾，结果返回布尔值。       |
| [`startsWith()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/startsWith) | 判断字符串的起始位置是否匹配其他字符串中的字符。             |
| [`indexOf()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/indexOf) | 从字符串对象中返回首个被发现的给定值的索引值，如果没有找到则返回-1。 |
| [`lastIndexOf()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/lastIndexOf) | 从字符串对象中返回最后一个被发现的给定值的索引值，如果没有找到则返回-1。 |
| [`replace()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/replace) | 被用来在正则表达式和字符串直接比较，然后用新的子串来替换被匹配的子串。 |
| [`split()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/split) | 通过分离字符串成字串，将字符串对象分割成字符串数组。         |
| [`substring()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/substring) | 返回在字符串中指定两个下标之间的字符。                       |
| [`toLowerCase()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/toLowerCase) | 将字符串转换成小写并返回。                                   |
| [`toUpperCase()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/toUpperCase) | 将字符串转换成大写并返回。                                   |
| [`trim()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/trim) | 从字符串的开始和结尾去除空格。                               |
| [`slice()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String/slice) | 摘取一个字符串区域，返回一个新的字符串。                     |



### Date

描述：JS使用Date对象表示系统时间，Date对象可以获取时间戳及其他单位时间

构建方式

```js
new Date(); // 以当前的系统时间作为基础，返回一个时间对象
new Date(value); // 以某一个时间点来创建一个时间
new Date(dateString); //以时间字符串来创建一个新的时间对象
new Date(year, monthIndex [, day [, hours [, minutes [, seconds [, milliseconds]]]]]); // 指定年月日来创建一个时间
```

| 函数名称                                                     | 描述                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [`now()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date/now) | 返回自 1970-1-1 00:00:00  UTC（世界标准时间）至今所经过的毫秒数。 |
| [`getDate()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date/getDate) | 根据本地时间返回指定日期对象的月份中的第几天（1-31）。       |
| [`getDay()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date/getDay) | 根据本地时间返回指定日期对象的星期中的第几天（0-6）。        |
| [`getFullYear()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date/getFullYear) | 根据本地时间返回指定日期对象的年份（四位数年份时返回四位数字）。 |
| [`getHours()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date/getHours) | 根据本地时间返回指定日期对象的小时（0-23）。                 |
| [`getMilliseconds()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date/getMilliseconds) | 根据本地时间返回指定日期对象的毫秒（0-999）。                |
| [`getMinutes()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date/getMinutes) | 根据本地时间返回指定日期对象的分钟（0-59）。                 |
| [`getMonth()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date/getMonth) | 根据本地时间返回指定日期对象的月份（0-11）。                 |
| [`getSeconds()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date/getSeconds) | 根据本地时间返回指定日期对象的秒数（0-59）。                 |
| [`getTime()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date/getTime) | 返回从1970-1-1 00:00:00 UTC（协调世界时）到该日期经过的毫秒数，对于1970-1-1 00:00:00 UTC之前的时间返回负值。 |

### Math

它拥有一些数学常数属性和数学函数方法。

| 函数或属性                                                   | 描述                                                 |
| ------------------------------------------------------------ | ---------------------------------------------------- |
| [`PI`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/PI) | 圆周率，一个圆的周长和直径之比，约等于 `3.14159`。   |
| [`ceil(x)`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/ceil) | 返回大于一个数的最小整数，即一个数向上取整后的值。   |
| [`floor(x)`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/floor) | 返回小于一个数的最大整数，即一个数向下取整后的值。   |
| [`max([x[, y[, …\]]])`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/max) | 返回零到多个数值中最大值。                           |
| [`min([x[, y[, …\]]])`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/min) | 返回零到多个数值中最小值。                           |
| [`random()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/random) | 返回一个 0 到 1 之间的伪随机数。                     |
| [`round(x)`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/round) | 返回四舍五入后的整数。                               |
| [`trunc(x)`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/trunc) | 返回一个数的整数部分，直接去除其小数点及之后的部分。 |



### JSON

| 函数或属性                                                   | 描述                                                     |
| ------------------------------------------------------------ | -------------------------------------------------------- |
| [parse()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/parse) | 以文本字符串形式接受JSON对象作为参数，并返回相应的对象。 |
| [stringify()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify) | 接收一个对象作为参数，返回一个对应的JSON字符串。         |



## 全局对象

#### Window

`window`作为全局变量，代表了脚本正在运行的窗口，暴露给 Javascript 代码。



| 函数或属性                                                   | 描述                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [`console`](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/console)`只读` | 返回 console 对象的引用，该对象提供了对浏览器调试控制台的访问。 |
| [`document`](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/document)`只读` | 返回对当前窗口所包含文档的引用。                             |
| [`history`](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/history)`只读` | 返回一个对 history 对象的引用。                              |
| [`innerHeight`](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/innerHeight)`只读` | 获得浏览器窗口的内容区域的高度，包含水平滚动条(如果有的话)。 |
| [`innerWidth`](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/innerWidth)`只读` | 获得浏览器窗口的内容区域的宽度，包含垂直滚动条(如果有的话)。 |
| [`outerHeight`](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/outerHeight)`只读` | 返回浏览器窗口的外部高度。                                   |
| [`outerWidth`](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/outerWidth)`只读` | 返回浏览器窗口的外部宽度。                                   |
| [`location`](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/location) | 获取、设置 window 对象的 location, 或者当前的 URL.           |
| [`localStorage`](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/localStorage)`只读` | 返回用来存储只能在创建它的源下访问的数据的本地存储对象的引用 |
| [`pageXOffset`](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/scrollX)/[`scrollX`](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/scrollX)`只读` | 返回文档/页面水平方向滚动的像素值。                          |
| [`pageYOffset`](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/scrollY)/[`scrollY`](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/scrollY)`只读` | 返回文档在垂直方向已滚动的像素值。                           |
| [`alert()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/alert) | 弹出一个警告框                                               |
| [`close()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/close) | 关闭当前标签页面（注意：该方法只能由 [`Window.open()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/open) 方法打开的窗口的 `window` 对象来调用。如果一个窗口不是由脚本打开的，那么，在调用该方法时，JavaScript 控制台会出现类似下面的错误：`不能使用脚本关闭一个不是由脚本打开的窗口。` 或 `Scripts may not close windows that were not opened by script.` 。） |
| [`confirm()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/confirm) | 显示一个具有一个可选消息和两个按钮(确定和取消)的模态对话框   |



##### 小知识

- innerHeight与outerHeight的区别(备注：innerWidth与outerWidth区别与之类似)
  ![](imgs\FirefoxInnerVsOuterHeight2.png)



### History

**`window.history`**是一个只读属性，用来获取[`History`](https://developer.mozilla.org/zh-CN/docs/Web/API/History) 对象的引用，[`History`](https://developer.mozilla.org/zh-CN/docs/Web/API/History) 对象提供了操作浏览器*会话历史*



| 函数或属性                                                   | 描述                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [`back()`](https://developer.mozilla.org/zh-CN/docs/Web/API/History/back) | 前往上一页, 用户可点击浏览器左上角的返回按钮模拟此方法. 等价于 `history.go(-1)`. |
| [`forward()`](https://developer.mozilla.org/zh-CN/docs/Web/API/History/forward) | 在浏览器历史记录里前往下一页，用户可点击浏览器左上角的前进按钮模拟此方法. 等价于 `history.go(1)`. |
| [`go()`](https://developer.mozilla.org/zh-CN/docs/Web/API/History/go) | 通过当前页面的相对位置从浏览器历史记录( 会话记录 )加载页面。比如：参数为-1的时候为上一页，参数为1的时候为下一页. 当整数参数超出界限时。例如: 如果当前页为第一页，前面已经没有页面了，我传参的值为-1，那么这个方法没有任何效果也不会报错。调用没有参数的 `go() `方法或者不是整数的参数时也没有效果。( 这点与支持字符串作为url参数的IE有点不同)。 |

### Location

**`Location `**接口表示其链接到的对象的位置（URL）。



| 函数或属性                                                   | 描述                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [`href`](https://developer.mozilla.org/zh-CN/docs/Web/API/Location/href) | 包含整个URL的一个[`DOMString`](https://developer.mozilla.org/zh-CN/docs/Web/API/DOMString)或者指定跳转位置 |
| [`search`](https://developer.mozilla.org/zh-CN/docs/Web/API/Location/search) | 包含URL参数的一个[`DOMString`](https://developer.mozilla.org/zh-CN/docs/Web/API/DOMString)，开头有一个`“?”`。 |
| [`reload()`](https://developer.mozilla.org/zh-CN/docs/Web/API/Location/reload) | 重新加载来自当前 URL的资源。他有一个特殊的可选参数，类型为 [`Boolean`](https://developer.mozilla.org/zh-CN/docs/Web/API/Boolean)，该参数为true时会导致该方法引发的刷新一定会从服务器上加载数据。如果是 `false`或没有制定这个参数，浏览器可能从缓存当中加载页面。 |

# 常用函数（持续更新）

js自带常用函数

| 函数名称                                                     | 阐述                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [`isNaN()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/isNaN) | `**isNaN()**`函数判断一个值是否是[`NaN`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/NaN)。 |
| [`parseInt()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/parseInt) | `**parseInt()**` 函数解析字符串参数，并返回指定的基数（基础数学中的数制）的整数。 |
| [`parseFloat()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/parseFloat) | `**parseFloat()**` 函数解析字符串参数，并返回一个浮点数。    |
| [`decodeURI()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/decodeURI) | 解码由[`encodeURI`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/encodeURI) 创建或其它流程得到的统一资源标识符（URI） |
| [`encodeURI()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/encodeURI) | 函数通过将特定字符的每个实例替换为一个、两个、三或四转义序列来对统一资源标识符 (URI) 进行编码 (该字符的 UTF-8 编码仅为四转义序列)由两个 "代理" 字符组成)。 |

   



