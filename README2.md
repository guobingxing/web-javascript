# JavaScript 2

标签（空格分隔）： 脚本语言

---

##1、数组
###**（1）索引数组 index array** 下标是数字

创建：
数组直接量：var arr = [元素1，元素2，...];
用new：var arr = new Array(元素1，元素2，...);

设置数组的值——SET：下标**从0开始**，最大到 length-1
var scores=[95,88,100];
scores[2]=98; //将值为100的元素重新赋值为98
scores[3]=75; //在数组尾部添加一个新的元素

获取数组的值——GET：
var cities = new Array('南京'，'杭州'，'青岛')；
console.log(cities[1]);  //杭州
console.log(cities[3]);  //undefined

访问数组中的元素——length：
var arr4 = new Array(10);
console.log(arr4.length); //长度为10

var arr5 = []; //长度为0
arr5[0] = 87; //长度为1
arr5[3] = 98; //长度为4

数组的遍历：元素下标从0开始到length-1结束
```
var nums = [50,90,20,10];
for(var i=0; i< nums.length;i++){
    nums[i]+=10;
}
```

固定套路：
获取数组最后一个元素：arr[arr.length-1]
获取数组倒数第n个元素：arr[arr.length-n]

###**（2）关联数组 Associative Array** 下标可自定义 
创建：
```
var bookInfo = [];
bookInfo['bookName']='西游记';
bookInfo['price']=35.5;
```

遍历关联数组：for in 循环 ， 快速查找元素
```
for(var key in hash){
    key; // 下标名
    hash[key];  //元素值
}
```

----------

##2、数组API函数
###（1）数组转字符串
固定套路：
**1> 将字符组成单词：chars.join(""); //无缝拼接
    判断空数组：arr.join("")==""
2> 将单词组成句子：words.join("");
3> 将数组转化为页面元素的内容：
    "<开始标签>"+
    arr.join("<结束标签><开始标签>")
    +"<结束标签>"**

###(2)拼接和选取：不直接修改原数组，而返回新数组！

拼接：concat() 拼接两个或多个数组并返回结果
var new Arr = arr1.concat(值1，值2，arr2，值3，...)

选取：slice() 返回现有数组的一个子数组
var subArr=arr.slice(starti,endi+1)

###(3)修改数组

删除：splice 直接修改原数组
arr.splice(starti,n)

插入：
arr.splice(starti,0,值1，值2，...)

替换：
arr.splice(starti,n,值1，值2，...)

###(4)颠倒数组
颠倒：reverse() 颠倒数组中元素的顺序
arr.reverse();
```
var arr1 = [10,20,30,40,50];
arr1.reverse();

console.log(arr1);
```
###(5)排序：将元素从小到大排序
arr.sort(): 默认将所以元素转为字符串在排列


----------

##3、DOM查找
|常用DOM方法|
|-|
|getElementById()|
|getElementsByTagName()|
|getElementsByClassName()|
|appendChild()|
|removeChild()|
|replaceChild()|
|inserBefore()|
|createAttribute()|
|createElement()|
|creatTextNode()|
|getAttribute|
|setAttribute|

###(1)按id属性
精确查找一个元素
var elem=document.getElementById("id")
```
<ul id="myLise">
        <li id="m1"></li>
        <li id="m2"></li>
        <li id="m3"></li>
</ul>
```
```
var elem=document.getElementById("myLise");
console.log(ul);
```
###(2)按标签名
返回一个动态集合，可查找所有子代节点
var elems=parent.getElementsByTagName("tag")
```
<ul id="myLise">
        <li id="m1"></li>
        <li id="m2"></li>
        <li id="m3"></li>
</ul>
```
```
var ul=document.getElementById("myLise");
var list=ul.getElementsByTagName("li");
console.log(list);
```
###(3)通过name属性查找
document.getElementsByName("name属性值")
```
<form id="registerForm">
        <input type="checkbox" name="boy" />
        <input type="checkbox" name="boy" />
        <input type="checkbox" name="boy" />
</form>
```
```
var list=document.getElementsByTagName("boy");
console.log(typeof list);
```
###(4)通过class查找
查找父元素下指定的class属性的元素
var elems=parent.getElementsByClassName("class")
有兼容性问题：IE9+
```
<div id="news">
        <p class="mainTitle"></p>
        <p class="subTitle"></p>
        <p class="mainTitle"></p>
</div>
```
```
var div=document.getElementById("news");
var list=div.getElementsByClassName("mainTitle");
console.log(list);
```
###(5)通过css选择器查找
####1> 只找一个元素：
var elem=parent.querySelector("selector")

