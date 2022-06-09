## 对象

1.自定义对象 2. 内置对象 3.浏览器对象（JS特有）

### 自定义对象

对象是一组无序的相关属性的方法的集合，所有的事物都是对象。

**属性**：外在性质

**方法**：能实现的功能

将一个对象的属性和方法封装起来构成一个完整的对象信息

#### 创建对象方法

1.**对象字面量**：{}

书写规范：![image-20220414145443731](D:\报告\Report\pic\/image-20220414145443731.png) 对象内部可以包装方法（函数)。

~~~js
var obj=
{
    uname:'name',
    age:18,
    sex:'male',
    log:function()
    {
        for(var i in obj)//定义一个变量来储存对象内部元素
        {
          	console.log(i);
            //得到变量名
          	console.log(obj[i]);
            //得到变量的保存内容
        }
    }
}

~~~



不同的地方：不需要声明变量变量就可以直接使用，并且独属于这个对象。

但是函数仍然需要声明

注意，逗号隔开；

![image-20220414145652494](D:\报告\Report\pic\/image-20220414145652494.png) 

同C++结构体和类，不同的：

![image-20220414145750644](D:\报告\Report\pic\/image-20220414145750644.png) 

~~~js
console.log(obj['age'])
//单独取age元素的值
~~~



2.**new创建**

类似创建数组的方法 Object

![image-20220414150441390](D:\报告\Report\pic\/image-20220414150441390.png) 

~~~js
var obj=new Object();
obj.uname='name';
obj.age=18;
obj.sex='male';
obj.say=function()
{
    for(var i in obj)//定义一个变量来储存对象内部元素
        {
          	console.log(i);
            //得到变量名
          	console.log(obj[i]);
            //得到变量的保存内容
        }
};
~~~

3.**构造函数创建**（类）

![image-20220414151754445](D:\报告\Report\pic\/image-20220414151754445.png) 

注意事项：函数名大写，this代表当前的，以免冲突。

~~~js
function people(name,age,sex)
{
    this.name=name;
    this.age=age;
    this.sex=sex;
}
var x=new people('name',18,'sex');
~~~

**new关键字**

创建空对象，然后用this会指向一个空对象（空内存区域）

#### 遍历对象属性

估计是面向对象特有：

![image-20220414154034428](D:\报告\Report\pic\/image-20220414154034428.png) 

~~~js
//遍历对象
for(var i in obj)
{
    console.log(i);
    //得到属性名
    console.log(obj[i]);
    //得到属性值
}
~~~



### 内置对象

自带的对象，类似于头文件

查就完了<a href="http://developer/mozilla.org/zh-CN/">MDN Web文档</a> 

#### Math对象

不是构造函数，直接调用

一些示例：

![image-20220416155346087](D:\报告\Report\pic\/image-20220416155346087.png) 

绝对值：![image-20220416155443980](D:\报告\Report\pic\/image-20220416155443980.png) 

取整：![image-20220416155623141](D:\报告\Report\pic\/image-20220416155623141.png) 

~~~js
var x=Math.PI;
var y=Math.sqrt(16);
~~~

四舍五入：

![image-20220416155821790](D:\报告\Report\pic\/image-20220416155821790.png) 

随机数：

![image-20220416160325413](D:\报告\Report\pic\/image-20220416160325413.png) 返回0到1之间的浮点数。

得到一定范围内的随机数（包含两头）![image-20220416160434622](D:\报告\Report\pic\/image-20220416160434622.png) 

~~~~js
function GetRandom(min,max)
{
    return Math.floor(Math.random()*(max-min+1))+min;
}
~~~~

-------



#### 日期(DATE)对象

构造函数，需要自行构造

使用：![image-20220416161217153](D:\报告\Report\pic\/image-20220416161217153.png) 没有参数就输出当前的时间

![image-20220416161519308](D:\报告\Report\pic\/image-20220416161519308.png) 

~~~js
var data1=new Date(2019,10,1);
console.log(data1);
//使用数字型会返回 月份+1 月
var data2=new Date('2019-10-1');
//输出正常
~~~

数字型输出的月份会大1，使用字符型可以准确输出

![image-20220416161810351](D:\报告\Report\pic\/image-20220416161810351.png) 

![image-20220416162205286](D:\报告\Report\pic\/image-20220416162205286.png) 

![image-20220416163128239](D:\报告\Report\pic\/image-20220416163128239.png) 

![image-20220416163656101](D:\报告\Report\pic\/image-20220416163656101.png) （日期格式化)

![image-20220416164438868](D:\报告\Report\pic\/image-20220416164438868.png) 

![image-20220416164756628](D:\报告\Report\pic\/image-20220416164756628.png) （首推)

![image-20220416164821461](D:\报告\Report\pic\/image-20220416164821461.png) （齐次)

![image-20220416165413820](D:\报告\Report\pic\/image-20220416165413820.png)![image-20220416165833419](D:\报告\Report\pic\/image-20220416165833419.png)

 倒计时案例原理：每个时间都是从1970年开始计数，所以到如今的每个毫秒都是独一无二的。利用这个特性可以做出倒计时的效果。即，让预定结束的时间减去当前时间。