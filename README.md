# JavaScript 1

标签（空格分隔）： 脚本语言

---

## 1、组成
核心（ECMA Script）
文档对象模型（DOM）
浏览器对象模型（BOM）


----------


## 2、添加方式
行内
script>内嵌</script>
script src="JS文件路径"></script>外部文件


----------


## 3、内容输出
### （1)使用 window.alert();  写入警告框
<script>
window.alert(5 + 6);
</script>
### （2)使用 document.write();  写入 HTML 输出 (仅用于测试)
<script>
document.write(5 + 6);
</script>
### （3)使用 innerHTML 写入 HTML 元素
<script>
 document.getElementById("id").innerHTML = 5 + 6;
</script>
### （4)使用 console.log() 写入浏览器控制台 （通过F12激活）
<script>
console.log(5 + 6);
</script>


----------


## 4、变量
### （1）语法
**var 变量名 = 值;**
**var 变量名1 = 值1; 变量名2 = 值2;...;**
若省略var则变成“全局变量”

### (2)变量名 命名规范
#### <1>不允许使用以下JS的关键字和保留关键字
<table>
<tr><td>break</td><td>case</td><td>catch</td><td>continue</td><td>default</td></tr>
<tr><td>delete</td><td>do</td><td>else</td><td>false</td><td>finally</td></tr>
<tr><td>for</td><td>function</td><td>if</td><td>in</td><td>instanceof</td></tr>
<tr><td>new</td><td>null</td><td>return</td><td>switch</td><td>this</td></tr>
<tr><td>throw</td><td>true</td><td>try</td><td>typeof</td><td>var</td></tr>
<tr><td>void</td><td>while</td><td>with</td><td>undefined</td><td>...</td></tr>
</table>
#### <2>不能以数字开头

### （3）变量的使用
var stuName="小猪佩奇"; 赋值需要 双引号
console.log(stuName); 输出值 小猪佩奇
变量需要赋值才能输出


----------


## 5、数据类型
### **（1）数字类型 number**
整数：32位 4字节
浮点数：即小数，64位 8字节

### **（2）字符串类型 string**
由 Unicode字符，数字，标点组成，占2字节
\u4e00: 汉字的起始字符
\u9fa5: 汉字的结束字符
转义字符：
1）\n 换行， 2）\r 回车，3）\t 一个制表符

### **（3）布尔类型 boolean**
作用：用于表示 条件的结果
取值：trun 真（1） ， false 假（0）

### **（4）空 null**
声明对象未赋值

### **（5）未定义 undefined**
声明变量未赋值，访问对象不存在的属性


----------


## 6、数据类型转换
### （1）弱类型
由数据来决定变量的数据类型

### （2）隐式转换（自动转换）
#### **1）函数**
var 变量名=值；
var s=typeof(变量名); 获取变量名的数据类型
var s1=typeof 变量名; 获取变量名的数据类型

#### **2）NaN**
Not a Number 不是一个数字
**isNaN（数据）**: 判断
结果为 trun：不是一个数字
结果为 false：是一个数字
**注：所有的数据类型与string做+运算时，最后的结果都为string**

#### **3）强制转换**

##### **1>语法：变量.toString();**
将任意类型的数据转换为string类型

##### **2>语法：var result = parseInt(数据);**
获取指定数据的整形部分
**注：从左至右依次转换，碰到第一个非整数字符则停止转换，若第一个字符就是非整数字符的话，结果为 NaN**

##### **3>语法：var result = parseFloat(数据);**
将指定数据转换成小数
ex:
    var result = parseFloat(35.25); //35.25
    var result = parseFloat(35.2你好); //35.2
    var result = parseFloat(你好35.2); //NaN
    
##### **4>语法：var result = Number(数据);**
将一个字符串解析为number
若包含非法字符则返回NaN


----------


## 7、运算符 & 表达式
### （1）算术运算符：
加（+）、减（-）、乘（*）、除（/）、求余（%）
取余操作，俗称 模；
ex： var i = 10 % 3；  // i = 1
用于判断数字奇偶性，获取数字最后几位

### （2）自增 & 自减
i=1;
j = i++ ;  // i = 2, j = 1
j = ++i ;  // i = 2, j = 2

###  (3)关系运算符
==  等于 ； !=  不等于 ； ===  全等 ； !==  不全等 ； >=  大于等于 ...
运算结果为 boolean类型

###  (4)逻辑运算符
#### **1）&&  与**
 两个条件都为真的时候 结果才为真；
 如果第一个条件为 false，则不会再判断第二个条件
 **var result = 条件1 && 条件2 ；**
 
#### **2) ||  或**
其中一个条件为真 结果就为真；
如果第一个条件为 turn，则不会再判断第二个条件
**var result = 条件1 || 条件2 ；**

#### **3) !  非** 
语法 ： ! 条件
非真即假

### （5）条件运算符
三目运算符：需要三个操作
语法：**表达式1？表达式2：表达式3；**
表达式1是 boolean类型；
若表达式1的值为 turn，则结果为 表达式2；
若表达式1的值为 false，则结果为 表达式3；


----------


## 8、函数
语法 & 调用 : 
**function 函数名（）{
    可执行语句；
}
函数名（）；**

### （1）定义带参数函数

### （2）带返回值的函数
**function 函数名（0或多个参数）{
    代码块；
    return 值；
}
var 变量 = 函数名（参数）；
console.log(变量)；**

### （3）变量的作用域

### （4）转换函数
parseInt(数据)； 将数据转换为 整数
paeseFloat(数据)； 将数据转换为 小数


----------


## 9、分支结构
### **（1）if-结构**
当条件满足时执行某些语句，
不满足时则 不执行这些语句。
**语法：
if（条件表达式）{
    语句块；
}**

### **（2）if-else 结构**
当条件满足时执行某些语句，
不满足时则 执行另一些语句。
**语法：
if（条件）{
    语句块1；
}else{
    语句块2；
}**

### **（3）else-if 结构**
**语法：
if（条件1）{
    语句块1；
}else if（条件2）{
    语句块2；
}...else{
    语句块n；
}**

### **（4）switch-case 结构**
将计算出来的值与case后的数值做 **等值判断**，若相等则执行对应后的语句
**语法：
switch（表达式）{
    case 值1:
        语句1；
        语句2；
    case 值2:
        语句3；
        ...
    default:
        语句n；
}**

### **（5）switch-case 和 break 联合使用**
break 的作用在于跳出switch 结构
**语法：
switch（表达式）{
    case 值1:
        语句1；
        语句2；
        break；
    case 值2:
        语句3；
        break；
        ...
    default:
        语句n；
}**

switch-case 结束机制：
1、碰到 break 结束；
2、没有 break 代码则以最后一块的 case 为主。


----------


## 10、循环结构
### （1）while 循环
循环为 turn 则执行循环，false 则退出循环

#### 1> continue 关键字
作用：终止本次循环 进入下次循环

#### 2> break 关键字
作用：终止整个循环结构

**语法：
while（boolean表达式）{
    循环体语句；
}**

### **（2）do-while 循环**
先循环 后判断，最少执行一次循环

语法：
do{
    可执行语句；
}while（boolean表达式）；

### **（3）for 循环**

**语法：
for（表达式1；表达式2；表达式3）{
    循环体语句；
}**

循环过程：
1、计算表达式1的值；
2、计算表达式2的值， turn 则循环，否则退出；
3、执行循环体；
4、执行表达式3；
5、计算表达式2，...
```
for（var i = 0 ; i<10 ; i++）{
    console.log(i);
}
```
