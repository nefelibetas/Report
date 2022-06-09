### 数字进制

八进制 0~7，写法：数字前+0

十六进制0~9及A~F，写法：数字前+0x；



#### 数字型Number

最大值：**1.7976931348623157e+308**

最小值: **5e-324**

~~~js
alert(Number.MAX_VAlUE);  
//1.7976931348623157e+308
alert(Number.MIN_VALUE);  
//5e-324
~~~



###### 数字型的三个特殊值

~~~js
alert(Infinity); 
//infinity无穷大

alert(-infinity);  
//-Infinity无穷小

alert(NaN);  
//NaN非数值
~~~



###### 转换为数字型

parseInt(string) 例： parseInt('字符串')   //转换为整形

parseFloat(string) 例：parseFloat('字符串')   //转换为浮点型

强制转换Number(string) 例：Number('字符串')

隐式转换（- * /） 例：console.log('字符串'-0);  //此处字符串得是数字才行

~~~js
var num='123'
parseInt(num);
//123
parseFloat(num);
//123
Number(num);
//123
console.log(num-0);
//123
~~~



###### 函数

isNaN(变量名)

变量是数字，返回false;  //true参与加法则视为1

变量不是数字，返回true;  //false参与加法则视为0

~~~js
var x='123';
var y=123;
console.log(isNaN(x));
//true
console.log(isNaN(y));
//false
~~~



typeof函数，用法:typeof 变量

例：

~~~js
var num=10;

console.log(typeof num); //number
console.log(typeof undefined) //undefined
console.log(typeof null) //null
~~~



undefined类型：undefined    null类型：object

