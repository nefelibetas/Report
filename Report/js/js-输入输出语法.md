#### 语法

##### 引入

1.< script src="xx.js"> < /script>  此方式双标签中间不写代码

2.行内式：直接写到元素内部、

< input type="button" value="" onclick="alert('')">

3.直接夹在两个script中

##### 声明变量

var 变量名  //声明一个变量 

var age=10; //数字型

var sex= '男'; //字符串

没声明直接赋值的，也是全局变量

**js是一种弱类型（动态）语言**,即不用提前声明变量类型，运行时会被自动确定。

**var作为关键字**



##### 输入、输出、警示

输入 prompt（info）  浏览器弹出输入框，用户输入，一般用变量接收   var myname=prompt(' ');

~~~javascript
var myname=prompt('');
~~~



输出console.log(msg)  浏览器控制台输出信息  console.log(变量名)  即可在控制台输出

~~~javascript
console.log(myname);
~~~



与c语言不同的是，输出语句会把例句的内容全当字符串。
**例如：console.log('age岁，是个');不会识别age为变量，而当字符串。**
**解决: console.log(age+'岁，是个');**

~~~js
console.log('age岁');
//输出结果是字符串，而不是变量的值
console.log(age+'岁');
//输出结果正常，为变量的值
~~~



警示 alert(msg)  浏览器弹出警示框  onclick="alert(' ')"  跳出提醒框，弹出内容写在  **' '**  内

~~~js
onclick="alert('msg')";
~~~



##### 杂谈

###### 声明变量特殊情况

var sex； console.log(sex)；  //只声明不赋值结果：undefined，undefined属性用于存放JavaScript中未存放的值

~~~js
var sex;
console.log(sex);
//输出结果为undefined，未被使用的变量
~~~



console.log(变量)；不声明 不赋值 直接使用 //会报错

~~~js
console.log(mname);
//不声明mname直接输出则会报错
~~~



变量=10;console.log(变量);  不声明只赋值  结果为10，不会出错。**但这里是直接创建了一个全局变量**

~~~js
year=10;
console.log(year);
//不会报错，而是转化成全局变量
~~~



此外，**name**不能作为变量名   在js中 name 既不是关键字也不是保留字，但是在Windows对象中有一个属性名为Windows.name，其作为一个字符串，声明name变量时，相当于给Windows.name赋值