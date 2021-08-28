# JavaScript Learning

## 变量入门

**变量就是存储数据的容器**

```javascript
var aa;  //声明变量
aa = 18; //赋值

//声明并赋值 一行
var age = 20;

//一次性声明多个变量并赋值
var h1 = 12, h2 = 13, h3 = 15;
```

## 变量命名规则

可以有：

- 数字
- 字母
- 下划线
- $

注意：

- ==不能以数字开头==
- ==不能是关键字（for white if....）==
- ==必须有意义==
- ==大小写敏感==
- ==如果变量重名，后面的会替换前面的==

**驼峰法**

> **小驼峰法：除第一个单词之外，其他单词首字母大写。**==变量一般用小驼峰法标识。==
>
> 譬如 
>
> ```js
> var myStudentCount;
> ```
>
> 变量 myStudentCount 第一个单词是全部小写，后面的单词首字母大写。

> **大驼峰法：相比小驼峰法，大驼峰法把第一个单词的首字母也大写了。**
>
> ==常用于类名，函数名，属性，命名空间。==
>
> 譬如
>
> ```js
> public class DataBaseUser;
> ```
>

## 交换变量值

```js
var a = 1;
var b = 2;
var c = a;

a = b;  //从右向左流动
b = c;
```

## 数据类型

- 数值 Number
- 字符串 String
- 布尔 Boolen（true、false）
- undefined
- null
- 对象 Object

### 字符串

```js
var name = 'lin' //使用单引号或双引号 引起来的就是字符串

//转义       \ -> 转义符号
var outPut = '你好，我是\'鞠亚\''
```

### 其他数据类型

```js
var s1 = '123';
console.log(s1.length); //在控制台输出 s1 的长度
```

![image-20210825211258495](/home/cattom/.config/Typora/typora-user-images/image-20210825211258495.png)

```js
var s1 = '123';
var s2 = '456';
var s3 = s1+s2 //字符串拼接
console.log(s3);

var s4 = 1;
console.log(s4+s3); //仍是字符串拼接

var s5 = 2;
console.log(s4+s5); //加法运算
```

+ +号既可以是数学加法运算 也可以是字符串拼接
+ 变量数据类型为数值时为加法运算
+ 变量数据类型为字符串时为字符串拼接
+ 从前往后进行运算

#### 布尔

ture false ==大小写敏感==

true 1

false 0

#### Undefined and Null

Undefined 表示一个声明了但没有赋值的变量

null 表示空，==变量的值若要想为null，必须手动设置==

## 注释

单行与多行

```js
// i'm cat tom

/*
  111
  111
*/
```

## 数据类型转换

### 转为字符串 (String)

#### 数值转为字符串

```js
var n = 5;
var s = n.toString(); // 数值转为字符串
console.log(typeof s); // typeof 显示数据类型

String(n); // 直接转化
```

##### 另外一种方式

```js
var n = 5;
var s = ''+n;  // 空字符串+数值（n）原数值（n）变字符串
console.log(typeof s);
```

#### 布尔转为字符串

```js
var n = true;
console.log(typeof n.toString());  //使用 .toString() 的方法
```

#### 字符串转为数值

```js
var a = '1';
var b = Number(a); // 注意这里
console.log(b);
```

### 转为数值

#### 其一

**Number()**

```js
var c = Number('c');
var d = Number(null);
var e = Number(undefined);

console.log(c,d,e);
```

![image-20210827132950812](/home/cattom/.config/Typora/typora-user-images/image-20210827132950812.png)

==NaN -> Not a Number.==

#### 其二

**parseInt()  -  整数**

```js
var a = parseInt('2');
var b = parseInt('k23');
var c = parseInt(null);
var d = parseInt(undefined);

console.log(a,b,c,d);
```

![image-20210827150040145](/home/cattom/.config/Typora/typora-user-images/image-20210827150040145.png)

#### 其三

**parseFloat()  -  浮点**

```js
var a = parseFloat('1.23df');
var b = parseFloat('1.3.4.5');
var c = parseFloat('h34');
var d = parseFloat(null);
var e = parseFloat(undefined);

console.log(a,b,c,d,e);
```

![image-20210827150824197](/home/cattom/.config/Typora/typora-user-images/image-20210827150824197.png)

### 转为布尔

```js
var a = Boolean('0');  // 字符串
var b = Boolean(0);  // 数值
var c = Boolean('2');  // 字符串（非 0 1 ）
var d = Boolean(null);
var e = Boolean(undefined);
var f = Boolean(2); // 数值

console.log(a,b,c,d,e,f);
```

![image-20210827152818047](/home/cattom/.config/Typora/typora-user-images/image-20210827152818047.png)

**解释...**

> 字符串转布尔，只判断字符串是否为空，为空则 ***false*** ，否则为 ***true***
>
> 数值转布尔，**0** 则 ***false*** ，**1 或 以上** 则为 ***true***
>
> **null** 和 **undefined** 转布尔，二者表“空”的意思，则均为 ***false*** 