####2> 找多个：
var elems=parent.querySelectorAll("selector")


###实操：随机码
```
<style>
    #code{
        width: ;
        height: ;
        background-color: ;
    }
</style>
```
```
<script>
    function createRndCode(){
        var chars = ['a','b','c','1','2','3'];
        var randCode = "";
        for(var i=0;i<3;i++){
            var randPos = Math.floor(Math.random()*(chars.length-1));
            randCode += chars[randPos];
        }
        document.getElementById("code").innerHTML = randCode;
    }
</script>
<div id="code"></div>
<button onclick="createRndCode()">验证码</button>
```


##4、DOM修改
###（1）修改
|核心DOM|HTML DOM|
|-|-|
|包含HTML和XML|仅对复杂的API进行了简化|
|可操作一切结构化文档的API|专门操作HTML文档的简化版DOM API|
|万能，繁琐|非万能，简单|
开发：先简单后繁琐

###（2）修改属性
核心DOM的4个操作：

1、读取属性值：
var value=elem.getAttribute("属性名")；

2、修改属性值：
elem.setAttribute("属性名"，value);
```
var h1 = document.getElementById("a1");
h1.setAttributeNode("name",zhangji);
```
3、判断是否包含指定属性：
var bool=elem.hasAttribute("属性名")；
```
document.getElementById('bt1').hasAttribute('onclick');
```
4、移除属性：
elem.removeAttribute("属性名")；
```
<a id="alink" class="slink" href="javascript:void(0)" onclick="jump()">百度搜索</a>
```
```
var a = document.getElementById('alink');
a.removeAttribute('class');
```

###(3)修改样式
内联元素：elem.style.属性名
强调：属性名：去横线，变驼峰
例:
css:
background-color  =>  backgroundColor
list-style-type  =>  listStyleType

##5、DOM添加

###（1）创建空元素
var elem=document.createElement("元素名")

###（2）设置关键属性
1、设置关键属性
a.innerHTML="go to tmooc";
a.href="http://tmooc.cn";
```
<a href="http://tmooc.cn">go to tmooc</a>
```
2、设置关键样式
a.style.opacity = "1";
a.style.cssText = "width: 100px; height: 100px";

###（3）将元素添加到DOM树
parentNode.insertBefore(newChild,existingChild)
用于在父元素中的指定字节点 之前 添加一个新的子节点
```
<ul id="menu">
    <li>首页</li>
    <li>联系我们</li>
</ul>
```
```
var ul = document.getElementById("menu");
var newLi = document.createElement("li");

ul.inserBefore(newLi,ul,lastChild);
```

文档片段：内存中，临时保存多个平级子元素的 虚拟父元素 
1、创建片段
var frag=document.createDocumentFragment();

2、将子元素临时追加到 frag 中
frag.appendChild(child);

3、将 frag 追加到页面
parent.appendChild(frag);


##6、BOM
1、浏览器对象模型
|window|代表整个窗口|
|-|-|
|history|封装当前窗口打开后，成功访问过的历史 url 记录|
|navigator|封装浏览器配置信息|
|document|封装当前正在加载的网页内容|
|location|封装了当前窗口正在打开的 url 地址|
|screen|封装了屏幕的信息|
|event|定义了网页中的事件机制|

2、获取当前窗口大小
完整窗口大小：window.outerWidth / outHeight
文档显示区大小：window.innerWidth / innerHeight


###**定时器**
####1、周期性定时器

（1）语法
**setlnterval(exp,time)**
exp:执行语句
time：周期，单位 毫秒
```
var timer = setlnterval(function(){
    console.log("hello world");
},1000);
```
（2）停止定时器
```
clearlnterval(timer);
```
####2、一次性定时器
（1）语法
**setTimeout(exp,time)**
exp:执行语句
time：间隔时间，单位 毫秒
```
var timer = setTimeout(function(){
    alert("恭喜过关");
},3000);
```
