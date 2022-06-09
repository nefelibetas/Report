#### 函数

函数封装减少代码量，提高代码复用率。

##### 声明

1.关键词![image-20220412202021687](D:\报告\Report\pic\/image-20220412202021687.png) 

![image-20220412202029478](D:\报告\Report\pic\/image-20220412202029478.png) 

~~~js
function GetSum(num1,num2)
{
    var sum=0;
    for(int i=num1;i<=num2;i++)
        sum+=i;
    console.log(sum);
}
var num1,num2;
var x=new GetSum(num1,num2);
~~~

甚至不用定义关键字。

用function定义函数不论放在哪个位置优先被预解读，即定义放在函数后面函数也能生效。

2. var 匿名函数

   ![image-20220414130142295](D:\报告\Report\pic\/image-20220414130142295.png) 

   ![image-20220414130343126](D:\报告\Report\pic\/image-20220414130343126.png) 

   var声明区域讲究，必须放在函数调用前。

   ~~~~js
   var GetSum=function (num1,num2)
   {
       var sum=0;
       for(int i=num1;i<=num2;i++)
           sum+=i;
       console.log(sum);
   }
   var num1,num2;
   GetSum(num1,num2);
   ~~~~
   
   

注意点：

![image-20220412203610965](D:\报告\Report\pic\/image-20220412203610965.png)

![image-20220413113317696](D:\报告\Report\pic\/image-20220413113317696.png) 

##### argument

一种伪数组，将**实参传递**的“数组”

可以使用下标索引，存储方式也下标顺序存储。

![image-20220413114103403](D:\报告\Report\pic\/image-20220413114103403.png) 

会将输入的实参全部传递，类似指针传递，这里是输入了1,2,3.三个实参，那么argument“数组”就会有3个元素，下标从0到2来存储。

~~~js
function fn()
{
    console.log(arguments);
    console.log(arguments.length);
}
fn(1,2,3);
~~~

利用argument动态数组存储。

反转函数：![image-20220413115418255](D:\报告\Report\pic\/image-20220413115418255.png) 和c++ 里的reverse相同

####  块级作用域

就是  **{}**  内部的区间定义的函数其他区域不能使用过，**但是**，js**没**这种东西。

#### 作用域链

![image-20220414131920195](D:\报告\Report\pic\/image-20220414131920195.png) 

即**就近原则**

![image-20220414131933878](D:\报告\Report\pic\/image-20220414131933878.png) 

~~~js
var num=10;
function fn()
{
	var num=20;
    function fun()
    {
        console.log(num);
        //输出20；
    }
}
~~~

优先查找最近的变量

#### 预解析

![image-20220414134045366](D:\报告\Report\pic\/image-20220414134045366.png) 

声明优先，赋值正常。