## 操作符

### 算数操作符

- 加（+）

- 减（-）

- 乘（*）

- 除（/）
- 取余数（%）

**表达式**：由 *值* 和 *操作符* 组成，运算有结果

**子表达式**：表达式中的每个数值及部分表达式

![image-20210827183612327](/home/cattom/.config/Typora/typora-user-images/image-20210827183612327.png)

```js
var s1 = 6;
var s2 = 3;

console.log(s1+s2);
```

### 一元运算符

适用于只有一个值的运算

对自身操作

==操作符在变量前，先进行自身运算，再进行其他运算==

==操作符在变量后，则反之==

```js
n1++  ++n1 //等价 n1+1
n1--  --n1 //等价 n1-1
```

Example 1：

```js
var n1 = 5;
++n1;
var n2 = 6;
console.log(n1+ ++n2); //等于13
console.log(n1+ n2++); //等于12
```

Example 2：

```js
var a = 1;
var b = ++a + a++;
console.log(b);  //等于4
```

Example 3：

```js
var a = 1;
var b = a++ + ++a;
console.log(b); //等于4
```

Example 4：

```js
var a = 1;
//       2  + 2+1
var b = ++a + ++a;
console.log(b); // 等于5
```

### 逻辑运算符（布尔运算符）

&&

与：两个操作数同时为 **true**，结果为 **true**，否则为 **false**

| |

或：两个操作数有一个为 **true**，结果则为 **true**，否则为 **false**

!

非：获取相反的结果

==在 JavaScript 中，逻辑运算的结果是决定整个表达式的子表达式的值==

==**运算优先级：先运算 && 再运算 ||**==

```js
var a = 1;
var b = 2;
var c = 0;

console.log(a && b);  //结果为2
console.log(c && b);  //结果为0

console.log(a || b);  //结果为1
console.log(a || c);  //结果为1

console.log(a || c && b);
```

### 关系运算符

大于号 >

小于号 <

大于等于号 >=

小于等于号 <=

### 相等运算符

等于 ==  **只比较值**

不等于 !=

全等于 ===  **比较值和数据类型**

不全等 !==

```js
var a = '2';
var b = 2;
console.log(a==b)
```

### 赋值运算

= 赋值

+= 加等于

-= 减等于

/= 除等于

%= 余数等于

```js
var a = 1;
a+=4; // 等价于 a = a+4
```

### 运算符的优先级

**从上到下**

1. ( )
2. 一元运算符 ++  --  !（非）
3. 算术运算符 先 * / % 后 + - 
4. 关系运算符
5. 相等运算符
6. 逻辑运算符  ==**运算优先级：先运算 && 再运算 ||**==
7. 赋值运算符

Example 1 :

```js
var s = 4>=6 || 'human' != 'haha' && !(12*2+3 == 122) && true;
console.log(s); // 结果为true
```

Example 2 :

```js
var n = 10;
var f = 5 == n / 2 && (2+2*n);
console.log(f); // 结果为22
```

## 流程控制

三种基本结构：

- 顺序结构：从上到下执行（默认）
- 分支结构：根据不同情况及判断，执行对应代码
- 循环结构：重复执行一段代码

### 分支结构

#### if语句

```js
if(判断条件){
    要执行的代码 // 条件成立代码执行
}else if(判断条件){
  // 前方哪个条件满足，哪个执行
  // 若前方代码已有代码执行，则后面的代码无论是否满足条件，均不执行
}else{
  // 若前面所有条件均不成立，则执行 else 部分的代码
}
```

Example 1 :

```js
var n1 = 100;
var n2 = 20;
if(n1>n2){
    console.log(n1);
}else{
    console.log(n2);
}
```

Example 2 :

```js
var n = 10;
if(n%2 == 0){
    console.log('偶数')
}else{
    console.log('奇数')
}
```

Example 3 - 判断某一年是不是闰年：

**闰年：能被4整除，但不能被100整除，亦或者是能被400整除**

```js
var Y = 2016;
if(Y%4 == 0){
    if(Y%100 != 0){
        console.log('闰年')
    }else if(Y%400 == 0){
        console.log('闰年')
    }else{
        console.log('平年')
    }
}else{
    console.log('平年')
}
```

#### switch - case 语句

```js
switch(值){
    case 值1:
        code;
        break;
    case 值2;
        code;
        break;
    default:
        code;
        break;
}
```

**依次判断 switch 中的值与每个 case 的值是否相等，相等则执行对应的代码，若均不相等则执行 default 中的代码**

**break: 判断若符合，执行代码，后跳出，不再继续判断**

Example 1 :

```js
var grade = 'B';
switch(grade){
    case 'A':
        console.log('90分以上');
        break;
    case 'B':
        console.log('80-90之间');
        break;
    case 'C':
        console.log('70-80之间');
        break;
    default:
        console.log('不及格');
        break;
}
```

