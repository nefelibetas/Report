#### 数组

##### 创建并初始化

![image-20220320135051706](D:\报告\Report\pic/image-20220320135051706.png) 

~~~js
var arr=new Array();
//new创建数组
var arr=[];
//字面量创建数组
~~~



![image-20220416171247677](D:\报告\Report\pic/image-20220416171247677.png) 

![image-20220416171340132](D:\报告\Report\pic/image-20220416171340132.png) 

~~~js
var arr=[1,2,3];
console.log(arr[0]);
//创建并且初始化
var arr1=new Array(2);
//创建一个长度为2的数组
var arr2=new Array(2,3);
//创建有两个元素的数组
~~~

JS数组与C不同（弱类型）![image-20220320135239289](D:\报告\Report\pic/image-20220320135239289.png)

##### 访问

此处同C语言，下标索引

##### 遍历

同C语言，循环加下标访问，循环遍历

##### 获取长度

用**length**函数

![image-20220320140019662](D:\报告\Report\pic/image-20220320140019662.png) 

~~~js
var arr=[];
for(int i=0;i<arr.length,i++)
{
    console.log(arr[i]);
}
~~~



具体如上

##### 新增

与c不同，数组的长度可以被随时修改

![image-20220412195448196](D:\报告\Report\pic/image-20220412195448196.png) ![image-20220412195454877](D:\报告\Report\pic/image-20220412195454877.png) 

~~~js
var arr=new Array(5);
arr.length=10;
//可以实时修改
~~~

##### 检测

![image-20220416172002292](D:\报告\Report\pic/image-20220416172002292.png) ![image-20220416172123966](D:\报告\Report\pic/image-20220416172123966.png) （H5新增)

~~~js
var arr=[];
//[]代表数组
var obj={};
//{}代表对象
console.log(arr instanceof Array)
//ture
console.log(obj instanceof Array);
//false
~~~

~~~js
console.log(Array.isArray(arr));
//true
console.log(Array.isArray(obj));
//false
~~~

第一种通用性更强

##### 元素操作

![image-20220416172330957](D:\报告\Report\pic/image-20220416172330957.png) 

前两个利用栈（栈顶操作），后两个在头部操作

push、pop返回的元素是添加的或者删除的元素

筛选：利用push(arr[i])进行原地数组操作减少空间开销

~~~js
var arr=[];
arr.push(1);
//变更后的长度
arr.pop();
//返回1，删除的元素

//把元素1压入（push）栈顶（数组尾部），然后用pop弹出

arr.unshift(1);
//返回变更后的长度
arr.shift();
//返回删除的元素

//把元素1在数组头加入（unshift），然后从数组头部取出一个元素（shift）
~~~



排序：![image-20220416184243055](D:\报告\Report\pic/image-20220416184243055.png) 

使用：![image-20220416184448920](D:\报告\Report\pic/image-20220416184448920.png) ![image-20220416184456671](D:\报告\Report\pic/image-20220416184456671.png) 

sort函数：会以首个数字的大小进行排序

解决方案：![image-20220416184717641](D:\报告\Report\pic/image-20220416184717641.png) 

~~~js
var arr=[1,2,3,4];
for(int i=0;i<arr.length,i++)
{
    console.log(arr[i]);
}
//输出1,2,3,4
arr.reverse();
for(int i=0;i<arr.length,i++)
{
    console.log(arr[i]);
}
//输出4,3,2,1

var points = [40,100,1,5,25,10];
points.sort(function(a,b){return a-b});
for(int i=0;i<points.length,i++)
{
    console.log(points[i]);
}
//正常排序数字

var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.sort();
for(int i=0;i<fruits.length,i++)
{
    console.log(fruits[i]);
}
//输出Apple,Banana,Mango,Orange

//默认按照字母升序排列

~~~



索引：

![image-20220416185209639](D:\报告\Report\pic/image-20220416185209639.png) 

 ![image-20220416185108857](D:\报告\Report\pic/image-20220416185108857.png) 找不到返回**-1** 

index从前方查找，lastindex从后方查找

~~~js
var arr=['red','green','blue','pink','blue'];
console.log(arr.indexOf('blue'));
//输出2，第一个blue被查询到就终止
console.log(arr.lastindexOf('blue'));
//输出4
~~~



其他：![image-20220417155519247](D:\报告\Report\pic\image-20220417155519247.png) 

~~~js
//concat();
var hege = ["Cecilie", "Lone"];
var stale = ["Emil", "Tobias", "Linus"];
var kai = ["Robin"];
var children = hege.concat(stale,kai);
for(int i=0;i<children.length,i++)
    console.log(children[i]);
//Cecilie,Lone,Emil,Tobias,Linus,Robin 

//slice()
var fruits = ["Banana", "Orange", "Lemon", "Apple", "Mango"];
var citrus = fruits.slice(1,3);
for(int i=0;i<citrus.length;i++)
    console.log(citrus[i]);
//Orange,Lemon

//splice()
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.splice(2,0,"Lemon","Kiwi"); 
for(int i=0;i<fruits.length;i++)
    console.log(fruits[i]);
//Banana,Orange,Lemon,Kiwi,Apple,Mango
~~~

